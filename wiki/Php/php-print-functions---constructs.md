---
tags: #php #basics @getting-good-php
---

# 


## Echo
- `echo` is not a function but a language construct.
- Multiple strings can be concatinated as they are outputted.

## Print
- `print` is also a language construct, like `echo` but takes a single string.

## Print_r
- Print readable, useful for outputting things like arrays and objects.
- To keep the whitespace, use in conjunciton with `<pre>`.
- Cannot output booleans.

```php
$person = array("name" => "Sherlock Holmes", "job" => "detective");
echo "<pre>";
print_r($person);
echo "</pre>";
```

## Var_dump
Outputs the contents of variables, similar to `print_r` but it can output Booleans.

```php
$a = true;
var_dump($a);   // bool(true)
```