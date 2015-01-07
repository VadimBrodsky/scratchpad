---
tags: #php #basics @getting-good-php
---

# PHP Scope
- Variable have local scope by default.
- To expand the scope use the `global` keyword.
- Variables that are imported from required file act as local to the file.

```php
$friend = "Ghost";
function greet() {
    global $friend;
    echo "Hello $friend";
}
greet();
```


## Superglobals
- Group of variables that are avaliable in all scopes.
- They are all associative arrays, offer special information.
    - `$GLOBALS` - all global variables in the script.
    - `$_SERVER` - information about the server that is running the PHP.
    - `$_GET` - any HTTP GET request variables.
    - `$_POST` - any HTTP POST request variables.
    - `$_REQUEST` - info about the HTTP request.
    - `$_SESSION` - array to store variables that are needed across pages.
    - `$_ENV` - info about the environment.
    - `$_COOKIE` - HTTP cookie informaiton.