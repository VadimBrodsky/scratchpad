---
tags: #php #basics #functions @getting-good-php
---

# PHP Array Functions

## Array_push
- To add one or more items to the end of the array.
- Modifies the array that is being passed.

```php
$starks = array("Rob", "John", "Brandon", "Riccon");
array_push($starks, "Ariya");
```


## Array_pop
Opposite of `array_push`, it pulls the last item off of the array and returns it.

```php
$starks = array("Rob", "Brandon", "Riccon");
array_pop($starks);
```


## Array_unshift
Add an item to the beginning of an array.


```php
$starks = array("Rob", "Brandon", "Riccon");
array_unshift($starks, "John", "Sansa", "Arya");
```


## Array_shift
Pulls the first item off an array and returns it.

```php
$starks = array("Rob", "Brandon", "Riccon");
array_pop($starks);
```