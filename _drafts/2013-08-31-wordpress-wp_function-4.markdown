---
layout: post
title: wordpress wp_function html
categories: []
tags:
- wordpress
- wp_function
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
<p>#wordpress #wp_function</p>
<p># get_template_directory_uri<br />
- Codex reference -- http://codex.wordpress.org/Function_Reference/get_template_directory_uri<br />
- Retrieve template directory URI for the current theme. Checks for SSL.<br />
- Note: Does not return a trailing slash following the directory address.<br />
- In the event a child theme is being used, the parent theme directory URI will be returned.<br />
- `get_template_directory_uri` should be used for resources that are not intended to be included in/over-ridden by a child theme.<br />
- Use `get_stylesheet_directory_uri` to include resources that are intended to be included in/over-ridden by the Child Theme.</p>
<p>```html<br />
&lt;script src=&quot;/scripts/functions.js" type="text/javascript"&gt;<br />
```</p>
