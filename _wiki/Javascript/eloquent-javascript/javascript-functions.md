# JavaScript Functions

## Standard Browser Environment
- `alert()`
- `confirm("Shall we, then?")` - returns `true` or `false`
- `prompt("Tell me everything you know.", "...")` - returns a string

---

## Value Types
- `Number()`
- `String()`
- `Boolean()`
- `isNaN()`

---

## Math
- `Math.cos;` 
- `Math.sin;` 
- `Math.tan;` 
- `Math.acos;` 
- `Math.asin;` 
- `Math.atan;`
- `Math.PI;` 
- `Math.E;`
- `Math.pow;` 
- `Math.sqrt;`
- `Math.max;` 
- `Math.min;`
- `Math.round;`
- `Math.floor;` 
- `Math.ceil;`

---

## Strings
- `string.toUpperCase`
- `string.split(" ")` - splits a string by the parameter, returns an array.
- `string.charAt(0)` - returns the first character in the string, will return `""` if there is no character at that position.
- `string.slice(0, 4)` - returns a string that is a subset of the original (0-4), will leave out the part of the string that does not exist.
- `string.indexOf(":")` - returns the index of a colon in the string.

---

## Objects
- `new Array("one", "two", "three")`
- `new Date(1980, 1, 1)` - year, month, day, hour, second, millisecond.

---

## Arrays
- `arrayVariable.push("new")` - add to value to array
- `arrayVariable.pop()` - remove the last
- `arrayVariable.join(" ")` - returns a string

---

## DOM

### DOM Element Selectors
- `document.getElementById('header');`
- `document.getElementsByTagName('p');`
- `document.getElementsByClassName('dropcap');`
- `document.querySelector('.dropcap');`
- `document.querySelectorAll('.dropcap');`

### DOM Attribute Node
- `.getAttribute()`
- `.setAttribute()`
- `.removeAttribute()`
- `.hasAttribute()`

### DOM Text Node
- `.innerHTML`

```javascript
document.getElementById('target').innerHTML = '<p>Hello World</p>';
```

### Moving in the DOM
- `.parentNode`
- `.previousSibling`
- `.nextSibling`
- `.firstChild`
- `.lastChild`

### Adding and removing Nodes
- `.createElement()`
- `.createTextNode()`
- `.appendChild()`
- `.removeChild()`

```javascript
var p = document.createElement('p');
var snippet = p.createTextNode('this goes into the paragraph');
document.getElementById('target').appendChild(snippet);
document.getElementById('remove-me').parentNode.removeChild();  // double check this
```