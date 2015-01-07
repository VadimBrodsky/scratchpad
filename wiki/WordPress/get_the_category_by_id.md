# get_the_category_by_id
- Codex reference -- http://codex.wordpress.org/Function_Reference/get_the_category_by_ID
- Retrieve category name based on category ID.
- Can use other functions to retreive the category id.

```php
<?php get_the_category_by_id( $cat_ID ); ?>
```

```php
<?php echo get_the_category_by_id( get_option('default_category') ); ?>
```