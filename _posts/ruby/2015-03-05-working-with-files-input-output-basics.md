---
title: "Working With Files: Input / Output Basics" 
layout: post
category: ruby
date: 2015-03-05 21:41:23 
---

- Input / Output of a ruby program.
- The `gets` method receives input from the user.
- Use `chomp` to remove the trailing `\n`.
- Use `chop` to remove the last character.

```ruby
input = gets 		#=> "Hello.\n"
input.chomp 		#=> "Hello."
input.chop 			#=> "Hello"

print input 		#=> "Hello"
puts input 			#=> "Hello\n"
```