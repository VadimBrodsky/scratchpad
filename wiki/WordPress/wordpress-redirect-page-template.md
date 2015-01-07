---
tags: #php #WordPress 
---

# WordPress Redirect Page Template

```php
<?php
/*
Template Name: Chamber Page Redirect
*/
?>
<?php 
    header("HTTP/1.1 301 Moved Permanently");
	header('Location: http://paulpuncher.com/');
?>
```