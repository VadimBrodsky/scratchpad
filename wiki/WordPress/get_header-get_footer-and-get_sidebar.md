# get_header, get_footer and get_sidebar
- Codex reference -- http://codex.wordpress.org/Function_Reference/get_header
- Codex reference -- http://codex.wordpress.org/Function_Reference/get_footer
- Codex reference -- http://codex.wordpress.org/Function_Reference/get_sidebar
- Includes the `header.php` or `footer.php` template file from your current theme's directory. 
- If a name is specified then a specialised footer `footer-{name}.php` will be included.
- If the theme contains no `footer.php` file then the footer from the default theme `wp-includes/theme-compat/footer.php` will be included.

```php
<?php get_header(); ?>
```

```php
<?php get_sidebar(); ?>
```

```php
<?php get_footer(); ?>
```