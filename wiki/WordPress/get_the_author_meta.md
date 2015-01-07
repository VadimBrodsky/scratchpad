# get_the_author_meta
- Codex reference -- http://codex.wordpress.org/Function_Reference/get_the_author_meta
- This function returns the desired meta data for a user. 
- If used within The Loop, the user ID need not be specified, and the displayed data is that of the current post author. 
- A user ID must be specified if used outside The Loop.
- `get_the_author_meta()` returns the data for use in PHP. 
- To display the information instead, [use the_author_meta](http://codex.wordpress.org/Function_Reference/the_author_meta)
- If the specified meta field does not exist for this user, the empty string is returned.

```php
<?php the_author_meta( $field, $userID ); ?>
```

```php
<?php $author_alt =  'Avatar of ' . get_the_author_meta('first_name')  . ' ' . get_the_author_meta('last_name'); ?>
<?php echo get_avatar( get_the_author_meta( 'email' ), '100', 'Mystery Man', $author_alt); ?>
```