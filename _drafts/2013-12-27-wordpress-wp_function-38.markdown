---
layout: post
title: wordpress wp_function php
categories: []
tags:
- wordpress
- wp_function
status: publish
type: post
published: true
meta:
  _encloseme: '1'
author:
  login: vadimbrodsky
  email: vadim@vadimbrodsky.com
  display_name: Vadim
  first_name: Vadim
  last_name: Brodsky
---
<p>#wordpress #wp_function</p>
<p># get_the_date<br />
- Codex reference -- http://codex.wordpress.org/Function_Reference/get_the_date<br />
- The `get_the_date` template tag retrieves the date the current `$post` was written.<br />
- Unlike `the_date()` this tag will always return the date.</p>
<p>```php<br />
_e('You are viewing the ' . get_the_date() . ' daily archives');<br />
_e('You are viweing the ' . get_the_date('Y') . 'yearly archives');<br />
_e('You are viewing the "' . single_cat_title('', false ) . '" Archives');<br />
```</p>
