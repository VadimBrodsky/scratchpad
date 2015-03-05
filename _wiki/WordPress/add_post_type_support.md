# add_post_type_support
- Codex reference -- http://codex.wordpress.org/Function_Reference/add_post_type_support
- Registers support of certain feature(s) for a given post type. Each feature has a direct impact on the corresponding field displayed in the post edit screen, such as the editor or a meta box. 
- Additionally, the 'revisions' feature dictates whether the post type will store revisions, and the 'comments' feature dictates whether the comments count will show on the post edit screen.

```php
<?php add_post_type_support( $post_type, $supports ) ?>
```

```php
<?php add_post_type_support('page', 'excerpt' ); ?>
```