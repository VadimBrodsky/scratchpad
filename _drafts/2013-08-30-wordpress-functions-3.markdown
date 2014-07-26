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
<p># add_filter<br />
- Allow to modify content before it's output at HTML.<br />
- Add filter function parameters:<br />
    -  What you are filtering (the_hook)<br />
    -  Function that will perform the filtering<br />
    -  The priority<br />
    -  How many parameters to accept<br />
-  Codex reference -- http://codex.wordpress.org/Plugin_API#Create_a_Filter_Function</p>
<p>```php<br />
function theme3_filter_wp_title ($current_title, $sep, $seplocal) {<br />
    // Grab the site name<br />
    $site_name = get_bloginfo('name');</p>
<p>    // Add the site name after the current page title<br />
    $full_title = $site_name . $current_title;</p>
<p>    // If we are on the front_page or homepage append the description<br />
    if ( is_front_page() || is_home() ) {<br />
        // Grab the site description<br />
        $site_desc = get_bloginfo('description');</p>
<p>        // Append site description to title<br />
        $full_title .= ' ' . $sep . ' ' .$site_desc;<br />
    }<br />
    // Return the modified title<br />
    return $full_title;<br />
}</p>
<p>// Hook into 'wp_title'<br />
add_filter('wp_title', 'theme3_filter_wp_title', 10, 3)<br />
```</p>
