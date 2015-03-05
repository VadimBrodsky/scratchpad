---
tags: #php @getting-good-php #basics
---

# Partials in PHP

- `include` - if the file cannot be found, displays a warning but will execute.
- `require` - if the file cannot be found, displays a fatal error and will stop execution.
- `include_once` - just like include, but if the file was already included it will not include it again.
- `require_once` - just like require, but if the file was already included it wlll not include it again.

```php
include partials/great_houses.php;
require ("houses.php");
require_once("partials/dothraki.php");
```