---
layout: post
title: getting-good-php php basics functions php php
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
<p># PHP JSON Functions<br />
- Way to pass data to and from JavaScript with Ajax.<br />
- JASON - JavaScript objects, similar to PHP associative arrays.</p>
<p>## json_encode<br />
Convert an associative array to JSON.</p>
<p>```php<br />
$houses = array("name" =&gt; "Stark", "sigil" =&gt; "Direwolf", "motto" =&gt; "Winter is Coming");<br />
print_r(json_encode($houses));<br />
```</p>
<p>## json_decode<br />
- Convert JSON to a PHP object.<br />
- First parameter - JSON string.<br />
- Second parameter - `true` to get an associative array instead of an object.</p>
<p>```php<br />
$decoded = json_decode('{"name":"Stark","sigil":"Direwolf","motto":"Winter is Coming"}', true);<br />
```</p>
