# blog_info
- Codex reference -- http://codex.wordpress.org/Function_Reference/bloginfo
- Used to echo the title or other information about the blog.
- To use the values in the code use `get_bloginfo()`

```php
// head
<title>
    <?php bloginfo('name'); ?>
</title>
<link rel="stylesheet" type="text/css" href="<?php bloginfo('stylesheet_url') ?>" >
// body
<h1>
    <?php bloginfo('name');?> | <?php bloginfo('description');?>
</h1>
```

# For use in the meta tag
- For HTML5 compliance, need to include one of the following:
    - `<meta charset='utf-8'>`
    - `<meta http-equiv='Content-Type' content='text/html; charset=utf-8'>`
- The `blog_info` function works well for this.

```html
<meta http-equiv="Content-Type" content="<?php bloginfo('html_type'); ?>;
    <?php bloginfo('charset'); ?>">
```