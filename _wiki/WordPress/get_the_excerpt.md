# get_the_excerpt
- Codex reference -- http://codex.wordpress.org/Function_Reference/get_the_excerpt
- Returns the excerpt of the current post with the "[...]" text at the end, which is not a "read more" link. 
- This template tag must be used within The Loop. 
- Alternatively, `the_excerpt()` can be used to directly display the excerpt, but it also adds opening and closing `<p>` tags to the string returned by `get_the_excerpt()`.
- If the post does not have an excerpt, this function applies `wp_trim_excerpt` to the post content and returns that generated string with "[...]" at the end. `wp_trim_excerpt` is applied via the `get_the_excerpt` filter and can be removed.


```php
<?php $excerpt = get_the_excerpt( $deprecated ) ?>
```

```php
<?php if(get_the_excerpt()) { ?>
    <p class="lead"><?php echo get_the_excerpt(); ?></p>
<?php } ?>
```