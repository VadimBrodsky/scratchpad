# the_title_attribute
- Codex reference -- http://codex.wordpress.org/Function_Reference/the_title_attribute
- The title of the current post.
- Usually used in the wordpress loop.
- Returns a clean version of the post title for use in HTML attributes.

```php
<a href="#" title="For More Info on <?php the_title_attribute(); ?>">
    Link
</a>
```