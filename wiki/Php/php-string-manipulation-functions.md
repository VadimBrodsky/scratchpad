---
tags: #php #basics #functions @getting-good-php
---

# PHP String Manipulation Functions

## Lcfirst
Changes the first letter of a string to lowercase.

```php
lcfirst("Vadim") === "vadim";
```

## Ucfirst
Changes the first letter of a string to uppercase.

```php
ucfirst("vadim") === "Vadim";
```

## Ucwords
Changes the first letter of evey word in the string to uppercase.

```php
ucwords("getting good with PHP") === "Getting Good With PHP";
```

## Strtolower
Changes the whole string to lowercase.

```php
strtolower("THIS WAS UPPERCASE") === "this was uppercase";
```

## Strtoupper
Changes the whole string to uppercase.

```php
strtoupper("this was lowercase") === "THIS WAS LOWECASE";
```

## Trim
- Use to trim white space from inputted string.
- There are two more functions `ltrim` and `rtrim`, removes the whitespace on left or right.
- All these funcitons accept a second parameter, the string of characters that can be trimmed.

```php
trim("   padding removed on both sides   ");    // returns "padding removed on both sides"
trim("_#_#_#_#_content_#_#_#_#_", "#_");        // returns "content"
```