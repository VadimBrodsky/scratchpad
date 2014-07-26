---
layout: post
title: wordpress wp_function php php
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
<p># register_sidebars<br />
- Codex reference -- http://codex.wordpress.org/Function_Reference/register_sidebars<br />
- Creates multiple Sidebars.<br />
- Registers one or more sidebars to be used in the current theme. Most themes have only one sidebar. For this reason, the number parameter is optional and defaults to one.<br />
- The args array parameter can contain a 'name' which will be prepended to the sidebar number if there is more than one sidebar. If no name is specified, 'Sidebar' is used.</p>
<p>```php</p>
<p>```</p>
<p>```php<br />
 sprintf(__('Sidebar %d'), $i ),<br />
	'id'            =&gt; "sidebar-$i",<br />
	'description'   =&gt; '',<br />
	'class'         =&gt; '',<br />
	'before_widget' =&gt; '
<li id="%1$s" class="widget %2$s">',<br />
	'after_widget'  =&gt; '</li>
<p>',<br />
	'before_title'  =&gt; '<br />
<h2 class="widgettitle">',<br />
	'after_title'   =&gt; '</h2>
<p>' );<br />
?&gt;<br />
```</p>
