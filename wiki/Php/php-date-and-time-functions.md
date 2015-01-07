---
tags: #php #basics #functions @getting-good-php
---

# PHP Date and Time Functions

## Parse_date
- Takes a date string and returns an associative array with the details of the date.

```php
print_r(date_parse("2013-08-20 21:33"));
```


## Time
Gives the unix timestamp - number of seconds that have passed since January 1, 1970.

```php
echo time();
```


## Strftime
- Practical date format.
- First parameter - a string with tokens to get the desired time format.
- Second parameter (optional) - time to parse, by default the current time.
- More info on tokens here - http://strfti.me/

```php
echo strftime("%B %d, %Y");
```