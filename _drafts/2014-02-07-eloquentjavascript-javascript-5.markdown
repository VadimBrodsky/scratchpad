---
layout: post
title: EloquentJavaScript JavaScript javascript javascript javascript javascript javascript
  javascript
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
<p># Chapter 5. Functional Programming<br />
- The programmer is always looking for ways to keep the complexity of his programs as low as possible.<br />
- A way to do this is try to make code more abstract.<br />
- If you assume a certain basic knowledge in the audience, you can talk in a language that deals with bigger concepts and express things in a much shorter and clever way.</p>
<p>## Higher-Order Functions<br />
- Since "doing something" can be represented as a function and since functions are also values, we canpass our actions as a function value.<br />
- Functions that operate on other functions are called _higher-order functions_.<br />
- Higher-order functions can be used to generalize many algorithms that regular functions cannot easlity describe.<br />
- Instead of a messy set of variables and loops, you can decompose algorithms into a combination of a few fundamental algorithms, which invoked by name and do not have to be typed out again and again.<br />
- Being able to write what we want to do instead of how we do it, means we are working at a higher level of abstraction.</p>
<p>```javascript<br />
function forEach(array, action){<br />
    for(var i=0; i &lt; array.length; i++)<br />
        action(array[i]);<br />
}</p>
<p>function sum(numbers){<br />
    var total = 0;<br />
    forEach(numbers, function(number){<br />
        total += number;<br />
    });<br />
    return total;<br />
}<br />
```</p>
<p>## Modifying Functions<br />
- Higher-order functions can modify the function value that is given.</p>
<p>```javascript<br />
function negate(func) {<br />
    return function(x){<br />
        return !func(x);<br />
    };<br />
}<br />
var isNotNaN = negate(isNaN);<br />
isNotNaN(NaN);      // false<br />
```</p>
<p>- The function returned by negate feeds the argument it is given to the original funciton `func` and then negates the result.<br />
- Functions have a method called `apply`, which is used for situations in which we don&#039;t know how many agrument the parameter function has.<br />
- It takes two arguments:<br />
    - The first ?<br />
    - The second - is an array containing the arguments to which a function must be applied.</p>
<p>```javascript<br />
function negate(func){<br />
    return function(){<br />
        return !func.apply(null, arguments);<br />
    };<br />
}<br />
```</p>
<p>## The reduce Function<br />
- Reduce combines an array into a single value.<br />
- By repeatedly using a function that combines an element of the array with a base value.<br />
- In JavaScript addition is an operator and not a function, we had to put it into a funciton.<br />
- Reduce takes the function as its first argument instead of last, is due to tradition, and it allows to use partial application.</p>
<p>```javascript<br />
function reduce(combine, base, array){<br />
    forEach(array, function(element){<br />
       base = combine(base, element);<br />
    });<br />
    return base;<br />
}<br />
function add(a, b){<br />
    return a + b;<br />
}<br />
function sum(numbers){<br />
    return reduce(add, 0, numbers);<br />
}<br />
```</p>
<p>A function that takes an array of numbers as its argument and returns the amount of zeroes that occur in it:</p>
<p>```javascript<br />
function countZeroes(array){<br />
    function counter(total, element){<br />
        return total + (element === 0 ? 1 : 0);<br />
    }<br />
    return reduce(counter, 0, array);<br />
}<br />
```</p>
<p>## Mapping Arrays<br />
- It goes over an array, applying a function to every element.<br />
- It builds a new array based on the results of the function and the values.</p>
<p>```javascript<br />
function map(func, array) {<br />
    forEach(array, function(element) {<br />
        result.push(func(element));<br />
    });<br />
    return result;<br />
}</p>
<p>map(Math.round,  [0.01, 2, 9.89, Math.PI]);     // [0,2,10,3]<br />
```</p>
