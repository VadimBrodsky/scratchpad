# Recluse Text Processing Example
1. Split the file into paragraphs by cutting at every empty line.
2. Remove the `%` characters from header paragraphs.
3. Process the text of the paragraphs themselves, splitting them into normal parts, emphasized parts, and footnotes.
4. Move all the footnotes to the bottom of the document, leaving numbers in their place.
5. Wrap each piece into the correct HTML tags.
6. Combine everything into a single HTML document.

## Step 1 - Splitting Paragraphs
```javascript
var paragraphs = RECLUSE.split("nn");
paragraphs.length;      // 22
```

## Step 2 - Finding Headers
```javascript
function processParagraph(paragraph) {
    var header = 0;
    while(paragraph.charAt(header) == '%')
        header++;
    if(header > 0)
        return {type: "h" + header, content: paragraph.slice(header +1)};
    else
        return {type: "p", content: paragraph};
}

processParagraph(paragraphs[0]);    //  {type: "h1", content "The Book of Programming"}
```

Using the Map Function
```javascript
map(processParagraph, RECLUSEFILE.split("nn"));
```

## Step 3 - Emphasis and Footnotes
1. If the paragraph starts with an asterik, take off the emphasized part and store it.
2. If the paragraph starts with an opening brace, take off the footnote and store it.
3. Otherwise, take off the part until the first emphasized part or footnote, or until the end of the string, and store it as normal text.
4. If there is anything left in the paragraph, start at step 1 again.

```javascript
function splitParagraph(text) {
    function split(pos) {
        if(pos == text.length) {
            return [];
        }
        else if(text.charAt(pos) == "*") {
            var end = findClosing("*", pos + 1);
            var frag = {type: "emphasized", content: text.slice(pos+1, end)};
            return [frag].concat(split(end + 1));
        }
        else if(text.charAt(pos) == "{") {
            var end = findClosing("{", pos + 1);
            var frag = {type: "footnote", content: text.slice(pos, end)};
            return [frag].concat(split(end + 1));
        } else {
            var end = findOpeningOrEnd(pos);
            var frag = {type: "normal", content: text.slice(pos, end)};
            return [frag].concat(split(end));
        }
    }
    
    function findClosing(character, from) {
    var end = text.indexOf(character, from);
    if(end == -1)   // indexOf returns -1 when it does not find a substring
        throw new Error ("Missing closing '" + character + "'" );
    else
        return end;
    }
    
    function findOpeningOrEnd(from) {
    function indexOrEnd(character) {
        var index = text.indexOf(character, from);
        return index == -1 ? text.length : index;
    }
    return Math.min(indexOrEnd("*"), indexOrEnd("{"));
    }
    return split(0);
}
```