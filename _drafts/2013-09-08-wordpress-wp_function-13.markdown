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
<p># the_post<br />
- Codex reference -- http://codex.wordpress.org/Function_Reference/the_post<br />
- Iterate the post index in The Loop.<br />
- Retrieves the next post, sets up the post, sets the `in the loop` property to `true`.</p>
<p>```php<br />
&lt;?php<br />
while ( have_posts() ) : the_post();<br />
    echo &#039;<br />
<h2>';<br />
	the_title();<br />
	echo '</h2>
<p>';<br />
	the_content();<br />
endwhile;<br />
?&gt;<br />
```</p>
