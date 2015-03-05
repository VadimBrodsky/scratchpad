# register_sidebars
- Codex reference -- http://codex.wordpress.org/Function_Reference/register_sidebars
- Creates multiple Sidebars.
- Registers one or more sidebars to be used in the current theme. Most themes have only one sidebar. For this reason, the number parameter is optional and defaults to one.
- The args array parameter can contain a 'name' which will be prepended to the sidebar number if there is more than one sidebar. If no name is specified, 'Sidebar' is used.

```php
<?php register_sidebars( $number, $args ); ?> 
```

```php
<?php $args = array(
    'name'          => sprintf(__('Sidebar %d'), $i ),
    'id'            => "sidebar-$i",
    'description'   => '',
    'class'         => '',
    'before_widget' => '<li id="%1$s" class="widget %2$s">',
    'after_widget'  => '</li>',
    'before_title'  => '<h2 class="widgettitle">',
    'after_title'   => '</h2>' ); 
?>
```