---
title: "Twig for Craft"
layout: post
category: Twig
date: 2015-05-11 14:22:31
---

# Twig

- Use output tags `{{ value }}` when need to print the value to the screen.
- Use logic tags `{% command %}` for twig commands.

## Comments

```twig
{# Holy cow Twig is awesome! #}
{# This would not render in HTML #}
```


## Variables
- There are different types of variables – strings, arrays, booleans, and objects.
- You can pass them into functions, manipulate them, and output them.
- All of your Craft templates are pre-loaded with a few global variables.
- templates that are loaded as a result of a matching route get pre-loaded with the variables defined by the route’s tokens.
- Templates that are loaded as the result of a matching entry URL get an “entry” variable.

```twig
{% set hour = now|date("G") %}
{% set author = 'Ryan Ireland' %}
```

Set can apply to a whole block of code

```twig
{% set socailLinks %}
  <ul class="social">
    <li class="twitter"><a href="">Twitter</a></li>
    <li class="facebook"><a href="">Facebook</a></li>
    <li class="instagram"><a href="">Instagram</a></li>
  </ul>
{% endset %}
```

Can set multiple variable on the same line

```twig
{% set title, subtitle, description = 'Foo', 'Bar', 'Baz' %}
```

## Hashes

```twig
{% set nav = {
  about:    {title: "Foo", desc: "Bar"},
  services: {title: "Foo", desc: "Bar"},
  work:     {title: "Foo", desc: "Bar"}
} %}
```


## Filters
- To manipulate variables and output with filters

```twig
{{ siteName | upper }}
{{ entry.title | upper }}
{{ now|date("M d, Y") }}
{{ page_title | title }}
{{ page_title | trim }}
{{ page_title | trim('.') }}
{{ page_title | trim('.') | title }}
```


## Conditionals

```twig
<p>Is it happy hour?</p>

{% set hour = now|date("G") %}
{% if hour >= 16 and hour < 18 %}
  <p>Yes!</p>
{% else %}
  <p>Nope.</p>
{% endif %}
```

```twig
{% if entries | length == 0 %}
  <p>No entries available</p>
{% endif %}
```

Logical conditionals

```twig
{% if bodyClass is not defined %}
  {% set bodyClass = entry is defined ? entry.section.handle : craft.request.firstSegmetn %}
{% endif %}
```

Check for the first iteration in a loop

```twig
{% if loop.first %}
  ...
{% endif %}
```

Additional loop methods
- `loop.first`: evaluates true if the current iteration is the first one
- `loop.index`: count of the current iteration that starts at 1
- `loop.index0`: count of the current iteration that starts at 0
- `loop.revindex`: number of iteration that left starting at 1
- `loop.revindex0`: number of iterations that left starting at 0
- `loop.last`: will evaluate true if it is the last iteration of the loop
- `loop.length`: total numbers of items in the loop



## Loops

```twig
{% for employee in department %}
  {{ employee.name }}
{% endfor %}
```

```twig
{% for artist in craft.entries.find({section: 'Artists', limit: '4', offset: '4'}) %}
  ...
{% endfor %}
```


```twig
{% for entry in craft.entries.section('news') %}
  {{ entry.title }}
{% endfor %}
```

Twig supports ranges

```twig
<select name="age" id="">
  {% for age in 1..100 %}
    <option name="age-{{ age }}">{{ age }}</option>
  {% endfor %}
</select>
```

This also works

```twig
{% for age in range(1, 100) %}
```


## Template Inheritance via Extending templates
- A child template can add to the parent template
- Site-wide wrapper template that contains reusable code
- Twig tag, placed in the child template
- Takes a parameter identifying the template you want to extend.
- The parent template needs to define a block section to specify which part is being overridden.

```twig
{# in the parent template #}
{% block nameOfBlock %}
  ...
{% endblock %}
```

```twig
{# In the child template #}
{% extend "_layouts/cp" %}
{% block nameOfBlock %}
  ...
{% endblock %}
```

To extend the parent's block instead of overriding it use the `parent()` function.

```twig
{# In the child template #}
{% extend "_layouts/cp" %}
{% block nameOfBlock %}
  {{ parent() }}
  ...
{% endblock %}
```


## Includes Templates
- Allows to pull entire rendered template into another template
- Include a sidebar, footer or header template
- In pure Twig have to specify the `html` extension while in Craft the extension can be omitted
- The included template can have access to any variables that were set

```twig
{% include "twigSidenav.html" %}
{% include "includes/_craftSidenav" %}
```


