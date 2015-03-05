---
title: "Ruby Control Structures: Conditionals" 
layout: post
category: ruby
date: 2015-03-04 23:02:05 
---

If something true, do this.

```ruby
if boolean
	...
end
```

```ruby
if boolean
	...
else
	...
end
```

```ruby
if boolean
	...
elsif boolean
	...
else
	...
end
```

```ruby
if x < 10
	puts "Below 10"
elsif x > 20
	puts "Over 20"
else
	puts "10-20"
end
```

```ruby
puts "This is Vadim" if name == "Vadim"  # inline conditional
```