# the_post_thumbnail
- Codex reference -- https://codex.wordpress.org/Function_Reference/the_post_thumbnail
- Display the Featured Image (previously called Post Thumbnails) for the current post, as set in that post's edit screen.
- This tag must be used within The Loop. Use `get_the_post_thumbnail($id, $size, $attr )` instead to get the featured image for any post.
- To enable post thumbnails, the current theme must include `add_theme_support( 'post-thumbnails' );` in its `functions.php` file. See also Post Thumbnails.

```php
<?php the_post_thumbnail( $size, $attr ); ?>
```