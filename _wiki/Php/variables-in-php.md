---
tags: #php #basics @getting-good-php
---

# Variables in PHP

- Begins with a dollar sign `$`
- Can be followed by any number of letters, numbers or underscores
- The first character afer the dollar sign cannot be a number
- PHP developers usually separate vairiable terms with underscores in the name.

```php
$variable = "<p>Something goes here</p>";
```

# Data types in PHP

## Strings

- Any set of characters between two quotes.
- Can be delimetred with double or single quotes - `"a" or 'b'`
- To escape the quote sign use the backslash - `'`
- `"this is a string"`
- `'That'll do it.'`

Double quotes allow for interpolation:

```php
$name = "Newton";
echo "Hello, $name.";
```

## Numbers

- PHP has only two types of numbers - integers and floats.
- The only non-number characters that are allowed are decimals, minus and scientific notation.

```php
1002.1223
-232
1.34e5
```


## Booleans

- Has only two values: `true` or `false`
- They are not case sensitive

```php
$life = true;
$death = false;
```

## Null

- The data type that represents nothing - the valueless value.
- For exaple when you create an uninitialized value.

```php
$hello;
echo $hello; // will be Null
```

## Array

- A list of variables.
- To setup, use the keyword `array(item1, item2, itenm)`
- In PHP arrays can be both numeric (with index) and associative (with key value pair).
- The `=>` is called `T_DOUBLE_ARROW`
- Arrays in PHP are not limited to one data type per array.

```php
$this_is_a_numeric_array = array("HTML", "CSS", "JavaScript", "PHP");
echo $this_is_a_numeric_array[0];

$this_is_an_associative_array = array (
    "name" => "Eddard Stark",
    "birtplacee" => "Winterfell",
    "married" => true,
    "allies" => array("Karstarks", "Tullies", "Mormonts")
);
echo $this_is_an_associative_array["name"];
```