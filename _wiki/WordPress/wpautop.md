# wpautop
- Codex reference -- http://codex.wordpress.org/Function_Reference/wpautop
- Changes double line-breaks in the text into HTML paragraphs `<p>`...`</p>`.
- WordPress uses it to filter the content and the excerpt.

```php
<?php wpautop( $foo, $br ); ?> 
```