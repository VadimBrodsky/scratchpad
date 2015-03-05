# WordPress Functions.php
- Must reside in the same directory as the `index.php` and `style.css`
- Turns on and off certain WordPress functionality for the theme.
- First line is always `<?php` but no need in closing it at the end.

## Add Menus
```php
<?php register_nav_menus(); ?>
```