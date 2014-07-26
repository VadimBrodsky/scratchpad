---
layout: post
title: sass compass singularity grid sass sass sass sass sass
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
<p># Setting up the Singularity Grid<br />
Use 3 variables to set up a grid:</p>
<p>## $grids</p>
<p>- Grid definition<br />
- Can be single number for symmetric grids<br />
- Or multiple numbers in relation for asymmentric grids<br />
- Each column is considered to have a width of 1</p>
<p>## $gutters</p>
<p>- Gutter definition.<br />
- The width of a single gutter in relation to a column of width of 1.<br />
- Can also be expressed as a single value with unit for fixed-sized gutters.</p>
<p>## $gutter-styles</p>
<p>- Type of gutter.<br />
- Default is full gutter with to the opposite side of a column that is float.<br />
- Can also be split to have half gutter with on each side.<br />
- Or fixed for fixed-sized gutters.</p>
<p># Example</p>
<p>### Symmetric Grid</p>
<p>```sass<br />
$grids: 12;<br />
$gutters: 0.9375em;<br />
$gutter-style: split;<br />
```</p>
<p>### Asymmetric Grid - Custom</p>
<p>```sass<br />
$grids: 1 4 1;<br />
$gutters: 1/6;<br />
$gutter-style: split;<br />
```</p>
<p>### Asymmetric Grid - Compound</p>
<p>```sass<br />
// Compound function comes from Singularity Extras<br />
$grids: compound(3, 4);<br />
$gutters: 1;<br />
```</p>
<p>### Asymmetric Grid - Ratio Based</p>
<p>```sass<br />
// Ratio function comes from Singularity Extras<br />
$grids: ratio(golden-ratio(), 4);<br />
$gutters: golden-ratio() * 1em;<br />
$gutter-styles: split;<br />
```</p>
<p>### Asymmetric Grid - Spiral Based</p>
<p>```sass<br />
// Ratio function comes from Singularity Extras<br />
$grids: ratio-spiral(5);<br />
$gutters: 1;<br />
```</p>
