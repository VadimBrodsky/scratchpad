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
<p># PHP Math Functions</p>
<p>## max / min<br />
- Find the higherst or the lower number.<br />
- Can pass an array instead of individual parameters.</p>
<p>```php<br />
echo max(12, 9, 4, 16, 2, 3.14);    // 16<br />
echo min(array(12, 9, 4, 16, 2, 3));    //2<br />
```</p>
<p>## mt_rand<br />
- Random number generator.<br />
- The two parameters are optional, represent the min and max range.<br />
- Uses the Mersenne Twister algorithm to generate a random number, it is faster than `rand`.</p>
<p>```php<br />
echo mt_rand();<br />
echo mt_rant(0,100);<br />
```</p>
<p>## round / ceil / floor<br />
- To round numbers.<br />
- `round` - mathematical.<br />
- `ceil` - up.<br />
- `floor` - down.<br />
- Second parameter determines the number of digits to keep.</p>
<p>```php<br />
echo round(7.5);<br />
echo round(3.14159, 2);<br />
echo ceil(2.1);<br />
echo floor(4.9);<br />
```</p>
