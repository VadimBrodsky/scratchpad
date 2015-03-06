---
title: "Ruby Methods: Default Values" 
layout: post
category: ruby
date: 2015-03-05 21:22:47 
---

- Default behavior for the method, so it will not break if the argument is missing when the method is called.
- Make the required arguments first in the argument list.

```ruby
def welcome(name="Friend")
	puts "Hello #{name}"
end
```