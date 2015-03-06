---
title: "Ruby Classes: Reader and Writer Methods" 
layout: post
category: ruby
date: 2015-03-05 21:26:51 
---

- Same as getters / setters in other languages.
- Give access control over the instance variables.
- Ruby has syntactic sugar to make the reader and writer method more concise.

```ruby
class Animal
	def noise=(noise) 		# same as above but shorter
		@noise = noise
	end

	def noise 				# same as above but shorter
		@noise
	end
end

animal = Animal.new 		
animal.noise = "Moo!" 		# like assigning a variable
puts animal.noise
```