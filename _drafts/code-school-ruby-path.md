---
title: "Code School: Try Ruby Notes" 
layout: post
category: ruby 
date: 2015-03-06 20:02:13 
---


# Array Methods: Max and Sort

```ruby
ticket = [12, 34, 22]
ticket.max
ticket.sort!
```


# Replacing part of a string

```ruby
string = "The quick brown fox jumped over the lazy dog"
string["fox"] = "rabbit"
```


# Getting the lines of a multi-line string

The `lines` method splits a string on line-breaks, `bytes` and `chars` are similar.

```ruby
poem.lines
poem.lines.to_a.reverse
poem.lines.to_a.reverse.join
```

# Default Values for a Hash

```ruby
ratings = Hash.new(0)
```

# List all of the files in a Directory

The `"/"` is a root path of the system.

```ruby
Dir.entries "/"
```

List only the text files in a directory

```ruby
Dir["/*.tx­t"]
```