---
tags: #php #php_function
---

# _GET
- PHP reference -- http://php.net/manual/en/reserved.variables.get.php
- An associative array of variables passed to the current script via the URL parameters.

```php
echo 'Hello ' . htmlspecialchars($_GET["name"]) . '!';
```