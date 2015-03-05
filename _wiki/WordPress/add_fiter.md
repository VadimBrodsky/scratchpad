# add_filter
- Allow to modify content before it's output at HTML.
- Add filter function parameters:
    -  What you are filtering (the_hook)
    -  Function that will perform the filtering
    -  The priority
    -  How many parameters to accept
-  Codex reference -- http://codex.wordpress.org/Plugin_API#Create_a_Filter_Function


```php
function theme3_filter_wp_title ($current_title, $sep, $seplocal) {
    // Grab the site name
    $site_name = get_bloginfo('name');
    
    // Add the site name after the current page title
    $full_title = $site_name . $current_title;
    
    // If we are on the front_page or homepage append the description
    if ( is_front_page() || is_home() ) {
        // Grab the site description
        $site_desc = get_bloginfo('description');
        
        // Append site description to title
        $full_title .= ' ' . $sep . ' ' .$site_desc;
    }
    // Return the modified title
    return $full_title;
}

// Hook into 'wp_title'
add_filter('wp_title', 'theme3_filter_wp_title', 10, 3);
```