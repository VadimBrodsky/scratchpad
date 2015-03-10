---
title: "Rails for Zombies: Level 1" 
layout: post
category: rails
date: 2015-03-06 21:25:49 
---

Hash Recipe
===========

```ruby
# General Hash Recipe
variable = { key: value }

# Reading value our of a hash
variable[:key] => value
```


Read - Retrieving Data from the Database
========================================

The table name is plural and lower case, the mapped object is singular and Title cased.

```ruby
t = Tweet.find(3)

# Hash syntax
t[:zombie]

# Dot syntax
t.zombie
```

More Complex Reading

```ruby
Tweet.find(2)
Tweet.find(2, 3, 4)
Tweet.first
Tweet.last
Tweet.all
```

```ruby
Tweet.count
Tweet.order(:zombie)
Tweet.limit(10)
Tweet.where(zombie: "ash")
```

Method Chaining

```ruby
Tweet.where(zombie: "ash").order(:status).limit(10)
Tweet.where(zombie: "ash").first
```


Create - Adding Data to the Database
======================================

Attribute Recipe

```ruby
t = TableName.new
t.key = value
t.save
```

Hash Recipe

```ruby
t = TableName.new(hash)
t.save
```

Shorthand

```ruby
TableName.create(hash)
```

Example

```ruby
t = Tweet.new
t.status = "Hello World"
t.save
```


Update
======

Generic Recipe

```
t = TableName.find(id)
t.key = value
t.save
```

Hash based Recipe

```ruby
t = TableName.find(id)
t.attributes = hash
t.save
```

Shorthand Recipe

```ruby
t = TableName.find(id)
t.update(hash)
```

Example

```ruby
t = Tweet.find(3)
t.zombie = "The Governor"
t.save
```


Delete
======

Deleting Recipe

```ruby
t = Table.find(id)
t.destroy
```

Finding and Destroying Recipe

```ruby
TableName.find(id).destroy
```

Destroying all

```ruby
TableName.destroy_all
```

Example

```ruby
t = Tweet.find(3)
t.destroy
```