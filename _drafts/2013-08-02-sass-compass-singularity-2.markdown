---
layout: post
title: sass compass singularity breakpoint html sass
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
<p>#sass #compass #singularity #breakpoint</p>
<p># Nested Grids</p>
<p>- `layout($grid, $gutter)`<br />
- The layout mixin allows you to selectively override the global context.<br />
- Each of the global context variables can be overriden individually.<br />
- If they aren't the global one will be used.</p>
<p># Example</p>
<p>## HTML Markup</p>
<p>```html</p>
<div class="main">
<div class="one">One</div>
<div class="two">Two</div>
<div class="three">
<div class="a">Three A</div>
<div class="b">Three B</div>
<div class="c">Three C</div>
</p></div>
<div class="four">Four</div>
</p></div>
<div class="first">First Section</div>
<div class="second">Second Section</div>
<p>```</p>
<p>## Sass</p>
<p>```sass<br />
$grids: 1 4 1;<br />
@gutters 1/6;</p>
<p>.first { @include grid-span(1, 1); }<br />
.main { @include grid-span(1, 2); }<br />
.second { @include grid-span(1, 3); }</p>
<p>@include layout(8, 1/12) {<br />
    .one { @include grid-span(1, 1);<br />
    .two { @include grid-span(1, 8);<br />
    .three { @include grid-span(6, 2);<br />
    .four {<br />
        @include grid-span(2, 4)<br />
        clear: both;<br />
    }<br />
}</p>
<p>@include layout(6, 1/12) {<br />
    .a { @include grid-span(2, 3);<br />
    .b { @include grid-span(2, 5);<br />
    .c { @include grid-span(2, 1);<br />
}</p>
<p>```</p>
