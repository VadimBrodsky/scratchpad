---
layout: post
title: getting-good-php php basics php php php php php php php php
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
<p># Control Structures</p>
<p>## If and Else</p>
<p>```php<br />
if ($argument == true) {<br />
    echo "This executes";<br />
} else if ($argument == false) {    // elseif as one word also works<br />
    echo "This execures";<br />
} else {<br />
    echo "$argument was null";<br />
}<br />
```</p>
<p>Alternative syntax: can use `endif`, `endfor`, `endforeach` and `endswitch` to replace curly braces.</p>
<p>```php<br />
if ($argument == true):<br />
    echo "This executes";<br />
elseif ($argument == false):<br />
    echo "This executes";<br />
else:<br />
    echo "There was a null";<br />
endif;<br />
```</p>
<p>## For and Foreach</p>
<p>```php<br />
$starks = array("Jon", "Rob", "Brandon", "Riccon");<br />
echo "
<ul>";<br />
for($i=0, $length = count($starks); $i &lt; $length; $i++) {<br />
    echo &quot;
<li> $starks[$i] </li>
<p>"<br />
}<br />
echo "</ul>
<p>"<br />
```</p>
<p>```php<br />
$stark = array("name" =&gt; "John Snow", "father" =&gt; "Eddard Stark","mother" =&gt; "Unknown");<br />
echo "
<ul>"<br />
foreach($stark as $value) {<br />
    echo "
<li> $value </li>
<p>";<br />
}<br />
echo "</ul>
<p>";</p>
<p>foreach($stark as $key =&gt; $value) {<br />
    echo "
<li> His $key is $value. </li>
<p>";<br />
}<br />
```</p>
<p>## Return</p>
<p>Whatever value is passed to the `return` statement is the value that will be returned to the function that was called.</p>
<p>```php<br />
function say_hello ($name) {<br />
    return "Hello, $name";<br />
}<br />
echo say_hello("Eddard");<br />
```</p>
<p>## Continue</p>
<p>Will skip the rest of the loop and will start the next iteration.</p>
<p>```php<br />
$starks = array("Jon", "Rob", "Brandon", "Riccon");<br />
foreach($starks as $stark) {<br />
    if($stark === "John") {<br />
        continue;<br />
    }<br />
    echo $stark;<br />
}<br />
```</p>
<p>## Break</p>
<p>Acts like `continue` but ends the entire loop.</p>
<p>```php<br />
$starks = array("Jon", "Rob", "Brandon", "Riccon");<br />
foreach($starks as $stark) {<br />
    if($stark === "John") {<br />
        break;<br />
    }<br />
    echo $stark;<br />
}<br />
```</p>
<p>## Switch</p>
<p>```php<br />
$house = "Stark";<br />
switch ($house) {   // The switch evaluation is equal to ==<br />
    case "Stark":<br />
        echo "Winter Is Coming";<br />
        break;<br />
    case "Lannister":<br />
        echo "Hear Me Roar!";<br />
        break;<br />
    case "Targaryen":<br />
        echo "Fire And Blood";<br />
        break;<br />
    default:<br />
        echo "A Lannister always pays his debts";<br />
}<br />
```</p>
