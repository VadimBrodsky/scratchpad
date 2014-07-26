---
layout: post
title: getting-good-php php basics php php php php php php php php php
categories: []
tags:
- basics
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
<p>#php #basics @getting-good-php</p>
<p># Operators in PHP</p>
<p>## Arithmetic Operators</p>
<p>```php<br />
$num = 10;<br />
$num = $num + 10;   // Addition<br />
$num = $num - 5;    // Subtraction<br />
$num = $num / 2;    // Division<br />
$num = $num * 0.2;  // Multiplication<br />
$num = $num % 3;    // Modulus<br />
```</p>
<p>## String Operators</p>
<p>The only string operator is concatination.</p>
<p>```php<br />
"first string" . "second string";<br />
```</p>
<p>## Assignment Operators</p>
<p>```php<br />
$num = 10;<br />
$num += 10;   // Addition<br />
$num -= 5;    // Subtraction<br />
$num /= 2;    // Division<br />
$num */ 0.2;  // Multiplication<br />
$num %/ 3;    // Modulus<br />
```</p>
<p>## Inrementing and Decrementing Operators</p>
<p>- Post-increment will perform the incrementing after it return the value.<br />
- Pre-increment will increment the value first then return it.</p>
<p>```php<br />
$num++; // Post increment<br />
$num--; // post decrement<br />
++$num; // Pre increment<br />
--$num; // Pre decrement<br />
```</p>
<p>## Comparison Operators</p>
<p>- Equal operator `==` will try to interpret and convert values into matching data types before comparison.<br />
- Identity oprtator `===` does not try to interpret and convert values into matching data types.<br />
- Not operator `!=` and `!==` opposite of equal and identical operator.<br />
- Greater / less than and equals `&gt; =  10; // false<br />
4 &lt;= 4 // true;<br />
```</p>
<p>## Logical Operators</p>
<p>- Most of the values in PHP can be interpreted as being true or false.<br />
- Most values are true.<br />
- These are the false values<br />
  - `&quot;&quot;`<br />
  - `0`<br />
  - `false`<br />
  - `null`<br />
  - `array()`</p>
<p>```php<br />
$truth = true;<br />
$lie === !$truth;<br />
```</p>
<p>```php<br />
$bacon; $eggs;<br />
$meal === $bacon &amp;&amp; $eggs;<br />
```</p>
<p>```php<br />
$this; $that;<br />
$either === $this || $that;<br />
```</p>
<p>```php<br />
// Conditional operator<br />
// conditional ? if_true : if_false<br />
$raining = $weather ? &quot;Take umbrella&quot; : &quot;Wear Shorts&quot;;<br />
```</p>
