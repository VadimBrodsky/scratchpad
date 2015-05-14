---
title: "Ruby Classes: Class Reader and Writer Methods" 
layout: post
category: ruby
date: 2015-03-05 21:31:19 
---

Same as with instance variables, class variables (attributes) need setter and getter methods.

```ruby
def self.animals    # reader
	@@animals
end

def self.animals=(array=[])    # writer
	@@animals = array
end
```