---
tags: #php #basics #functions @getting-good-php
---

# PHP Array Sorting Functions

## Asort
- Sorts an array by value - alphabetically.
- The indecies are kept with their appropirate values.
- Works on both associative and numeric arrays.

```php
$stark = array("name" => "Rob", "Father" => "Eddard", "Mother" => "Kathryn");
asort($stark);
```


## Arsort
Just like `asort` just sorts reverse-alphabetically.


## Count
Counts the number of items in the array.

```php
$starks = array("Rob", "Brandon", "Riccon");
count($starks); // 3
```


## Array_sum
To sum up all of the items in an array.

```php
$arr = array(0,1,2,3,4,5,6,7,8,9,10);
echo array_sum($arr);   // 55
```