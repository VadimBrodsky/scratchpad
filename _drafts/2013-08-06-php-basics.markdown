---
layout: post
title: getting-good-php php basics php php php php php php
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
<p># Variables in PHP</p>
<p>- Begins with a dollar sign `$`<br />
- Can be followed by any number of letters, numbers or underscores<br />
- The first character afer the dollar sign cannot be a number<br />
- PHP developers usually separate vairiable terms with underscores in the name.</p>
<p>```php<br />
$variable = "
<p>Something goes here</p>
<p>";<br />
```</p>
<p># Data types in PHP</p>
<p>## Strings</p>
<p>- Any set of characters between two quotes.<br />
- Can be delimetred with double or single quotes - `"a" or 'b'`<br />
- To escape the quote sign use the backslash - `'`<br />
- `"this is a string"`<br />
- `'That'll do it.'`</p>
<p>Double quotes allow for interpolation:</p>
<p>```php<br />
$name = "Newton";<br />
echo "Hello, $name.";<br />
```</p>
<p>## Numbers</p>
<p>- PHP has only two types of numbers - integers and floats.<br />
- The only non-number characters that are allowed are decimals, minus and scientific notation.</p>
<p>```php<br />
1002.1223<br />
-232<br />
1.34e5<br />
```</p>
<p>## Booleans</p>
<p>- Has only two values: `true` or `false`<br />
- They are not case sensitive</p>
<p>```php<br />
$life = true;<br />
$death = false;<br />
```</p>
<p>## Null</p>
<p>- The data type that represents nothing - the valueless value.<br />
- For exaple when you create an uninitialized value.</p>
<p>```php<br />
$hello;<br />
echo $hello; // will be Null<br />
```</p>
<p>## Array</p>
<p>- A list of variables.<br />
- To setup, use the keyword `array(item1, item2, itenm)`<br />
- In PHP arrays can be both numeric (with index) and associative (with key value pair).<br />
- The `=&gt;` is called `T_DOUBLE_ARROW`<br />
- Arrays in PHP are not limited to one data type per array.</p>
<p>```php<br />
$this_is_a_numeric_array = array("HTML", "CSS", "JavaScript", "PHP");<br />
echo $this_is_a_numeric_array[0];</p>
<p>$this_is_an_associative_array = array (<br />
    "name" =&gt; "Eddard Stark",<br />
    "birtplacee" =&gt; "Winterfell",<br />
    "married" =&gt; true,<br />
    "allies" =&gt; array("Karstarks", "Tullies", "Mormonts")<br />
);<br />
echo $this_is_an_associative_array["name"];<br />
```</p>
