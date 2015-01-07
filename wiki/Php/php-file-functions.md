---
tags: #php #basics #functions @getting-good-php
---

# PHP File Functions

## fopen
- Open a file.
- First parameter - file path.
- Second parameter - the mode you want to open it in.
- Modes:
    - `r` opens to read.
    - `r+` opens to read and write, pointer at the beginning of the file.
    - `w` opens to write, clears all content from the file, or creates the file if it doesn't exist.
    - `w+` opens to read and write, clears all content from the file or creates the file if it doesn't exist.
    - `a` opefile handns to write, with the pointer at the end of the file.
    - `a+` opens to read and write, with the pointer at the end. It creates the file if it doesn't exist.



## file_get_contents
- Reads the entire file into a single string.
- Does not require to use `fopen` first.
- Parameter - the path to the file.

```php
$quote = file_get_contents("./quote.txt");
echo $quote;
```


## fgets
- Takes a file handle as a parameter, returns one line of the file.
- The pointer is moved forward.

```php
$file = fope("./quote.txt", "r");
$line1 = fgets($file);
$line2 = fgets($file);
```


## fread
- First parameter - the file handle as the first parameter.
- Second parameter - the number of bytes that the function will read out.
- If the number of bytes is larget than the file, the whole file would be read.

```php
$file = fopen("./quote.txt", "r");
echo fread($file, 29);
```


## file_put_contents
- Similar to `file_get_contents`, don't need to use `fopen`.
- First parameter - file path.
- Second parameter - the string that's to be written to the file.

```php
$str = "this is the content that will be written to the file";
file_put_contents("new_text_file.txt", $str);
```


## fputs and fwrite
- These two funcitons are an alias to the same function.
- First paramater - the handle string.
- Second parameter - the string to write

```php
$file = fopen("quote2.txt", "w+");
fwrite($file, "Winter is Coming");
```


## fclose
- Closes the file.
- Takes the file handle as a parameter.