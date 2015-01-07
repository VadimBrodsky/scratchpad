# body_class
- Codex reference -- http://codex.wordpress.org/Function_Reference/body_class
- Gives the body element different classes and can be added.
- Typically, in the `header.php` HTML body tag.
- Can pass an array of additional classes as a parameter.

```php
<body <?php body_class( 'container' ); ?>>
```