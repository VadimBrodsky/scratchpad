---
layout: post
title: getting-good-php php basics functions php php php php php
categories: []
tags:
- basics
- functions
- php
status: publish
type: post
published: true
meta:
  _pingme: '1'
  _encloseme: '1'
author:
  login: vadimbrodsky
  email: vadim@vadimbrodsky.com
  display_name: Vadim
  first_name: Vadim
  last_name: Brodsky
---
<p>#php #basics #functions @getting-good-php</p>
<p># PHP File Functions</p>
<p>## fopen<br />
- Open a file.<br />
- First parameter - file path.<br />
- Second parameter - the mode you want to open it in.<br />
- Modes:<br />
    - `r` opens to read.<br />
    - `r+` opens to read and write, pointer at the beginning of the file.<br />
    - `w` opens to write, clears all content from the file, or creates the file if it doesn't exist.<br />
    - `w+` opens to read and write, clears all content from the file or creates the file if it doesn't exist.<br />
    - `a` opefile handns to write, with the pointer at the end of the file.<br />
    - `a+` opens to read and write, with the pointer at the end. It creates the file if it doesn't exist.</p>
<p>## file_get_contents<br />
- Reads the entire file into a single string.<br />
- Does not require to use `fopen` first.<br />
- Parameter - the path to the file.</p>
<p>```php<br />
$quote = file_get_contents("./quote.txt");<br />
echo $quote;<br />
```</p>
<p>## fgets<br />
- Takes a file handle as a parameter, returns one line of the file.<br />
- The pointer is moved forward.</p>
<p>```php<br />
$file = fope("./quote.txt", "r");<br />
$line1 = fgets($file);<br />
$line2 = fgets($file);<br />
```</p>
<p>## fread<br />
- First parameter - the file handle as the first parameter.<br />
- Second parameter - the number of bytes that the function will read out.<br />
- If the number of bytes is larget than the file, the whole file would be read.</p>
<p>```php<br />
$file = fopen("./quote.txt", "r");<br />
echo fread($file, 29);<br />
```</p>
<p>## file_put_contents<br />
- Similar to `file_get_contents`, don't need to use `fopen`.<br />
- First parameter - file path.<br />
- Second parameter - the string that's to be written to the file.</p>
<p>```php<br />
$str = "this is the content that will be written to the file";<br />
file_put_contents("new_text_file.txt", $str);<br />
```</p>
<p>## fputs and fwrite<br />
- These two funcitons are an alias to the same function.<br />
- First paramater - the handle string.<br />
- Second parameter - the string to write</p>
<p>```php<br />
$file = fopen("quote2.txt", "w+");<br />
fwrite($file, "Winter is Coming");<br />
```</p>
<p>## fclose<br />
- Closes the file.<br />
- Takes the file handle as a parameter.</p>
