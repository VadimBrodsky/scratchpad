# the_post
- Codex reference -- http://codex.wordpress.org/Function_Reference/the_post
- Iterate the post index in The Loop. 
- Retrieves the next post, sets up the post, sets the `in the loop` property to `true`.

```php
<?php
while ( have_posts() ) : the_post();
    echo '<h2>';
    the_title();
    echo '</h2>';
    the_content();
endwhile;
?>
```