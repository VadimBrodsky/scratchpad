# get_avatar
- Codex reference -- http://codex.wordpress.org/Function_Reference/get_avatar
- Retrieve the avatar for a user who provided a user ID or email address. 
- Most commonly used in the comments section.
- This function is [pluggable](http://codex.wordpress.org/Pluggable_Functions), however plugin authors wishing to change the gravatar output should use the get_avatar filter instead, for compatibility purposes.
- This function will not return an avatar if "Show Avatars" is unchecked in Settings > Discussion.

```php
<?php echo get_avatar( $id_or_email, $size, $default, $alt ); ?>
```

```php
<?php $author_alt =  'Avatar of ' . get_the_author_meta('first_name')  . ' ' . get_the_author_meta('last_name'); ?>
<?php echo get_avatar( get_the_author_meta( 'email' ), '100', 'Mystery Man', $author_alt); ?>
```