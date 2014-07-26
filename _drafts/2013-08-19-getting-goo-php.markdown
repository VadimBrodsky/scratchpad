---
layout: post
title: getting-good-php php basics php
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
<p>#php @getting-good-php #basics</p>
<p># Partials in PHP</p>
<p>- `include` - if the file cannot be found, displays a warning but will execute.<br />
- `require` - if the file cannot be found, displays a fatal error and will stop execution.<br />
- `include_once` - just like include, but if the file was already included it will not include it again.<br />
- `require_once` - just like require, but if the file was already included it wlll not include it again.</p>
<p>```php<br />
include partials/great_houses.php;<br />
require ("houses.php");<br />
require_once("partials/dothraki.php");<br />
```</p>
