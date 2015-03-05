# add_theme_support
- Codex reference -- http://codex.wordpress.org/Function_Reference/add_theme_support
- Allows a theme or plugin to register support of a certain theme feature. 
- If called from a theme, it should be done in the theme's `functions.php` file to work. 
- It can also be called from a plugin if attached to an action hook.

```php
add_theme_support('post-thumbnails');
```