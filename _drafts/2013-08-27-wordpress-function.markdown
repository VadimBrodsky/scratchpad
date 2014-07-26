---
layout: post
title: wordpress wp_function php html
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
<p># blog_info<br />
- Codex reference -- http://codex.wordpress.org/Function_Reference/bloginfo<br />
- Used to echo the title or other information about the blog.<br />
- To use the values in the code use `get_bloginfo()`</p>
<p>```php<br />
// head<br />
<title></p>
<p></title><br />
&lt;link rel=&quot;stylesheet&quot; type=&quot;text/css&quot; href=&quot;" &gt;</p>
<p>// body</p>
<h1>
     |<br />
</h1>
<p>```</p>
<p># For use in the meta tag<br />
- For HTML5 compliance, need to include one of the following:<br />
    - ``<br />
    - ``<br />
- The `blog_info` function works well for this.</p>
<p>```html<br />
 &lt;meta http-equiv=&quot;Content-Type&quot; content=&quot;;<br />
    "&gt;<br />
```</p>
