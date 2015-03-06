---
title: "Ruby Classes: Accessing the Superclass" 
layout: post
category: ruby
date: 2015-03-05 21:33:02 
---

- To change the behavior of a superclass' method without completely overriding it.
- The keyword `super` is used for that.
- It returns the result of the original method to where `super` is called.

```ruby
class Pig < Animal
  def noise
    parent_noise = super
    return "Hello and also #{parent_noise}"
  end
end

wilbur = Pig.new
wilbur.make_noise
```