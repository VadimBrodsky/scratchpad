---
title: "Ruby Comparison Operator" 
layout: post
category: ruby
date: 2015-03-04 22:58:20 
---

Compares two values.

```ruby
value1 <=> value2
```

|  Return Value |  Meaning   |
| :------------ | :--------- |
|  -1           | Less than  |
|   0           | Equal      |
|   1           | More than  |

```ruby
1 <=> 2		#=> -1
2 <=> 1		#=> 1
2 <=> 2		#=> 0
```