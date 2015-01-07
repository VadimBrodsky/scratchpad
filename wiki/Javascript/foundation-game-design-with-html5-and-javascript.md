---
tags: #JavaScript @Game-Design
---

# Foundation Game Design with HTML5 and JavaScript

## Console Functions
```javascript
console.log();
```

## Object Selectors
```javascript
document.querySelector();       // Selects the first object that matches the criteria
document.querySelectorAll();    // Selects all of the objects, places in an array
```

## HTML Elements
```javascript
variableName.innerHTML          // The content of an HTML tag
variableName.setAttribute("id", "example");
```

## Edit CSS
```javascript
variableName.style.color = "red";
variableName.style.textDecoration ="underline";
```

## Creating Elements
```javascript
document.createElement("p");
document.body.appendChild(variable);
variableName.parentNode.removeChild(variable);
```

## AddEvent Listener
Mouse events: `mouse down`, `mouse up`, `click`, `dblclick`, `mousemove`, `mouseover`, `mouseout`

```javascript
var button = document.querySelector("button");
button.addEventListener("click", clickHandler, false);
function clickHandler () {
    console.log("Button Clicked");   
}
```

## Remove Event Listener
```javascript
button.removeEventListener("click", clickHandler, false);
button.style.display = "none";
```