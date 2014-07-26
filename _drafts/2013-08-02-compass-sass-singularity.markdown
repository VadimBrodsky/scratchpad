---
layout: post
title: compass sass singularity ie8up sass css
categories: []
tags:
- compass
- ie8up
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
<p>#compass #sass #singularity #ie8up</p>
<p># Applying Border-Box Box Model</p>
<p>- Works in IE8 and up.</p>
<p>```sass<br />
// we can import all of compass safely because it doesn't write any css.<br />
@import 'compass';</p>
<p>// we switch our box model to Boder Box.<br />
// From Paul Irish<br />
*, *:before, *:after {<br />
    @include box-sizing('border-box');<br />
}<br />
```</p>
<p>```css<br />
/* http://www.paulirish.com/2012/box-sizing-border-box-ftw */<br />
/* apply a natural box layout model to all elements */<br />
*, *:before, *:after {<br />
  -moz-box-sizing: border-box;<br />
  -webkit-box-sizing: border-box;<br />
  box-sizing: border-box;<br />
 }<br />
```</p>
