---
tags: #sass #compass #singularity #grid
---

# Setting up the Singularity Grid
Use 3 variables to set up a grid:

## $grids

- Grid definition
- Can be single number for symmetric grids
- Or multiple numbers in relation for asymmentric grids
- Each column is considered to have a width of 1


## $gutters

- Gutter definition.
- The width of a single gutter in relation to a column of width of 1.
- Can also be expressed as a single value with unit for fixed-sized gutters.


## $gutter-styles

- Type of gutter.
- Default is full gutter with to the opposite side of a column that is float.
- Can also be split to have half gutter with on each side.
- Or fixed for fixed-sized gutters.


# Example

### Symmetric Grid

```sass
$grids: 12;
$gutters: 0.9375em;
$gutter-style: split;
```

### Asymmetric Grid - Custom

```sass
$grids: 1 4 1;
$gutters: 1/6;
$gutter-style: split;
```

### Asymmetric Grid - Compound

```sass
// Compound function comes from Singularity Extras
$grids: compound(3, 4);
$gutters: 1;
```

### Asymmetric Grid - Ratio Based

```sass
// Ratio function comes from Singularity Extras
$grids: ratio(golden-ratio(), 4);
$gutters: golden-ratio() * 1em;
$gutter-styles: split;
```

### Asymmetric Grid - Spiral Based

```sass
// Ratio function comes from Singularity Extras
$grids: ratio-spiral(5);
$gutters: 1;
```