---
title: "Ruby Modules: Namespaces" 
layout: post
category: ruby
date: 2015-03-05 21:37:54 
---

- Namespacing allows for class names that don't conflict.
- Use a namespace wrapper and double colons `ModuleName::ClassName`.
- Keep class name distinct from standard Ruby classes.
- Disambiguating your own class definitions.
- Ensure classes used in open source code won't conflict.

```ruby
module Romantic 		# Module wrapper
	class Date
		...
	end
end

dinner = Romantic::Date.new 	# Module date
dinner.date = Date.new 			# Ruby date
```