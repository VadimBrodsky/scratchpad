---
title: "Object Types: Constants" 
layout: post
category: ruby
date: 2015-03-04 22:50:09 
---

- Constants are similar to variables.
- Not true objects, point to objects.
- Constants are different than variables, a constant is _constant_.
- Any variable that starts with a capital letter is a constant in Ruby.
- Changing constants will present a warning, but will work.

```ruby
CONST = "This is a constant"
CONST = "Changed"   #=> warning: already initialized constant CONST
CONST               #=> "Changed"
```