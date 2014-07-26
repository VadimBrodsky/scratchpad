---
layout: post
title: Game-Design JavaScript javascript javascript javascript javascript javascript
  javascript javascript
categories: []
tags:
- JavaScript
status: publish
type: post
published: true
meta:
  _pingme: '1'
  _encloseme: '1'
author:
  login: vadimbrodsky
  email: vadim@vadimbrodsky.com
  display_name: Vadim
  first_name: Vadim
  last_name: Brodsky
---
<p>#JavaScript @Game-Design</p>
<p># Foundation Game Design with HTML5 and JavaScript</p>
<p>## Console Functions<br />
```javascript<br />
console.log();<br />
```</p>
<p>## Object Selectors<br />
```javascript<br />
document.querySelector();       // Selects the first object that matches the criteria<br />
document.querySelectorAll();    // Selects all of the objects, places in an array<br />
```</p>
<p>## HTML Elements<br />
```javascript<br />
variableName.innerHTML          // The content of an HTML tag<br />
variableName.setAttribute("id", "example");<br />
```</p>
<p>## Edit CSS<br />
```javascript<br />
variableName.style.color = "red";<br />
variableName.style.textDecoration ="underline";<br />
```</p>
<p>## Creating Elements<br />
```javascript<br />
document.createElement("p");<br />
document.body.appendChild(variable);<br />
variableName.parentNode.removeChild(variable);<br />
```</p>
<p>## AddEvent Listener<br />
Mouse events: `mouse down`, `mouse up`, `click`, `dblclick`, `mousemove`, `mouseover`, `mouseout`</p>
<p>```javascript<br />
var button = document.querySelector("button");<br />
button.addEventListener("click", clickHandler, false);<br />
function clickHandler () {<br />
    console.log("Button Clicked");<br />
}<br />
```</p>
<p>## Remove Event Listener<br />
```javascript<br />
button.removeEventListener("click", clickHandler, false);<br />
button.style.display = "none";<br />
```</p>
