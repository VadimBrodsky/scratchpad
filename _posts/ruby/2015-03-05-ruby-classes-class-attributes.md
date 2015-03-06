---
title: "Ruby Classes: Class Attributes" 
layout: post
category: ruby
date: 2015-03-05 21:30:41 
---

- Store values that apply to the class generally.
- Using the class variable `@@variable`.
- Persists any time we have the class, even without the variables.
- Information that is general for the whole class.
- Keep track of all of the objects with `@@total`.
- Keep track of all the instances with an array of class attributes.
- Cannot access the class attributes outside of the class, only with class methods.

```ruby
class Animal
	...
	@@species = ['cat', 'cow', 'dog', 'duck', 'horse', 'pig']
	@@curent_animals = []

	def self.all_species
		@@species
	end

	def initialize
		@@current_animals << self
	end
	...
end

puts Animal.all_species
puts Animal.current_animals.inspect 	# would not work, need class method
```