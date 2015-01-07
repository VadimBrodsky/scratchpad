# the_content
- Codex reference -- http://codex.wordpress.org/Function_Reference/the_content
- Displays the contents of the current post. 
- This template tag must be within The_Loop.
- If the quicktag `<!--more-->` is used in a post to designate the "cut-off" point for the post to be excerpted, `the_content()` tag will only show the excerpt up to the `<!--more-->` quicktag point on non-single/non-permalink post pages. 
- By design, `the_content()` tag includes a parameter for formatting the `<!--more-->` content and look, which creates a link to "continue reading" the full post.

```php
<?php the_content( $more_link_text, $stripteaser ); ?>
```

```php
<article>
    <?php the_content(); ?>
</article>
```