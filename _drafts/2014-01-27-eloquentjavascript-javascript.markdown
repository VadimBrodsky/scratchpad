---
layout: post
title: EloquentJavaScript JavaScript javascript javascript
categories: []
tags:
- JavaScript
status: publish
type: post
published: true
meta:
  _encloseme: '1'
author:
  login: vadimbrodsky
  email: vadim@vadimbrodsky.com
  display_name: Vadim
  first_name: Vadim
  last_name: Brodsky
---
<p>@EloquentJavaScript #JavaScript</p>
<p># JavaScript Functions</p>
<p>## Standard Browser Environment<br />
- `alert()`<br />
- `confirm("Shall we, then?")` - returns `true` or `false`<br />
- `prompt("Tell me everything you know.", "...")` - returns a string</p>
<p>---</p>
<p>## Value Types<br />
- `Number()`<br />
- `String()`<br />
- `Boolean()`<br />
- `isNaN()`</p>
<p>---</p>
<p>## Math<br />
- `Math.cos;`<br />
- `Math.sin;`<br />
- `Math.tan;`<br />
- `Math.acos;`<br />
- `Math.asin;`<br />
- `Math.atan;`<br />
- `Math.PI;`<br />
- `Math.E;`<br />
- `Math.pow;`<br />
- `Math.sqrt;`<br />
- `Math.max;`<br />
- `Math.min;`<br />
- `Math.round;`<br />
- `Math.floor;`<br />
- `Math.ceil;`</p>
<p>---</p>
<p>## Strings<br />
- `string.toUpperCase`<br />
- `string.split(" ")` - splits a string by the parameter, returns an array.<br />
- `string.charAt(0)` - returns the first character in the string, will return `""` if there is no character at that position.<br />
- `string.slice(0, 4)` - returns a string that is a subset of the original (0-4), will leave out the part of the string that does not exist.<br />
- `string.indexOf(":")` - returns the index of a colon in the string.</p>
<p>---</p>
<p>## Objects<br />
- `new Array("one", "two", "three")`<br />
- `new Date(1980, 1, 1)` - year, month, day, hour, second, millisecond.</p>
<p>---</p>
<p>## Arrays<br />
- `arrayVariable.push("new")` - add to value to array<br />
- `arrayVariable.pop()` - remove the last<br />
- `arrayVariable.join(" ")` - returns a string</p>
<p>---</p>
<p>## DOM</p>
<p>### DOM Element Selectors<br />
- `document.getElementById('header');`<br />
- `document.getElementsByTagName('p');`<br />
- `document.getElementsByClassName('dropcap');`<br />
- `document.querySelector('.dropcap');`<br />
- `document.querySelectorAll('.dropcap');`</p>
<p>### DOM Attribute Node<br />
- `.getAttribute()`<br />
- `.setAttribute()`<br />
- `.removeAttribute()`<br />
- `.hasAttribute()`</p>
<p>### DOM Text Node<br />
- `.innerHTML`</p>
<p>```javascript<br />
document.getElementById('target').innerHTML = '
<p>Hello World</p>
<p>';<br />
```</p>
<p>### Moving in the DOM<br />
- `.parentNode`<br />
- `.previousSibling`<br />
- `.nextSibling`<br />
- `.firstChild`<br />
- `.lastChild`</p>
<p>### Adding and removing Nodes<br />
- `.createElement()`<br />
- `.createTextNode()`<br />
- `.appendChild()`<br />
- `.removeChild()`</p>
<p>```javascript<br />
var p = document.createElement('p');<br />
var snippet = p.createTextNode('this goes into the paragraph');<br />
document.getElementById('target').appendChild(snippet);<br />
document.getElementById('remove-me').parentNode.removeChild();  // double check this<br />
```</p>
