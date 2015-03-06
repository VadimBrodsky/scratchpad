---
title: "Ruby Classes: Class Methods" 
layout: post
category: ruby
date: 2015-03-05 21:29:32 
---

- A method that can be called on a class, even without an instance of the class.
- Example: `Animal.new`.
- Using the `self` keyword, that applies to the object that we are currently in.

```ruby
def self.method_name
	...
end
```

```ruby
class Animal
	...
	def self.all_species
		['cat', 'cow', 'dog', 'duck', 'horse', 'pig']
	end

	def self.create_with_attributes(noise, color)
		animal = self.new(noise)
		animal.color = color
		return animal
	end
	...
end

puts Animal.all_species
animal2 = Animal.create_with_attributes('black', 'quack')
```