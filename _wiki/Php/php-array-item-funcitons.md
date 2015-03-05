---
tags: #php #basics #functions @getting-good-php
---

# PHP Array-Item Funcitons

## Array_map
- To map an array with another array.
- Pass a name of a function to operate on each item in an array, via a stringin the first parameter.

```php
$starks = array("Rob", "Brandon", "Riccon");
$F = array_map("strtoupper", $starks);
```


## Array_walk
- Similar to `arra_map`, but it does not returns an array but rather a `true` or `false`.
- The funciton name is passed as the second parameter.

```php
function greet ($name) {
    echo "Hello, $name n";
}
$starks = array("Rob", "Brandon", "Riccon");
array_walk($starks, "greet");
```


## Array_search
- To search within arrays.
- First parameter is the value to search for, second for the array to search within.

```php
$starks = array("Rob", "Brandon", "Riccon");
echo array_search("Brandon", $starks);  // 1
```


## In_array
- Find whether an item is within an array.
- Returns either `true` or `false`.

```php
$starks = array("Rob", "Brandon", "Riccon");
var_dump(in_array("Brandon", $starks));
```


## Array_slice
- To slice a part of an array.
- First parameter - array.
- Second parameter - offset (index to begin the slice from, if the number is negative it will be counted from the end of the array).
- Third parameter - length of the slice.

```php
$starks = array("Rob", "Brandon", "Riccon");
print_r(array_slice($starks, 1, 1));    // Brandon
print_r(array_slice($starks, 1, 2));    // Brandon, Riccon
```


## Array_splice
- Similar to the `array_slice` function, but will insert new values or array into the cutout place.
- Fourth parameter - either a single value or an array of values that will replace the values that are being sliced out.
- The changes are made to the original array.

```php
$starks = array("Rob", "Brandon", "Riccon");
array_splice($starks, 0, 2, "John");
```