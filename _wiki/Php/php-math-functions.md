---
tags: #php #basics #functions @getting-good-php
---

# PHP Math Functions

## max / min
- Find the higherst or the lower number.
- Can pass an array instead of individual parameters.

```php
echo max(12, 9, 4, 16, 2, 3.14);    // 16
echo min(array(12, 9, 4, 16, 2, 3));    //2
```


## mt_rand
- Random number generator.
- The two parameters are optional, represent the min and max range.
- Uses the Mersenne Twister algorithm to generate a random number, it is faster than `rand`.

```php
echo mt_rand();
echo mt_rant(0,100);
```

## round / ceil / floor
- To round numbers.
- `round` - mathematical.
- `ceil` - up.
- `floor` - down.
- Second parameter determines the number of digits to keep.

```php
echo round(7.5);
echo round(3.14159, 2);
echo ceil(2.1);
echo floor(4.9);
```