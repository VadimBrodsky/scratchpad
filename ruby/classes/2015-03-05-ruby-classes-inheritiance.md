---
title: "Ruby Classes: Inheritiance" 
layout: post
category: ruby
date: 2015-03-05 21:31:51 
---

- Bestowal of methods and attributes of another class.
- Superclass / parent => subclass / children.
- In Ruby we can inherit from only 1 superclass at a time, there are no multiple inheritances.

```ruby
class Cow < Animal
end

betsy = Cow.new("Moo!")
betst.class 		# Cow
```