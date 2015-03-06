---
title: "Working With Files: Writing" 
layout: post
category: ruby
date: 2015-03-05 21:43:30 
---

- Before writing the data to the file, Ruby waits for the file to be closed first.
- Write to the hard drive only once in batch.

```ruby
file = File.new('test_file.txt', 'w')
file.puts "abcd"
file.close
```

```ruby
file.puts "abcd" 		# puts string with line break
file.print "abcd" 		# puts string whiteout line break
file.write "abcd" 		# like print but returns the number of characters
file << "abcd" 			# like print but returns the object
```