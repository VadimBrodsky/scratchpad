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
<p># PHP Date and Time Functions</p>
<p>## Parse_date<br />
- Takes a date string and returns an associative array with the details of the date.</p>
<p>```php<br />
print_r(date_parse("2013-08-20 21:33"));<br />
```</p>
<p>## Time<br />
Gives the unix timestamp - number of seconds that have passed since January 1, 1970.</p>
<p>```php<br />
echo time();<br />
```</p>
<p>## Strftime<br />
- Practical date format.<br />
- First parameter - a string with tokens to get the desired time format.<br />
- Second parameter (optional) - time to parse, by default the current time.<br />
- More info on tokens here - http://strfti.me/</p>
<p>```php<br />
echo strftime("%B %d, %Y");<br />
```</p>
