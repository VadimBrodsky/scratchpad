---
tags: #php #basics #functions @getting-good-php
---

# PHP String / Array Functions

## Explode
- To break up a string.

```php
$str = "This is a string.";
$arr = explode(" ", $str);  // returns array("This", "is", "a", "string");
```

## Implode
- The reverse of `explode`, also known as `join`.

```php
$arr = array("123", "456", "7890");
$phone_number = implode("-", $arr); // returns "123-456-7890"
```