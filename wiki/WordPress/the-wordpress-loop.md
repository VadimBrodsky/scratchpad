# The WordPress Loop
- Codex reference -- http://codex.wordpress.org/The_Loop_in_Action
- When the structure of the content repeats, but only the content changes.
- The engine behind WordPress blogs.
- Most of the time the loop will only lists 10 posts, as set in the Reading Settings of WordPress.

```php
<?php if(have_posts()) : while(have_posts()) : the_post(); ?>
    <!-- content here -->
<?php endwhile; else: ?>
    <p><?php _e('Sorry, no posts matches your criteria.'); ?></p>
<?php endif; ?>
```