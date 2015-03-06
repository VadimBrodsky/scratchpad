---
title: "Ruby Classes: Attributes" 
layout: post
category: ruby
date: 2015-03-05 21:26:46 
---

- Values that persists inside of an instance. 
- A special kind of variable - `@variable` an [[Instance Variables]].
- Never has access to instance variables outside of the instance.
- Only the methods of the class have access to instance variables.

```ruby
class Animal
  def set_noise(noise)
    @noise = noise 
  end

  def make_noise
    @noise
  end
end

animal1 = Animal.new
animal1.set_noise("Moo!")
puts animal1.make_noise 	#=> "Moo!"

animal2 = Animal.new
animal.set_noise("Whoof!")
puts animal2.make_noise 	#=> "Whoof!"
```