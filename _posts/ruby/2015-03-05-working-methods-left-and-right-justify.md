---
title: "Working Methods: Left and Right Justify" 
layout: post
category: ruby
date: 2015-03-05 21:46:56 
---

- Add characters to a string until reaches a defined length.
- Useful for command line output justification.

```ruby
"Hello".ljust(30, "#")
#=> "Hello#########################"
```

```ruby
"Hello".rjust(30, "#")
#=> "#########################Hello"
```