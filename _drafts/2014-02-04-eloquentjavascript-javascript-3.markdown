---
layout: post
title: EloquentJavaScript JavaScript javascript javascript javascript javascript javascript
  javascript javascript javascript javascript javascript javascript
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
<p># Chapter 3. Data Structures: Objects and Arrays</p>
<p>## Properties<br />
- Some JavaScript values have other values associated with them.<br />
- These associations are called _properties_.<br />
- Every string has a property `length` - refers to the integer amount of characters in that string.<br />
- Porerties can be accessed either with brackets or dot notation.<br />
- The dot notation is a shorthand, it only works when the name of the propery is a valid variable name.<br />
- The bracket notation can be any expression, it is converted to a string to determine the property name, variables can be property names.<br />
- Trying to read properties from `null` or `undefined` will cause an error.</p>
<p>```javascript<br />
vat text="pueple haze";<br />
text["length"];     // retruns 11<br />
text.length;        // returns 11<br />
```</p>
<p>## Object Values<br />
- In most value types - the properties are fixed.<br />
- In objects - the properties can be freely added, removed, and changed.<br />
- The main role of objects is to be a collection of properties.<br />
- Each object propery is labeled by name, they can be any strings.<br />
- Trying to read nonexistent property gives the value `undefined`.</p>
<p>The keyword `delete` is used to cut off properties.<br />
```javascript<br />
var cat = {color: "gray", name: "Spot", size: 46};</p>
<p>cat.size = 47;<br />
cat.size;       // returns 47</p>
<p>delete cat.size;<br />
cat.size;       // returns undefined<br />
```</p>
<p>If a property that does not yet exist is se with the `=` operator, it is added to the object.<br />
```javascript<br />
var empty = {};<br />
empty.notReally = 1000;<br />
empty;      // returns {notReally: 1000}<br />
```</p>
<p>The operator `in` can be used to test whether an object has a certain property, it produces a boolean.<br />
```javascript<br />
var chineseBox = {};<br />
chineseBox.content = chineseBox;<br />
"content" in chineseBox;            // returns true<br />
"content" in chineseBox.content;     // returns true<br />
```</p>
<p>## Objects as Sets<br />
- A set is a collection of values in which no value occurs more than once.<br />
- To add a name to the set, we set the property in the object to some value.<br />
- Removing a name from the set is done by deleting the property.<br />
- The `in` operator can be used to determine whether a certain name is part of the set.</p>
<p>## Mutability<br />
- Object values can change, the content of a value can be modified, by changing properties.<br />
- With objects, there is a difference between having two references to the smae object and having two different objects that contain the same proeprties.<br />
- JavaScript's `==` opertor, when comparing objects, will return true only if both values given to it are the precise same value.<br />
- Comparing different objects with identical contents will give false.</p>
<p>```javascript<br />
var object1 = {value: 10};<br />
var object2 = object1;<br />
var object3 = {value: 10};</p>
<p>object1 == object2;     // true<br />
object1 == object3;     // false</p>
<p>object1.value = 15;<br />
object2.value;          // 15<br />
object3.value;          // 10<br />
```</p>
<p>## Arrays: Objects as Collections<br />
- New arrays can be created using brackes `var array = [];`.<br />
- The `length` property tells us how many values the array holds.</p>
<p>```javascript<br />
for(var current=0; current &lt; mailArchive.length; current++)<br />
    print(&quot;Processing email #&quot;, current, &quot;: &quot;, mailArchive[current]);<br />
```</p>
<p>## Methods<br />
- Strings and array object contian a number of properties that refer to function values.<br />
- Properties that contain fucntions are called _methods_.<br />
- Some useful string and array methods:<br />
    - `string.toUpperCase`<br />
    - `array.push(&quot;add one at the end&quot;)`<br />
    - `array.join(&quot; &quot;)`<br />
    - `array.pop()`</p>
<p>## The Arguments Object<br />
- Every function adds an arguments variable to its environment when the funciton is called.<br />
- This variable refers to an object that resembles an array.<br />
- It has a property 0 for the first argument, 1 for the second etc.<br />
- It also has a `length` property.<br />
- Some function can take any number of arguments, like `print` does - they typically look over the values in the arguments.<br />
- Other functions can take optional values - when not given by the caller get some sensible default values.</p>
<p>```javascript<br />
function add(number, howmuch) {<br />
    if(arguments.length &lt; 2)<br />
        howmuch = 1;<br />
    return number + howmuch;<br />
}<br />
```</p>
<p>## The Date Object<br />
- A JavaScript object to store date information.<br />
- A date is represented by the amount of milliseconds it is away from January 1, 1970.<br />
- A function `new` is used to build up the object, this funciton is a _constructor_.<br />
- The order of arguments is year, month, day, hour, minute, second, milliseconds.<br />
- The last four arguments are optional, they default to `0` if not defined.<br />
- Month numbers go from `0` to `11`, while day numbers start from `1`.<br />
- Date objects can be inspected with a number of `get` methods.<br />
- All, except for `getDay` also have a `set` variant, that can be used to change the value in the date object.</p>
<p>```javascript<br />
new Date(1987, 0, 12, 20, 30);<br />
var today = new Date();<br />
print(&quot;Year: &quot; , today.getFullYear(), &quot;, month: &quot; , today.getMonth() , &quot;, day: &quot; , today.getDate());<br />
print(&quot;Hour: &quot; , today.getHours() , &quot;, minutes: &quot; , today.getMinutes() , &quot;, seconds: &quot; , today.getSeconds());<br />
print(&quot;Day of the week: &quot; , today.getDay());<br />
```</p>
<p>- The method `getTime()` will get the amount of time that passed from January 1, 1970 in milliseconds.<br />
- Comparing dates with ``,`=` does exactly what is expected.<br />
- Testing whether two dates are equal</p>
<p>```javascript<br />
var wende1 = new Date(1989, 10, 9);<br />
var wende2 = new Date(1980, 10, 9);<br />
wende1.getTime() == wende2.getTime();   // true<br />
```</p>
<p>- The date object also contains information about a time zone.<br />
- The `getTimezoneOffset` function of a Date can be used to find out how many minutes it differs from GMT.</p>
<p>```javascript<br />
new Date().getTimezoneOffset();     // 300 for Toronto<br />
```</p>
<p>## The Math Object<br />
- Objects sometimes play a role of holding a number of related values.<br />
- The `Math` object houses many mathenmatical methods and constants.</p>
<p>```javascript<br />
Math.cos; Math.sin; Math.tan; Math.acos; Math.asin; Math.atan;<br />
Math.PI; Math.E;<br />
Math.pow; Math.sqrt;<br />
Math.max; Math.min; Math.round; Math.floor; Math.ceil;<br />
```</p>
<p>## Enumerable Properties<br />
- Some properties of objects are hidden from `in loops` -- these are _not enumerable_.<br />
- The reason behind this, is to hide these proiperties when looking for relevant information that is stored in the object.<br />
- All properties your programs add to objects are visible.<br />
- There is no way to make them hidden.</p>
