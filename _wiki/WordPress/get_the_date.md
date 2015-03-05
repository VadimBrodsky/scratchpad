# get_the_date
- Codex reference -- http://codex.wordpress.org/Function_Reference/get_the_date
- The `get_the_date` template tag retrieves the date the current `$post` was written. 
- Unlike `the_date()` this tag will always return the date.

```php
_e('You are viewing the ' . get_the_date() . ' daily archives');
_e('You are viweing the ' . get_the_date('Y') . 'yearly archives');
_e('You are viewing the "' . single_cat_title('', false ) . '" Archives');
```