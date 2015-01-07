# get_the_tags
- Codex reference -- http://codex.wordpress.org/Function_Reference/get_the_tags
- Returns an array of objects, one object for each tag assigned to the post. 
- If this function is used in The Loop, then no ID need be passed.
- This function does not display anything; you should access the objects and then echo or otherwise use the desired member variables.
- Useful to test if there are tags assigned, to avoid outputting empty divs.

```php
<?php if(get_the_tags()) { ?>
    <p class="pull-right"><?php the_tags(); ?></p>
<?php } ?>
```