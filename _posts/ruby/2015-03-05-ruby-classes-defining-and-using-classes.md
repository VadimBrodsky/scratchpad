---
title: "Ruby Classes: Defining and Using Classes" 
layout: post
category: ruby
date: 2015-03-05 21:25:56 
---

```ruby
class NameOfClass
	...
end
```

```ruby
class Animal
	def make_noise
		"Moo!"
	end
end

animal = Animal.new 	#=> #<Animal:0x007f9e7d1a9dc0>
animal.make_noise 		#=> "Moo!"
```