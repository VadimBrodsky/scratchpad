# comments_number
- Codex reference -- http://codex.wordpress.org/Function_Reference/comments_number
- Displays the total number of comments, Trackbacks, and Pingbacks for the current post. 
- This tag must be within The Loop.
- Use `get_comments_number()` to retrieve the value.
- To display the number of comments within the parameter string use the '%' character.

```php
<?php comments_number( $zero, $one, $more ); ?>
```