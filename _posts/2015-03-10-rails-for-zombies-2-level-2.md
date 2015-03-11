---
title: "Rails for Zombies 2: Level 2" 
layout: post
category: rails
date: 2015-03-09 21:29:51 
---

Named Scope
===========

The more complex model data should be in the models file, especially frequently used lookups.

```ruby
# app/models/zombie.rb
class Zombie < ActiveRecord::Base
	scope :rotting, where(rotting: true)
	scope :fresh, where("age < 20")
	scope :recent, order("created_at desc").limit(3)
end
```

and in the controller:

```ruby
# app/controllers/rotting_zombies_controller.rb
class RottingZombiesController < ApplicationController
	def index
		@rotting_zombies = Zombie.rotting
		
		# Method chaining to create queries:
		Zombie.rotting.limit(5)
		Zombie.recent.rotting
		Zombie.recent.fresh.rotting
	end
end
```


Callbacks
=========

To have a method run every time before the `save` command use the `before_save` callback,

Code that is specified in the model file with a callback will run regardless of the action that is triggered in the controller.

Reading attributes doesn't need `self`, setting attributes needs `self`.

```ruby
# app/model/zombie.rb
class Zombie < ActiveRecord::Base
	before_save :make_rotting

	def make_rotting
		if age > 20
			self.rotting = true
		end
	end
end
```


Returning False in a Callback Will Halt
=======================================

The save operation will stop if the callback method returns false.

```ruby
before_save :taste

def taste
	false
end
```


All Callbacks
=============

All of the callback methods that are available in ActiveRecord.

- `before_vlidation` and `after_validation`
- `before_save` and `after_save`
- `before_create` and `after_create`
- `before_update` and `after_update`
- `before_destroy` and `after_destroy`

Notes:

- Can use multiple callbacks, even of same type.
- If any return false then everything stops, with before then save / destroy isn't done.

Examples:

```ruby
after_create :send_welcome_email
before_save :encrypt_password
before_destroy :set_deleted_flag
```


has_one Relationship
====================

Example: A zombie may or may not have a (single) brain.

```bash
rails g model brain zombie_id:integer status:string flavor:string
```

```ruby
# db/migrate/20110805011138_create_brains.rb
class CreateBrains < ActiveRecord::Migration
	def change
		create_table :brains do |t|
			t.integer :zombie_id
			t.string :status
			t.string :flavor
		end
		add_index :brains, :zombie_id
	end
end
```

```ruby
# app/models/brain.rb
class Brain < ActiveRecord::Base
	belongs_to :zombie
end
```

The `:dependent` option will make sure that if the zombie is destroyed the brain will be destroyed as well.

```ruby
# app/models/zombie.rb
class Zombie < ActiveRecord::Base
	has_one :brain, dependent: :destroy
end
```


Relationship Options
====================

Some of the relationship options:

- `dependent: :destroy` -- will call destroy on associated objects.
- `foreign_key: :unded_id` -- changes the associated key.
- `primary_key: :zid` -- change the primary key.
- `validates: true` -- when zombie validates brain will too.


Relationship Include Option
===========================

When using to display large amount of data in the view, the SQL will run for every query unless optimized with the `includes` methods.

```ruby
# app/controllers/zombies_controller.rb
def index
	@zombies = Zombie.includes(:brain).all
```


has_many :through Relationship
==============================

Example: A zombie may play multiple roles.

For this we will need to have a `Zombie` and `Role` tables, but to enable zombies to have more than one assignment an `Assignment` table is needed.

```ruby
# app/model/assignment.rb
class Assignment < ActiveRecord::Base
	belongs_to :zombie
	belongs_to :role
end
```

```ruby
# app/models/zombie.rb
class Zombie < ActiveRecord::Base
	has_many :assignments
	has_many :roles, through: :assignments
end
```

```ruby
# app/models/role.rb
class Role < ActiveRecord::Base
	has_many :assignments
	has_many :zombies, through: :assignments
end
```