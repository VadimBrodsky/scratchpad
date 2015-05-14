---
title: "Ruby Methods: Defining Methods" 
layout: post
category: ruby
date: 2015-03-05 21:21:02 
---

Method names can have question marks `?` - convention for tests and booleans.

```ruby
def method_name
	...
end

def add
	puts 1 + 1
end

def over_five?
	value = 3
	puts value > 5 ? 'over 5' : 'not over 5'
end
```