## Craft Specific Includes
- `includeCss`: to include CSS snippets
- `includeCssFile`: to include a CSS file
- `includeHiResCss`: to include a CSS that targets Hi-Resolution screens via a media query
- `includeJs`: include a preset JavaScript snippet
- `includeJSFile`: includes a JavaScript file before the closing body tag


## Embedding Templates
- Offers a hybrid of `extend` and `include` tags
- Includes an entire template but override parts of the template using blocks
- Like an `extend` but allows to pass on variables


```twig
{% embed 'social' %}
  {% block title %}
    ...
  {% endblock %}
{% endembed %}
```

The template that is being embedded:

```twig
<div class="module-social">
  <h4>{% block title %}We're Social{% endblock %}</h4>
  <ul>
    <li><a href="">Follow us on Twitter</a></li>
    <li><a href="">Follow us on Facebook</a></li>
    <li><a href="">Follow us on Instagram</a></li>
  </ul>
</div>
```

## Blocks

- Define where to yield data from child templates

```twig
{% block content %}
  ...
{% endblock %}
```


## Functions

```twig

```


## Craft Global Variables

- Site name: `{{ siteName }}`, defined in Settings -> General Settings -> Site Name
- Global fields: `{{ siteWideInformation.siteTagline }}`
- Entry Title: `{{ entry.title }}`
- Entry Body: `{{ entry.body }}`


## Image Transform URL

```twig
<img src="{{ image.getUrl('artistThumbnail') }}">
```


## 404 Template
- Add `404.html` file in the root template.

```
template/404.html
```

## Macros
- The Twig version of functions
- Use a Twig macro to generate often used markup with slight variations
- When used in the same file `{{ _self.socialList(networks, "three-networks") }}`

```twig
{% macro macroName(param1, param2) %}
  ...
{% endmacro %}
```

Macro defined in a separate file

```twig
{# _macros.html #}

{% macro socialList(networks, className) %}
  <ul {% if className %}class="{{ className }}"{% endif %}>
  {% for network in networks %}
    <li class="{{ network.name | lower }}"><a href="{{ nework.url }}">{{ network.name }}</a></li>
  {% endfor %}
  </ul>
{% endmacro %}

```

Then use it in a template


```twig
{# template.html #}

{% import '_macros' as siteMacros %}

{% set networks = {
  twitter: {name: "Twitter", url: "http://www.twitter.com/"},
  facebook: {name: "Facebook", url: "http://www.facebook.com/"},
  instagram: {name: "Instagram", url: "http://www.instagram.com/"}
} %}

{{ siteMacros.socialList(networks, "three-networks") }}
```


## Verbatim
- Tells Twig to process sections of code or content as raw text
- Used to be called `raw`
- Twig won't process the Twig tags, just outputs the code as code


## Navigation and Pagination
- Craft-specific tags
- Navigation tag creates hierarchical navigation
- Pagination tags give standard pagination for section entries


## Craft Nav Tag
- A Craft tag, not part of Twig
- Create hierarchical navigation for Structure sections or Category groups
- The biggest benefit of the `nav` tag is the flexibility to add nested lists with `children` tag`

```twig
{% set entries = craft.entries.section('services') %}
<ul>
  {% nav entry in entries %}
  <li><a href="{{ entry.url }}">{{ entry.title }}</a>
    {% ifchildren %}
      <ul>
        {% children %}
      </ul>
    {% endifchildren %}
  </li>
  {% endnav %}
</ul>
```


## Craft paginate Tag
- A Craft tag, not part of Twig
- Allows to create next and previous links
- Uses the `{% paginate %}` and `{% endpaginate %}` tags

```twig
{% paginate craft.entries.section('news').limit('4') as newsEntries %}

  {% for newsEntry in newsEntries %}
    {% if loop.first and craft.request.pageNum == 1 %}
      Only items on the first page of the pagination
    {% endif %}
    Other items
  {% endfor %}

  <div class="pagination-nav">
    <ul>
      {% if paginate.prevUrl %}
        <li><a href="{{ paginate.prevUrl }}">Previous Page</a></li>
      {% endif %}

      {% for page, url in paginate.getPreviousUrls(5) %}
        <li><a href="{{ url }}">{{ page }}</a></li>
      {% endfor %}

      <li class="current">{{ paginate.currentPage }}</li>

      {% for page, url in paginate.getNextUrls(5) %}
        <li><a href="{{ url }}">{{ page }}</a></li>
      {{ endfor }}

      {% if paginate.nextUrl %}
        <li><a href="{{ paginate.nextUrl }}">Next Page</a></li>
      {% endif %}
    </ul>
  </div>
{% endpaginate %}
```
