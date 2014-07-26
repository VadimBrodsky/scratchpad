---
layout: post
title: EloquentJavaScript JavaScript javascript javascript javascript javascript javascript
  javascript javascript
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
<p># Chapter 2. Functions<br />
- The keyword `function` is always used when creating a new function.<br />
- When followed by a variable name, the new function will be stored under that name.<br />
- Function definition can be anywhere in the source order, they will be looked-up when called.<br />
- The best function are those that perform a single, simple action - they are easier to name and can be used in a wider variery of situations.<br />
- Good principle - not to add cleverness unless you are absolutely sure you are going to need it, otherwise you'll spend more time writing complicated frameworks for every little bit of functionality instead of any actual work.<br />
- Pure functions are generally without complex side-effects, they always produce the same result based on the same input.</p>
<p>```javascript<br />
function square(x) {<br />
    return x*x;<br />
}<br />
```</p>
<p>## Return Statement<br />
- Some functions can create side effects, while other will create values and return them.<br />
- The `return` keyword indicates the value that the function returns.<br />
- The `return` keyword without a statement will cause the function to return undefined.<br />
- The value from a function without a return statement will be undefined.</p>
<p>## Variable Scope<br />
- Variables that are declared inside the function exist only in that local scope.<br />
- Function can access global varibales.<br />
- Functions defined inside other functions can refer to variables in both their parent and grandparent functions.<br />
- The set of variables visible inside a function is determined by the place of that function in the program text.<br />
- All variables that were defined "above" a function's definition are visible -- lexical scoping.<br />
- Functions are the only things that create a new scope in JavaScript.</p>
<p>```javascript<br />
function multiplyAbsolute(number, factor) {<br />
    function multiply(number) {<br />
        return number * factor;<br />
    }<br />
    if (number &lt; 0)<br />
        return multiply(-number);<br />
    else<br />
        return multiply(number);<br />
}<br />
```</p>
<p>## Anonymous Functions<br />
- The funciton is called and defined in the same place.<br />
- No name is given to the funciton.</p>
<p>```javascript<br />
var a = null;<br />
(a || function(){return &quot;B&quot;;})(); // returns B<br />
```</p>
<p>## Closures<br />
- What happens to a local variables when the function call that created them is no longer on the stack?<br />
- Upwards Funarg Problem - many programming languages forbid it.<br />
- JavaScript makes sure that the local variable is reachable.<br />
- Closure - a function that &quot;closes over&quot; some local variables.<br />
- Allows to create funciton that dynamically create function values.</p>
<p>```javascript<br />
function makeAdder(amount) {<br />
    return function(number) {<br />
        return number + amount;<br />
    }<br />
}<br />
vad addTwo = makeAdder(2);<br />
addTwo(3); // returns 5<br />
```</p>
<p>## Optional Values<br />
- JavaScript is nonstrict about the amount of arguments you can pass to a function.<br />
- If you pass to many - the extra ones are ignored.<br />
- If you pass to few - the missing ones get the value undefined.</p>
<p>```javascript<br />
function power(base, exponent) {<br />
    var result = 1;<br />
    if (exponent === undefined)<br />
        exponent = 2;<br />
    for(var count=0; count  goal)<br />
            return null;<br />
        else<br />
            return find(start+5,"(" + history + " + 5)") || find(start*3, "(" + history + " *3)");<br />
    }<br />
    return find(1,"1");<br />
}</p>
<p>findSequence(24); // returns (((1*3)+5)*3)<br />
```</p>
