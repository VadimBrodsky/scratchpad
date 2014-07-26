---
layout: post
title: include sass compass singularity grid html sass
categories: []
tags:
- compass
- grid
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
<p>#sass #compass #singularity #grid</p>
<p># Spanning the Singularity Grid</p>
<p>Singularity is a semantic CSS based grid, everything is controlled by the CSS.</p>
<p>## Grid-Span Mixin</p>
<p>`@include grid-span($span, $location);`</p>
<p>- Mixin for "attaching" a selection to columns on the current grid.<br />
- Two required arguments are:<br />
  - `$span`, how many columns you'd like to span.<br />
  - `$location`, what column you'd like to start from. </p>
<p># Example</p>
<p>## HTML Structure</p>
<p>```html</p>
<div class="main">Main Section</div>
<div class="first">First Section</div>
<div class="second">Second Section</div>
<p>```</p>
<p>## Sass</p>
<p>```sass<br />
$grids: 1 4 1;<br />
$gutters: 1/6;</p>
<p>.first { @include grid-span(1, 1); }<br />
.main { @include grid-span(1, 2); }<br />
.second { @include grid-span(1, 3);}<br />
```</p>
