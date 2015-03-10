---
title: "Rails for Zombies: Level 2" 
layout: post
category: ruby
date: 2015-03-06 22:12:28 
---

Models
======

- How your Rails application communicates with a data store.
- Models are located under `app/modes/modelname.rb`.
- To enforce the non blank data use `validates_presence_of` method.

```ruby
class Tweet < ActiveRecord::Base
  validates_presence_of :status
end
```


Model Errors
============

To see the model errors use the `.errors.messages` on the model instance to get a hash with the error messages.

```ruby
t.errors.messages
t.errors[:status][0]
```


Model Validation Methods
=======================

Validation included by Rails:

```ruby
validates_presence_of :status
validated_numericality_of :fingers
validated_uniqueness_of :toothmarks
validates_confirmation_of :password
validates_acceptance_of :zombification
validates_length_of :password, minimum: 3
validates_format_of :email, with: /regex/i
validates_inclusion_of :age, in: 21..99
validates_exclusion_of :age, in: 0...21, message: "Sorry you must be 21"
```

Alternative syntax:

```ruby
validates :status, presence: true
validates :status, length { minimum: 3 }
```

or as a single line

```ruby
validates :status,
          presence: true,
          length: { minimum: 3 }
```


Model Relationships
===================

Linking data across multiple tables.

```ruby
# app/models/zombie.rb
class Zombie < ActiveRecord::Base
  has_many :tweets
end
```

```ruby
# app/models/tweet.rb
class Tweet < ActiveRecord::Base
  belongs_to :zombie
end
```

Using associations

```ruby
ash = Zombie.find(1)
t = Tweet.create(status: "hello world", zombie: ash)
ash.tweets.count
ash.tweets
```

```ruby
t = Tweet.find(5)
t.zombie
t.zombie.name
```