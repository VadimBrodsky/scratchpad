# wp_title
- Codex reference -- http://codex.wordpress.org/Function_Reference/wp_title
- Displays or returns the title of the page. 
- A separator string can be defined.
- This tag can be used anywhere within a template as long as it's outside The Loop on the main page.
- Typically used in the `<title>` element for the head of a page.
- A good practice is to use the `add_filter` function in `functions.php` to allow for SEO plugins integration.

```html
<title><?php wp_title("|"); ?></title>
```