---
tags: @LearningjQuey
---

## Basic Document

```html


    
        
        <title>Hello</title>
        
        
        
    
    
        <h1>Hello World</h1>
    

```

```javascript
    $(document).ready(function() {
        console.log("Hello World");
    });
```
## Ready Function
- jQuery allows to schedule function calls for  firing once the DOM is loaded - without necessarily waiting for images to fully render.
- `$(document).ready()` - allows for an elegant cross-browser solution.
- We can either call an anonymous function, or use a pre-defined function as a parameter of the `.ready()` method.

### Pre-Defined Function
```javascript
function addHighlightClass() {
    $('div.poem-stanza').addClass("highlight");
}

// function call
$(document).ready(addHighlightClass);
```

### Anonymous Function
```javascript
$(document).ready(function() {
    $('div.poem-stanza').addClass('highlight');
});
```


## jQuery Functions

### addClass
- `.addClass()`
- Applied a CSS class to the part of the page that was selected.

### removeClass
- `.removeClass()`
- Removes a CSS class of the selected element.

### concole.log
- `console.log()`
- Used for debugging - logging into the console.