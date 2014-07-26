---
layout: post
title: getting-good-php php basics functions php php php php php php
categories: []
tags:
- basics
- functions
- php
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
<p>#php #basics #functions @getting-good-php</p>
<p># PHP Array-Item Funcitons</p>
<p>## Array_map<br />
- To map an array with another array.<br />
- Pass a name of a function to operate on each item in an array, via a stringin the first parameter.</p>
<p>```php<br />
$starks = array("Rob", "Brandon", "Riccon");<br />
$F = array_map("strtoupper", $starks);<br />
```</p>
<p>## Array_walk<br />
- Similar to `arra_map`, but it does not returns an array but rather a `true` or `false`.<br />
- The funciton name is passed as the second parameter.</p>
<p>```php<br />
function greet ($name) {<br />
    echo "Hello, $name n";<br />
}<br />
$starks = array("Rob", "Brandon", "Riccon");<br />
array_walk($starks, "greet");<br />
```</p>
<p>## Array_search<br />
- To search within arrays.<br />
- First parameter is the value to search for, second for the array to search within.</p>
<p>```php<br />
$starks = array("Rob", "Brandon", "Riccon");<br />
echo array_search("Brandon", $starks);  // 1<br />
```</p>
<p>## In_array<br />
- Find whether an item is within an array.<br />
- Returns either `true` or `false`.</p>
<p>```php<br />
$starks = array("Rob", "Brandon", "Riccon");<br />
var_dump(in_array("Brandon", $starks));<br />
```</p>
<p>## Array_slice<br />
- To slice a part of an array.<br />
- First parameter - array.<br />
- Second parameter - offset (index to begin the slice from, if the number is negative it will be counted from the end of the array).<br />
- Third parameter - length of the slice.</p>
<p>```php<br />
$starks = array("Rob", "Brandon", "Riccon");<br />
print_r(array_slice($starks, 1, 1));    // Brandon<br />
print_r(array_slice($starks, 1, 2));    // Brandon, Riccon<br />
```</p>
<p>## Array_splice<br />
- Similar to the `array_slice` function, but will insert new values or array into the cutout place.<br />
- Fourth parameter - either a single value or an array of values that will replace the values that are being sliced out.<br />
- The changes are made to the original array.</p>
<p>```php<br />
$starks = array("Rob", "Brandon", "Riccon");<br />
array_splice($starks, 0, 2, "John");<br />
```</p>
