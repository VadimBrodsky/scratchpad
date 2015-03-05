---
title: "Object Types: Nil" 
layout: post
category: ruby
date: 2015-03-04 22:50:30 
---

- An empty object.
- Nil the only Ruby object that is `false` in a boolean context, apart from `false` itself.

```ruby
nil.nil?			#=> true
value.nil?			#=> false
"".nil?				#=> false
nil.to_i 			#=> 0
nil.to_s			#=> ""
nil.to_s.empty?		#=> true
```