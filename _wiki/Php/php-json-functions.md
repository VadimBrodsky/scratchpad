---
tags: #php #basics #functions @getting-good-php
---

# PHP JSON Functions
- Way to pass data to and from JavaScript with Ajax.
- JASON - JavaScript objects, similar to PHP associative arrays.


## json_encode
Convert an associative array to JSON.

```php
$houses = array("name" => "Stark", "sigil" => "Direwolf", "motto" => "Winter is Coming");
print_r(json_encode($houses));
```

## json_decode
- Convert JSON to a PHP object.
- First parameter - JSON string.
- Second parameter - `true` to get an associative array instead of an object.

```php
$decoded = json_decode('{"name":"Stark","sigil":"Direwolf","motto":"Winter is Coming"}', true);
```