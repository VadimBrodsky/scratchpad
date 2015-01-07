# get_option
- http://codex.wordpress.org/Function_Reference/get_option
- A safe way of getting values for a named option from the options database table. 
- If the desired option does not exist, or no value is associated with it, `FALSE` will be returned.

```php
<?php echo get_option( $option, $default ); ?> 
```

```php
get_option('default_category');
```