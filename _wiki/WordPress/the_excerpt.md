# the_excerpt
- Codex reference -- http://codex.wordpress.org/Function_Reference/the_excerpt
- Displays the excerpt of the current post with the "[...]" text at the end, which is not a "read more" link. 
- Used to directly display the excerpt, but it adds opening and closing `<p>` tags to the string returned by get_the_excerpt(). 
- If you do not provide an explicit excerpt to a post (in the post editor's optional excerpt field), it will display an automatic excerpt which refers to the first 55 words of the post's content. 
- Also in the latter case, HTML tags and graphics are stripped from the excerpt's content. This template tag must be within The Loop.

```php
<?php the_excerpt(); ?> 
```