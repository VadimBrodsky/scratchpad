# dynamic_sidebar
- Codex reference -- http://codex.wordpress.org/Function_Reference/dynamic_sidebar
- This function calls each of the active widget callbacks in order, which prints the markup for the sidebar. 
- If you have more than one sidebar, you should give this function the name or number of the sidebar you want to print. 
- This function returns true on success and false on failure.
- The return value should be used to determine whether to display a static sidebar. This ensures that your theme will look good even when the Widgets plug-in is not active.

```php
<?php dynamic_sidebar( $index ); ?>
```

```php
<ul id="sidebar">
<?php if ( ! dynamic_sidebar() ) : ?>
    <li>{static sidebar item 1}</li>
    <li>{static sidebar item 2}</li>
<?php endif; ?>
</ul>
```