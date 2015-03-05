# the_author_meta
- Codex reference -- http://codex.wordpress.org/Function_Reference/the_author_meta
- The the_author_meta Template Tag displays the desired meta data for a user. 
- If this tag is used within The Loop, the user ID value need not be specified, and the displayed data is that of the current post author. 
- A user ID can be specified if this tag is used outside The Loop.
- If the meta field does not exist, nothing is printed.
- NOTE: Use `get_the_author_meta` if you need to return (not display) the information.

```php
<?php the_author_meta( $field, $userID ); ?> 
```

```php
<?php if(get_the_author_meta('user_url')) { ?>
    <a href="<?php the_author_meta('user_url'); ?>" title="<?php the_author_meta('first_name'); ?>'s Website" target="_blank">
        <?php the_author_meta('user_url'); ?>
    </a>
<?php } ?>
```