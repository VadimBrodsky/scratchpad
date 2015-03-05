---
tags: #php #basics @getting-good-php
---

# Operators in PHP

## Arithmetic Operators

```php
$num = 10;
$num = $num + 10;   // Addition
$num = $num - 5;    // Subtraction 
$num = $num / 2;    // Division
$num = $num * 0.2;  // Multiplication
$num = $num % 3;    // Modulus
```


## String Operators

The only string operator is concatination.

```php
"first string" . "second string";
```


## Assignment Operators

```php
$num = 10;
$num += 10;   // Addition
$num -= 5;    // Subtraction 
$num /= 2;    // Division
$num */ 0.2;  // Multiplication
$num %/ 3;    // Modulus
```

## Inrementing and Decrementing Operators

- Post-increment will perform the incrementing after it return the value.
- Pre-increment will increment the value first then return it.

```php
$num++; // Post increment
$num--; // post decrement
++$num; // Pre increment
--$num; // Pre decrement
```


## Comparison Operators

- Equal operator `==` will try to interpret and convert values into matching data types before comparison.
- Identity oprtator `===` does not try to interpret and convert values into matching data types.
- Not operator `!=` and `!==` opposite of equal and identical operator.
- Greater / less than and equals `> =  10; // false
4 <= 4 // true;
```


## Logical Operators

- Most of the values in PHP can be interpreted as being true or false.
- Most values are true.
- These are the false values
  - `""`
  - `0`
  - `false`
  - `null`
  - `array()`


```php
$truth = true;
$lie === !$truth;
```

```php
$bacon; $eggs;
$meal === $bacon && $eggs;
```

```php
$this; $that;
$either === $this || $that;
```

```php
// Conditional operator
// conditional ? if_true : if_false
$raining = $weather ? "Take umbrella" : "Wear Shorts";
```