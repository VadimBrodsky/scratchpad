---
layout: post
title: EloquentJavaScript JavaScript javascript javascript javascript javascript javascript
  JavaScript javascript javascript javascript
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
<p># Chapter 1. Basic JavaScript: Values, Variables, and Control Flow</p>
<p>## Basic Value Types in JavaScript<br />
- Numbers<br />
- Strings<br />
- Booleans - `true` or `false` (`0`, `NaN`, `""` all count as `false`)<br />
- Objects<br />
- Functions<br />
- Undefined (null == undefined)</p>
<p>## Variables<br />
- Variables are created by invoking their name, but this is a bad practice.<br />
- The keyword `var` is used to create new variables explicitly.<br />
- Variable names cannot include spaces, cannot start with a digit.<br />
- Can use `$` and `_` in variable names.</p>
<p>## Keywords and Reseved Words<br />
```javascript<br />
abstract boolean break byte case catch char class const continue debugger default delete do double else enum export extends false final finally float for function goto if impements import in instanceof int interface long native new null package private protected public return short static super switch synchronized this throw throws transient true try typeof var void volatile while with<br />
```</p>
<p>## Operators - Binary and Unary<br />
- plus `+` (can be used on strings to concatinate)<br />
- minus `-`<br />
- multiply `*`<br />
- division `/`<br />
- modulo `%`<br />
- type of `typeof`</p>
<p>All arithmetic operations on the value `NaN` result in `NaN`</p>
<p>## Special String Characters<br />
- Use the backslash `` to add a special meaning to a string.<br />
- New line `n`<br />
- Tab `t<br />
- Quote `'`</p>
<p>```javascript<br />
"A newline character is written like "\n"."<br />
```</p>
<p>## Boolean Operators<br />
- less ``<br />
- less than or equal to `='<br />
- equal to `==`<br />
- not equal to `!==`<br />
- Logical and `&amp;&amp;`  // can be used on non boolean values<br />
- Logical or `||`   // can be used on non boolean values<br />
- Logical not `!`<br />
- Precisely equal `===`<br />
- Not precisely equal `!==`</p>
<p>```javascript<br />
var input= prompt("What is your name?", "Kilgore Trout");<br />
console.log("Hello " + (input || 'dear'));<br />
```</p>
<p>## Expressions and Statements<br />
- An expression can be content to just produce a value, but a statement amounts to something only if it somehow changes the world.<br />
- The changes are called - side effects<br />
- Every statement needs to terminated by a semicolon `;`<br />
- A lone semicolon can be used to produce an empty statement.</p>
<p>## The Environment<br />
- The collection of variables and their values that exist at a given time.<br />
- It always contains a number of standard variables.<br />
- When a browser loads a page it creates a new environment and attaches the standard variables to it.<br />
- The variables only survive on that page, until the browser goes to a new page.<br />
- It is possible to modify the environment with new values, this can damage functionality.</p>
<p>## Conditionals<br />
- Use to create seperate parallel paths in execution.</p>
<p>```javascript<br />
if(true == false) {<br />
    ...<br />
} else if {<br />
    ...<br />
} else {<br />
    ...<br />
    };<br />
```</p>
<p>```javascript<br />
switch(value) {<br />
    case "rock": console.log("breaks scissors");<br />
        break;<br />
    case "paper": console.log("covers rock");<br />
        break;<br />
    case "scissors": console.log("cuts paper");<br />
        break;<br />
    default: console.log("It's a tie");<br />
        break;<br />
}<br />
```</p>
<p>## Loops<br />
- Cases statements to be executed multiple times.<br />
- To the world outide the loop, the loop counts as a single statement.<br />
- `while` loop is the simplest loop - continues while the condition is true.<br />
- `do` loop will execute its body at least once, only then will test the condition.<br />
- `for` loop is a shorter and more comprehensive form of the `while` loop.<br />
- `break` keyword is used to stop the execution of the loop ahead of time.</p>
<p>```JavaScript<br />
var result = 1;<br />
var counter = 0;<br />
while (counter &lt; 10 ) {<br />
    result = result * 2;<br />
    counter++;<br />
}<br />
result;<br />
```</p>
<p>```javascript<br />
do {<br />
    var input = prompt(&quot;Who are you?&quot;);<br />
}<br />
```</p>
<p>```javascript<br />
for (var number = 0; number &lt;= 12; number = number + 2) {<br />
    ...<br />
}<br />
```</p>
<p>## Functions<br />
- A function is a piece of program wrapped in a value.<br />
- Can be evoked by using the function value that contains it.<br />
- In the browser, the variable `alert` holds a function that shows a dialog box with a message.<br />
- Values given to functions are called arguments.<br />
- Functions can produce side effects or return values.</p>
<p>```javascript<br />
alert(&quot;Good Morning!&quot;);<br />
```</p>
