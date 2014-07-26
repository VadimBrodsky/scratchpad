---
layout: post
title: getting-good-php php basics functions php php php php
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
<p># PHP Array Functions</p>
<p>## Array_push<br />
- To add one or more items to the end of the array.<br />
- Modifies the array that is being passed.</p>
<p>```php<br />
$starks = array("Rob", "John", "Brandon", "Riccon");<br />
array_push($starks, "Ariya");<br />
```</p>
<p>## Array_pop<br />
Opposite of `array_push`, it pulls the last item off of the array and returns it.</p>
<p>```php<br />
$starks = array("Rob", "Brandon", "Riccon");<br />
array_pop($starks);<br />
```</p>
<p>## Array_unshift<br />
Add an item to the beginning of an array.</p>
<p>```php<br />
$starks = array("Rob", "Brandon", "Riccon");<br />
array_unshift($starks, "John", "Sansa", "Arya");<br />
```</p>
<p>## Array_shift<br />
Pulls the first item off an array and returns it.</p>
<p>```php<br />
$starks = array("Rob", "Brandon", "Riccon");<br />
array_pop($starks);<br />
```</p>
