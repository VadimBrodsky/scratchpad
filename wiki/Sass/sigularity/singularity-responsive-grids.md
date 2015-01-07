---
tags: #sass #compass #breakpoint #singularity
---

# Responsive Grids

- `add-* (context at breakpoint)`
- `$grids`, `$gutters`, and `$gutter-styles` all have a corresponding add context function.
- This allows Singularity to know what context to use when you call the `GRID-SPAN`.
- Breakpoint is a `min-width` value.

# Example

```sass
$grids: 12;
$gutters: 1/3;

$grids: add-grid(1 4 1 at 700px);
$gutters: add-gutter(1/6 at 700px);

.first {
    @include grid-span(3, 4);
    @include breakpoint(700px) {  
        @inlcude grid-span(1, 1);
    }
}

.main {
    @include grid-span(6, 7);
    @include breakpoint(700px) {
        @include grid-span(1, 2);
    }
}

.second {
    @include grid-span(3, 1);
    @include breakpoint(700px) {
        @inlcude grid-span(1, 3);
    }
}
```