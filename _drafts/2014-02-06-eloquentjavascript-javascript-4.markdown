---
layout: post
title: EloquentJavaScript JavaScript javascript javascript javascript javascript javascript
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
<p># Chapter 4. Error Handling<br />
- Most programs need a kind of a disaster plan to handle unexpected input.</p>
<p>## Types of Problems<br />
- Most problems that a program can encounter can be divided into two categories:<br />
    - Programmer Mistakes<br />
    - Run-time problems</p>
<p>## Returning a Special Value<br />
- When a function encounters a problem that it cannot solve itself, one possible reaction is to return a value that it could not normally return.<br />
- Usually the value of `undefined` is returned in these situations.<br />
- This does not work whem a funciton is expected to return every possible kind of value, like listing the contents of an array.<br />
- Also this kind of checking can lead to a lot of clutter in the code.</p>
<p>## Exceptions<br />
- When a function cannot return normally, we want it to stop running and jump immediately back to a place that knows how to handle the problem.<br />
- This process is called _exception handling_.<br />
- It is possible for code to raise (or throw) an exception, which is a value.<br />
- Raising an exception is similair to a `return` statement - but it does not jump out of the current function but also out of its callers, all the way to the top-level call that started the current execution.<br />
- This is called _unwinding the stack_.<br />
- It is possible to set obstacles for exceptions along the stack - these `catch` the exceptions and can do something with it.<br />
- After this the program continues running at the point where the exception was caught.<br />
- THe big advantage of exceptions -- error handling code is necessary only at the point where the error occurs and at the point where it is handled. The functions in between can forget all about it.</p>
<p>```javascript<br />
function lastElement(array){<br />
    if(array.length &gt; 0)<br />
        return array[array.length - 1];<br />
    else<br />
        throw "Cannot take the last element of an empty array.";<br />
}</p>
<p>function lastElementPlusTen(array){<br />
    return lastElement(array) + 10;<br />
}</p>
<p>try {<br />
    print(lastElementPlusTen([]));<br />
}<br />
catch(error) {<br />
    print("Something went wrong: ", error);<br />
}<br />
```<br />
- The keyword `throw` is used to raise an exception.<br />
- The keyword `try` sets up an obstacle for exceptions.<br />
- When the code in the block after it raises an exception, the catch block will be executed.<br />
- The variable named in the parentheses after the cord catch will hold the excpetion value when the block executes.<br />
- The `try` statements can be followed by a `finally` keyword, which will run the code regardless of what is happening.<br />
- The `finally` keyword usually will clean up the code if something went wrong.</p>
<p>```javascript<br />
var currentThing = null;<br />
function processThing(thing){<br />
    var prevThing = thing;<br />
    currentThing = thing;<br />
    try {<br />
        // do complticated processing<br />
    }<br />
    finally {<br />
        currentThing = prevThing;<br />
    }<br />
}<br />
```</p>
<p>## Error Objects<br />
- There is a special type of object that is raised for problems.<br />
- These error objects always haave a message property containing a description of the problem.</p>
<p>```javascript<br />
try {<br />
    print(Sasquatch);<br />
}<br />
catch(error) {<br />
    print("Caught: " + error.message);<br />
}<br />
```</p>
<p>- Custom objects can be raised using the `new` keyword and the `Error` constructor, to give a message as argument.</p>
<p>```javascript<br />
throw new Error("Custom Error message was thrown!");<br />
```</p>
<p>## Unhandled Exceptions<br />
- When an exception makes it all the way to the bottom of the stack without being caught -- it gets handled by the environment.<br />
- The result would be different depending on the JavaScript environment -- in the browser it would be displayed in the console.<br />
- For programmer mistakes or problems that the program cannot hangle - letting the error go thorough is ok.<br />
- An ungandled exception is a reasonable way to signal a broken program.</p>
<p>## Selective Catching<br />
- When explicitly handling an exception using `catch`, care must be taken to not catch too much.</p>
<p>```javascript<br />
var invalidInputError = new Error("Invalid numeric input");</p>
<p>function inputNumber(){<br />
    var input = Number(prompt("Give me a number", ""));<br />
    if(isNaN(input))<br />
        throw InvalidInputError;<br />
    return input;<br />
}</p>
<p>for(;;){<br />
    try{<br />
        alert(inputNumber() + 5);<br />
        break;<br />
    }</p>
<p>    catch(e){<br />
        if(e != invalidInputError)<br />
            throw e;<br />
        alert("You did not input a number. Try again.");<br />
    }<br />
}<br />
```</p>
