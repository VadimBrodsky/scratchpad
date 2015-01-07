# WordPress Header.php

## Doctype
Must include a valid doctype.

```html
<!DOCTYPE html>
```

## HTML Tag
- Wordpress helps us to declare the language settings.
- Uses the `language_attributes` function.
- Codex reference -- http://codex.wordpress.org/Function_Reference/language_attributes

```html
<html <?php language_attributes(); ?>></html>
```

## Title Tag
- Set the title of the page.
- Need to make sure that SEO plugins are able to change the title, with the `wp_title` filer.
- Also passing the separator parameter, in this case `|`
- Need to add a filer to `functions.php` for this to work.
- Codex reference -- http://codex.wordpress.org/Function_Reference/wp_title

```html
<title>
    <?php wp_title("|"): ?>
</title>
```

## Meta Tag
- It is hard to build in static meta descriptions.
- Better to rely on SEO plugins for these.
- Can use `blog_info` for the `http-equiv` compliance.

```html
<meta http-equiv="Content-Type" content="<?php bloginfo('html_type'); ?>; charset=<?php bloginfo('charset'); ?>">
```

## Stylesheet and Other Template Files
- Need to use a funciton to map the path to these files, cannot rely on absolute or relative paths.

```html
<link rel="stylesheet" type="text/css" media="all" href="<?php bloginfo('stylesheet_url'); ?>" />
```

## Action Hook wp_head
- Need to include this at the end of `` to allow for plugin CSS and JavaScript output.

```html
<?php wp_head(); ?>
```

## Body Tag
- The last thing in in the `header.php` tag is the body tag,
- Need to add the `body_class` funciton to the `body` tag to have the WordPress generated classes apply to it.

```html
<body <?php body_class( 'container' ); ?> >
```