---
tags: #sass
---

# Functions in Sass

Function example:
```sass
@function bb-opos( $bb-flow ) {
    @if $bb-flow == right {
        @return left;
    }
    @else {
        @return right;
    }
}
```

## The return directive

- `@return`
- The result or the answer of a function
- There can be only one return


## Using the result of a funciton

With a variable:

```sass
$bb-flow: left !default;
$bb-opos: bb-opos($bb-flow);
```

With a property:

```sass
float: #($bb-opos);
```