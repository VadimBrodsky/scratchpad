---
tags: #sass #compass #singularity #grid
---

# Spanning the Singularity Grid

Singularity is a semantic CSS based grid, everything is controlled by the CSS.

## Grid-Span Mixin

`@include grid-span($span, $location);`

- Mixin for "attaching" a selection to columns on the current grid.
- Two required arguments are:
  - `$span`, how many columns you'd like to span.
  - `$location`, what column you'd like to start from. 

# Example

## HTML Structure

```html

    <div class="main">Main Section</div>
    <div class="first">First Section</div>
    <div class="second">Second Section</div>

```

## Sass

```sass
$grids: 1 4 1;
$gutters: 1/6;

.first { @include grid-span(1, 1); }
.main { @include grid-span(1, 2); }
.second { @include grid-span(1, 3);}
```