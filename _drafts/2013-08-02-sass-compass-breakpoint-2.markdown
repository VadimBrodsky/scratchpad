---
layout: post
title: sass compass breakpoint singularity sass
categories: []
tags:
- breakpoint
- compass
- sass
- singularity
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
<p>#sass #compass #breakpoint #singularity</p>
<p># Responsive Grids</p>
<p>- `add-* (context at breakpoint)`<br />
- `$grids`, `$gutters`, and `$gutter-styles` all have a corresponding add context function.<br />
- This allows Singularity to know what context to use when you call the `GRID-SPAN`.<br />
- Breakpoint is a `min-width` value.</p>
<p># Example</p>
<p>```sass<br />
$grids: 12;<br />
$gutters: 1/3;</p>
<p>$grids: add-grid(1 4 1 at 700px);<br />
$gutters: add-gutter(1/6 at 700px);</p>
<p>.first {<br />
    @include grid-span(3, 4);<br />
    @include breakpoint(700px) {<br />
        @inlcude grid-span(1, 1);<br />
    }<br />
}</p>
<p>.main {<br />
    @include grid-span(6, 7);<br />
    @include breakpoint(700px) {<br />
        @include grid-span(1, 2);<br />
    }<br />
}</p>
<p>.second {<br />
    @include grid-span(3, 1);<br />
    @include breakpoint(700px) {<br />
        @inlcude grid-span(1, 3);<br />
    }<br />
}<br />
```</p>
