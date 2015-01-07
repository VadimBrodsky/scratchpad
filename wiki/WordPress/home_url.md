# home_url
- Codex reference -- http://codex.wordpress.org/Function_Reference/home_url
- The home_url template tag retrieves the home URL for the current site, optionally with the $path argument appended. 
- The function determines the appropriate protocol, "https" if is_ssl() and "http" otherwise. If the $scheme argument is "http" or "https" the is_ssl() check is overridden.
- In case of WordPress Network Setup, use network_home_url() instead.

```php
<?php home_url( $path, $scheme ); ?>
```

```php
<?php echo home_url(); ?>
```