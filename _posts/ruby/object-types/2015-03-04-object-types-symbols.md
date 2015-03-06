---
title: "Object Types: Symbols" 
layout: post
category: ruby
date: 2015-03-04 22:43:42 
---

- Symbol: a label that is used to identify a piece of data.
- Stored in memory one time.
- Good for keys in hashes.

```ruby
:test
:test.object_id        #=> 197608
```

```ruby
hash = {:first_name => 'John', :last_name => 'Smith'}
hash[:first_name]
```

```ruby
 # As of Ruby 1.9 this is equivalent to the previous example
hash = {first_name: 'John', last_name: 'Smith'}

{ :name => "John" } == { name: "John" }
```
