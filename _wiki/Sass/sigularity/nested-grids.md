---
tags: #sass #compass #singularity #breakpoint
---

# Nested Grids

- `layout($grid, $gutter)`
- The layout mixin allows you to selectively override the global context.
- Each of the global context variables can be overriden individually.
- If they aren't the global one will be used.

# Example

## HTML Markup

```html
    <div class="main">
		<div class="one">One</div>
		<div class="two">Two</div>
		<div class="three">
			<div class="a">Three A</div>
			<div class="b">Three B</div>
			<div class="c">Three C</div>
		</div>
		<div class="four">Four</div>
	</div>
	<div class="first">First Section</div>
	<div class="second">Second Section</div>
```

## Sass

```sass
$grids: 1 4 1;
@gutters 1/6;

.first { @include grid-span(1, 1); }
.main { @include grid-span(1, 2); }
.second { @include grid-span(1, 3); }

@include layout(8, 1/12) {
    .one { @include grid-span(1, 1);
    .two { @include grid-span(1, 8);
    .three { @include grid-span(6, 2);
    .four {
        @include grid-span(2, 4)
        clear: both;
    }
}

@include layout(6, 1/12) {
    .a { @include grid-span(2, 3);
    .b { @include grid-span(2, 5);
    .c { @include grid-span(2, 1);
}
```