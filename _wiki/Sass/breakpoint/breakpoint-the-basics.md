# Breakpoint - The Basics

tags: [[Breakpoint|/pages/breakpoint/]]

- Breakpoint is a Media Query Framework
- The basic `min-width` media queries get reduced to a single line.

```sass
$breakpoint-to-ems: true; // converts all pixel values to ems

$nav-inline: 532px;

nav {
    background: #c0ffee;
    @include breakpoint($nav-inline) {
        background: #decaff;
    }
}
```

# Breakpoint - No Query Fallbacks

- Brakpoint provides fallbacks for when media queries aren't available.
- Works with Modernizer by adding class to the unsupported property.

```sass
$breakpoint-no-query-fallbacks: true;
$breakpoint-to-ems: true;

$nav-inline: 532px, 'no-query' '.no-mq';

nav {
    background: #c0ffee;
    @include breakpoint($nav-inline) {
        background: #decaff;
    }
}
```