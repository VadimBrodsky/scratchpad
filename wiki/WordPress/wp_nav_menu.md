# wp_nav_menu
- Codex reference -- http://codex.wordpress.org/Function_Reference/wp_nav_menu
- Need to be enabled in `functions.php` first.
- Displayes the WordPress menu.

## Basic Usage
```html
<nav>
    <ul>
        <?php wp_nav_menu(array('menu' => 'All Pages')); ?>
    </ul>
</nav> 
```

## Default Values
```php
<?php
$defaults = array(
    'theme_location'  => '',
    'menu'            => '',
    'container'       => 'div',
    'container_class' => '',
    'container_id'    => '',
    'menu_class'      => 'menu',
    'menu_id'         => '',
    'echo'            => true,
    'fallback_cb'     => 'wp_page_menu',
    'before'          => '',
    'after'           => '',
    'link_before'     => '',
    'link_after'      => '',
    'items_wrap'      => '<ul id="%1$s" class="%2$s">%3$s</ul>',
    'depth'           => 0,
    'walker'          => ''
);
wp_nav_menu( $defaults );
?>
```