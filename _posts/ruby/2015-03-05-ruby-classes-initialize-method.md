---
title: "Ruby Classes: Initialize Method" 
layout: post
category: ruby
date: 2015-03-05 21:29:00 
---

- Methods that run when the object is being initialized.
- Use the `initialize` class method.
- Can pass arguments to the `initialize` method, the `new` method uses them.

```ruby
class Animal
	def initialize(noise, legs, arms)
		@noise = noise
		@legs = legs
		@arms = arms
		puts "A new animal has been instantiated."
	end
end

animal = Animal.new("Moo", 4, 0)
```