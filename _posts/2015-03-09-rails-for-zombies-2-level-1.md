---
title: "Rails for Zombies 2: Level 1" 
layout: post
category: rails
date: 2015-03-09 20:18:13 
---

Creating a Rails APP
====================

Running the `rails` command outside of the rails app folder shows usage information.

To create a new rails app type:

```
rails new TwitterForZombies
```

Running the `rails` command inside the rails app directory will show all of the commands that can be run on the app.

- `generate` or `g` - Generate new code.
- `console` or `c` - Start the Rails console.
- `server` or `s` - Start the Rails server.
- `dbconsole` or `db` - Start a console for the db in `config/database.yml`

All commands can be run with the `-h` flag for more information.


Using Generators
================

Used to generate source for the rails app.

```bash
rails generate GENERATOR [args]
rails g
```

- `helper` 
- `mailer`
- `migration`
- `model`
- `scaffold`

Scaffolds generate an entire resource, from model and migration to controller and views, along with a full test suite.

Variable database types: `string`, `text`, `integer`, `boolean`, `decimal`, `float`, `binary`, `date`, `time`, `datetime`.

```bash
rails g scaffold zombie name:string bio:text age:integer
```


Database Migration
==================

Dinging the database structure from inside rails. Rails automatically creates a primary key called `id`.

```ruby
# db/migrate/20110701239207_create_zombies.rb
class CreateZombies < ActiveRecord::Migration
	def change
		create_table :zombies do |t|
			t.string :name
			t.text :bio
			t.integer :age

			t.timestamps
		end
	end
end
```

The `t.timestamps` is equivalent to `t.datetime :created_at` and `t.datetime :updated_at`. Set automatically to track date and time for create and update events.

To apply the changes outlined in the migration file on the database the migration needs to be run.

```bash
rake db:migrate
```


Example: Adding Columns
=======================

Generate syntax to add columns to the databse structure - `Add<Anything>To<Table name>`

```bash
rails g migration AddEmailAndRottingToZombies email:string rotting:boolean
```

```ruby
class AddEmailAndRottingZombies < ActiveRecord::Migration
	def change
		add_column :zombies, :email, :string
		add_column :zombies, :rotting, :boolean, default: false
	end
end
```

Migration options can be set to specify additional options on the table or columns: `default: <value>`, `limit: 30`, `null: false`, `first: true`, `after: :email`, `unique: true`.


Migration Rake Tasks
====================

- `rake db:migrate` -- runs all missing migrations.
- `rake db:rollback` -- to rollback the previous migration.
- `rake db:schema:dump` -- dump the current db state.
- `rake db:setup` -- created db, loads schema.

The `db/schema.rb` is the authoritative source for db schema.

Best to run `db:setup` instead of `db:migrate` when starting work on an existing application.


Example: Removing Columns
=========================

To remove a column follow the `Remove<Anythin>From<Table Name>` pattern.

```bash
rails g migration RemoveAgeFromZombies age:integer
```

For more complex migrations, separate `up` and `down` methods need to be specified to keep compatibility with rollbacks.

```ruby
class RemoveAgeFromZombies < AriveRecord::Migration
	def up
		remove_colum :zombies, :age
	end

	def down
		add_column :zombies, :age, :integer
	end
end
```

Migration commands:

- `rename_column :zombies, :bio, :description`
- `rename_table :zombies, :ghouls`
- `drop_table :zombies`
- `change_column :zombies, :age, :integer, limit: 4`
- `change_column_default :zombies, :is_admin, default: true`


Example: Other Migrations
=========================

Use the format `<anything>` as part of the migration generator:

```bash
rails g migration DropZombiesTable
```


Database Configuration
======================

The default development database that comes with rails is `sqlite3` as specified in the `Gemfile`.

The database setting are located under `/congif/database.yml`.