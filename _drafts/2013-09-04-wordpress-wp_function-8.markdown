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
<p># register_nav_menus<br />
- Codex reference -- http://codex.wordpress.org/Function_Reference/register_nav_menus<br />
- Registers multiple custom navigation menus.<br />
- To be used in the `funcitons.php` file.</p>
<p>```php<br />
register_nav_menus(<br />
    array(<br />
        'main-nav-header-top' =&gt; 'Main Nav, Top of Header',<br />
        'sub-nav-header-bottom' =&gt; 'Sub Nav, Bottom of Header',<br />
        'footer-nav' =&gt; 'Footer Menu'<br />
    )<br />
);<br />
```</p>
