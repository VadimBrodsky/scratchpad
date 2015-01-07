---
tags: #compass #sass #singularity #ie8up
---

# Applying Border-Box Box Model

- Works in IE8 and up.

```sass
// we can import all of compass safely because it doesn't write any css.
@import 'compass';

// we switch our box model to Boder Box.
// From Paul Irish
*, *:before, *:after {
    @include box-sizing('border-box');
}
```

```css
/* http://www.paulirish.com/2012/box-sizing-border-box-ftw */
/* apply a natural box layout model to all elements */
*, *:before, *:after {
  -moz-box-sizing: border-box; 
  -webkit-box-sizing: border-box; 
  box-sizing: border-box;
 }
```