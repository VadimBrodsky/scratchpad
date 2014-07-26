---
layout: post
title: sass compass breakpoint sass sass
categories: []
tags:
- breakpoint
- compass
- sass
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
<p>#sass #compass #breakpoint</p>
<p># Breakpoint - The Basics</p>
<p>- Breakpoint is a Media Query Framework<br />
- The basic `min-width` media queries get reduced to a single line.</p>
<p>```sass<br />
$breakpoint-to-ems: true; // converts all pixel values to ems</p>
<p>$nav-inline: 532px;</p>
<p>nav {<br />
    background: #c0ffee;<br />
    @include breakpoint($nav-inline) {<br />
        background: #decaff;<br />
    }<br />
}<br />
```</p>
<p># Breakpoint - No Query Fallbacks</p>
<p>- Brakpoint provides fallbacks for when media queries aren't available.<br />
- Works with Modernizer by adding class to the unsupported property.</p>
<p>```sass<br />
$breakpoint-no-query-fallbacks: true;<br />
$breakpoint-to-ems: true;</p>
<p>$nav-inline: 532px, 'no-query' '.no-mq';</p>
<p>nav {<br />
    background: #c0ffee;<br />
    @include breakpoint($nav-inline) {<br />
        background: #decaff;<br />
    }<br />
}<br />
```</p>
