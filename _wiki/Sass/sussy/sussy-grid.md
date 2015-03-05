---
tags: #sass #gird
---

# Sussy Grid

```scss
// require "susy"; // config.rb

@import "susy";

$total-columns: 12;
$column-width: 60px; // rem em %
$gutter-width: 20px; // rem em %
$grid-padding: $gutter-width;

#page {
    @include container;
}

#main {
	@include span-columns(8);

	header {
		@include span-colum(8, 8);
	}

	section {
		@include span-columns(6, 8);
	}

	aside {
		@include span-columns(2 omega, 8);
	}
}

#sidebar {
	@include span-columns(4 omega); // omega - makes items float: right; for last item in a row.
}


@include at-breakpoint (780px 12 920px) {
	#page {
		#main {
			@include span-columns(8,12);
		}
	}
}


@include at-breakpoint (780px 12 920px) {
	@include layout(6) {
		#page {
			//some stuff
		}
	}

	// with-grid-settings(columns, column width, gutter, padding)
	@include with-grid-settings(12, 35px, 15px, 15px) {
		#page {
			@include container;
		}
	}
}

.element {
	@include prefix(2); // padding
	suffix
	pad
	bleed

	@include pre(2); // margin
	post
	squish
	push
	pull
}
```

# Organizing SCSS

```
screen.scss + @import compass
|
|-base
|---layout
|---global
|---reset
|---fonts
|---tabs
|
|-mixins-vars
|---variables
|---mixins
|-outer-modules
|---module
|--etc.
|
|-pages
|---front
|---selection
|---article
|--etc.
|
|-partials
|---header
|---footer
|---blocks
|---etc.

ie.scss

maintenance.scss
```