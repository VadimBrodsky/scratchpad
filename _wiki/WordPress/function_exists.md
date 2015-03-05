# function_exists
- PHP Documentation reference -- http://php.net/manual/en/function.function-exists.php
- Checks the list of defined functions, both built-in (internal) and user-defined, for `function_name`.
- Useful to check if the plugin function is present in WordPress

```php
bool function_exists ( string $function_name );
```

```php
<?php if(function_exists('bcn_display_list')) {
        bcn_display_list();
    }
?>
```