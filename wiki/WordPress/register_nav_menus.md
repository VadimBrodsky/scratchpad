# register_nav_menus
- Codex reference -- http://codex.wordpress.org/Function_Reference/register_nav_menus
- Registers multiple custom navigation menus.
- To be used in the `funcitons.php` file.

```php
register_nav_menus(
    array(
        'main-nav-header-top' => 'Main Nav, Top of Header',
        'sub-nav-header-bottom' => 'Sub Nav, Bottom of Header',
        'footer-nav' => 'Footer Menu'
    )
);
```