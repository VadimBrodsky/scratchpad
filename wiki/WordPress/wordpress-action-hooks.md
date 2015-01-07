# Wordpress Action Hooks
- Let's developers to do something when it is triggered.
- The most common use of this is to give plugins the ability to output their own links to stylesheets or JavaScript files.

```php
<?php add_action('wp_head', 'your_function'); ?>
```

## Examples of Action Hooks
- [[wp_title]]
- [[wp_head]]