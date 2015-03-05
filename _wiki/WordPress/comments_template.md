# comments_template
- Codex reference -- http://codex.wordpress.org/Function_Reference/comments_template
- Displays all of the approved comments on the current post.
- Includes the comments form.
- WordPress validates the comments data.
- Loads the comment template - comments.php file. 
- For use in single Post and Page displays. 
- Will not work outside of single displays unless $withcomments is set to "1".

```php
<?php comments_template( $file, $separate_comments ); ?
```