---
tags: #php #php_function
---

# _POST
- PHP reference -- http://php.net/manual/en/reserved.variables.post.php
- An associative array of variables passed to the current script via the HTTP POST method.

```php
echo 'Hello ' . htmlspecialchars($_POST["name"]) . '!';
```