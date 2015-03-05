# get_search_query
- Codex reference -- http://codex.wordpress.org/Template_Tags/get_search_query
- The search query string is passed through `esc_attr()` to ensure that it is safe for placing in an html attribute. 
- This function is used to get the query string when a user performs a search on the site. 
- It returns the query string rather than displaying it, as the `the_search_query()` function does.

```php
<?php $search_query = get_search_query(); ?>
```