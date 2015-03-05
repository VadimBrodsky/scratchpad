# get_template_directory_uri
- Codex reference -- http://codex.wordpress.org/Function_Reference/get_template_directory_uri
- Retrieve template directory URI for the current theme. Checks for SSL.
- Note: Does not return a trailing slash following the directory address.
- In the event a child theme is being used, the parent theme directory URI will be returned.
- `get_template_directory_uri` should be used for resources that are not intended to be included in/over-ridden by a child theme. 
- Use `get_stylesheet_directory_uri` to include resources that are intended to be included in/over-ridden by the Child Theme.

```html
<script src="<?php echo get_template_directory_uri(); ?>/scripts/functions.js" type="text/javascript"></script>
```