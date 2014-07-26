---
layout: post
title: wordpress theme partial html html html html html html html
categories: []
tags:
- partial
- theme
- wordpress
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
<p>#wordpress #theme #partial</p>
<p># WordPress Header.php</p>
<p>## Doctype<br />
Must include a valid doctype.</p>
<p>```html</p>
<p>```</p>
<p>## HTML Tag<br />
- Wordpress helps us to declare the language settings.<br />
- Uses the `language_attributes` function.<br />
- Codex reference -- http://codex.wordpress.org/Function_Reference/language_attributes</p>
<p>```html<br />
&lt;html &gt;<br />
```</p>
<p>## Title Tag<br />
- Set the title of the page.<br />
- Need to make sure that SEO plugins are able to change the title, with the `wp_title` filer.<br />
- Also passing the separator parameter, in this case `|`<br />
- Need to add a filer to `functions.php` for this to work.<br />
- Codex reference -- http://codex.wordpress.org/Function_Reference/wp_title</p>
<p>```html<br />
<title></p>
<p></title><br />
```</p>
<p>## Meta Tag<br />
- It is hard to build in static meta descriptions.<br />
- Better to rely on SEO plugins for these.<br />
- Can use `blog_info` for the `http-equiv` compliance.</p>
<p>```html<br />
&lt;meta http-equiv=&quot;Content-Type&quot; content=&quot;; charset="&gt;<br />
```</p>
<p>## Stylesheet and Other Template Files<br />
- Need to use a funciton to map the path to these files, cannot rely on absolute or relative paths.</p>
<p>```html<br />
&lt;link rel=&quot;stylesheet&quot; type=&quot;text/css&quot; media=&quot;all&quot; href=&quot;" /&gt;<br />
```</p>
<p>## Action Hook wp_head<br />
- Need to include this at the end of `` to allow for plugin CSS and JavaScript output.</p>
<p>```html</p>
<p>```</p>
<p>## Body Tag<br />
- The last thing in in the `header.php` tag is the body tag,<br />
- Need to add the `body_class` funciton to the `body` tag to have the WordPress generated classes apply to it.</p>
<p>```html<br />
&lt;body  &gt;<br />
```</p>
