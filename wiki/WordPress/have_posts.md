# have_posts
- Codex reference -- http://codex.wordpress.org/Function_Reference/have_posts
- This function checks to see if the current WordPress query has any results to loop over. 
- This is a boolean function, meaning it returns either `TRUE` or `FALSE`.
- As a side effect, `have_posts` starts, steps through, or resets The Loop. 
- At the end of the loop, `have_posts` returns `0`.

```php
<?php
if ( have_posts() ) :
    while ( have_posts() ) : the_post();
        // Your loop code
    endwhile;
else :
    echo wpautop( 'Sorry, no posts were found' );
endif;
?>
```