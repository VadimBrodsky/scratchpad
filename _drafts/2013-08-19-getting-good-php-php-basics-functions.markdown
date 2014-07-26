---
layout: post
title: getting-good-php php basics functions php php php
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
<p># PHP String Replacement Functions</p>
<p>## Str_replace<br />
- Replaces sectionsof strings.<br />
- Accepts 3 parameters: string to search, string to replace it with, and a string to do the searching and replacing on.<br />
- Returns a modified string.<br />
- Works like `str_replace` only it is case insensitive.</p>
<p>```php<br />
$str = "This is the original string";<br />
echo str_replace("original", "modified", $str);  // returns "This is the modified string"<br />
```</p>
<p>## Strlen<br />
Returns the number of characters in the string.</p>
<p>```php<br />
echo strlen("Getting Good with PHP");   // returns 21<br />
```</p>
<p>## Strpos<br />
- To find a string within a string.<br />
- It takes two parameters, the orignal string and the substring to search for.<br />
- Returns the number indicating the position within the original string where the substring begins.<br />
- This function accepts a third parameter, to start searching from a specific point.</p>
<p>```php<br />
echo strpos("This is the haystack string", "haystack"); // returns 12<br />
echo strpos("This is the haystack string", "t", 11);<br />
```</p>
