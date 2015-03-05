# register_sidebar
- Codex reference -- http://codex.wordpress.org/Function_Reference/register_sidebar
- Builds the definition for a single sidebar and returns the ID. 
- Call on "widgets_init" action.

```php
<?php register_sidebar( $args ); ?> 
```

```php
<?php $args = array(
    'name'          => __( 'Sidebar name', 'theme_text_domain' ),
    'id'            => 'unique-sidebar-id',
    'description'   => '',
    'class'         => '',
    'before_widget' => '<li id="%1$s" class="widget %2$s">',
    'after_widget'  => '</li>',
    'before_title'  => '<h2 class="widgettitle">',
    'after_title'   => '</h2>' ); 
?>
```