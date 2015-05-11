---
title: "HTML Email Notes" 
layout: post
category: email
date: 2015-05-11 14:29:56 
---

CSS Selectors For Yahoo Mail
============================

Use attribute selectors instead of classes to display correctly in Yahoo. The
`!imporant` will override any inline styles.

```css
@media screen and (max-width: 600px) {
  table[class="responsive-table"] {
    width: 100% !important;
  }
}
```


Meta Tags
=========

General responsive meta tag:

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

Windows phone specific meta tag:

```html
<meta http-equiv="X-UA-Compatible" content="IE-edge" />
```

