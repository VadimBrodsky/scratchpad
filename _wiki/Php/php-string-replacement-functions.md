---
tags: #php #basics #functions @getting-good-php
---

# PHP String Replacement Functions

## Str_replace
- Replaces sectionsof strings.
- Accepts 3 parameters: string to search, string to replace it with, and a string to do the searching and replacing on.
- Returns a modified string.
- Works like `str_replace` only it is case insensitive.

```php
$str = "This is the original string";
echo str_replace("original", "modified", $str);  // returns "This is the modified string"
```

## Strlen
Returns the number of characters in the string.

```php
echo strlen("Getting Good with PHP");   // returns 21
```

## Strpos
- To find a string within a string.
- It takes two parameters, the orignal string and the substring to search for.
- Returns the number indicating the position within the original string where the substring begins.
- This function accepts a third parameter, to start searching from a specific point.

```php
echo strpos("This is the haystack string", "haystack"); // returns 12
echo strpos("This is the haystack string", "t", 11);
```