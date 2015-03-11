---
title: "Rails for Zombies 2: Level 3" 
layout: post
category: rails
date: 2015-03-10 20:53:06 
---

What is REST
============

Representation State Transfer, published by Roy Fielding in 2000 in the "Architectural Styles and the Design of Network-based Software Architectures"

An example of REST is the HTTP protocol, it has:

1. Resources (noun) - addressable through URI
2. Standard methods (verb) - GET, POST, PUT, DELETE

## Rest Verbs:

| Actions | SQL    | REST   | URI      |
|---------|--------|--------|----------|
| show    | select | get    | /users/3 |
| create  | create | post   | /users   |
| update  | update | put    | /users/3 |
| destroy | delete | delete | /users/3 |


## Restful Links

To specify the correct verb for the transaction use the `method:`.

Show action:

```erb
<%= link_to 'show', zombie %>
```

Create action:

```erb
<%= link_to 'create', zombie, method: :post %>
```

Update action:

```erb
<%= link_to 'update', zombie, method: :put %>
```

Destroy action:

```erb
<%= link_to 'delete', zombie, method: :delete %>
```


Rake Routes
===========

The `resource` method in the routes files creates RESTful routes.

```ruby
# app/config/routes.rb
resources :zombies
```

Run the `rake routes` command to get a list of all the defined routes in the application.


### Relative Paths

- `zombies_path` -- `/zombies`
- `new_zombie_path` -- `/zombies/new`

### Absolute Paths

- `zombies_url` -- `http://localhost:3000/zombies`
- `new_zombie_url` -- `http://localhost:3000/zombies/new`


Creating a Form
===============

Both create and update zombie form:

```erb
<%= form_for(@zombie) do |f| %>
  ...
 <% end %>
```

If `@zombie` isn't saved to the database yet the form will use the post method.

```html
<form action="/zombies" method="post">
```

If the `@zombie` is saved to the database the form will use a put.

```html
<form action="/zombies/8" method="post">
	<input name="_method" type="hidden" value="put">
```


Submitting a Form
=================

Both create and update zombie form:

```erb
<%= form_for(@zombie) do |f| %>
  ...
  <%= f.submit %>
<% end %>
```

If `@zombie` isn't saved to the database yet:

```html
<input name="commit" type="submit" value="Create Zombie" />
```

If `@zombie` is already saved to the database:

```html
<input name="commit" type="submit" value="Update Zombie" />
```


Text_field Helper
=================

```erb
<%= form_for(@zombie) do |f| %>
  ...
	  <%= f.text_field :name %>
  <%= f.submit %>
<% end %>
```

When submitted the request parameters, can be viewed from the log:

```ruby
:params => {:zombie => {:name => "John"}}
```

If `@zombie` isn't saved to the database yet:

```html
<input name="zombie[name]" size="30" type="text" />
```

If `@zombie` is already saved to the database:

```html
<input name="zombie[name]" size="30" type="text" value="John" />
```

If `@zombie.name` has a validation error

```html
<div class="field_with_errors">
	<input name="zombie[name]" size="30" type="text" value="" />
</div>
```


Label Helper
============

```erb
<%= form_for(@zombie) do |f| %>
  ...
    <%= f.label :name %><br>
    <%= f.text_field :name %>
  <%= f.submit %>
<% end %>
```

will render out:

```html
<label for="zombie_name">Name</label>
```

If `@zombie.name` has a validation error

```html
<div class="field_with_error">
	<label for="zomie_name">Name</label>
</div>
```


Input Helpers
=============

Multiline text area:

```erb
<%= f.text_area :bio %>
```

Check box used for booleans:

```erb
<%= f.check_box :rotting %>
```

List of radio buttons (without their labels)

```erb
<%= f.radio_button :decomp, 'fresh', checked: true %>
<%= f.radio_button :decomp, 'rotting' %>
<%= f.radio_button :decomp, 'stale' %>
```

Select box with three options:

```erb
<%= f.select :decomp, ['fresh', 'rotting', 'stale'] %>
```

Select box with tree options, each with a numerical value:

```erb
<%= f.select :decomp, [['fresh', 1], ['rotting', 2], ['stale', 3]] %>
```


Alternative Text Input Helpers
==============================

Text filed types for password, numbers, range, email, url and telephone:

```erb
<%= f.password_field :password %>
<%= f.number_field :price %>
<%= f.range_field :quantity %>
<%= f.email_field :email %>
<%= f.url_field :website %>
<%= f.telephone_field :phone %>
```


Nested Routes
=============

We can nest dependent resources inside each other to create more Restful urls.

```ruby
# app/config/routes.rb
TwitterForZombies::Application.routes.draw do
	resources :zombies do
		resources :tweets
	end
end
```

To make this work we also need to update the controller and update all the links and form_for helpers.

```ruby
# app/controller/tweets_controller.rb
class TweetsController < ApplicationController
	before_filer :get_zombie

	def get_zombie
		@zombie = Zombie.find(params[:zombie_id])
	end

	def show
		@tweet = @zombie.tweets.find(params[:id])
		...
	end

	def index
		@tweets = @zombie.tweets
		...
	end
end
```

Run `rake routes` to find the nester routes.

```erb
<%= link_to "#{@zombie.name}'s Tweets", zombie_tweet_path(@zombie) %>
<%= link_to 'New Tweet', new_zombie_tweet_path(@zombie) %>
<%= link_to 'Edit', edit_zombie_tweet_path(@zombie, tweet) %>
<%= link_to 'Show', zombie_tweet_path(@zombie, tweet) %>
<%= link_to 'Show', [@zombie, tweet] %>
<%= link_to 'Destroy', [@zombie, tweet], method :delete %>
```



Partials
========

Partials have `_form.html.erb` underscores in the file name. In the view call the `render` method:

```erb
<%= render 'form' %>
```


Variable Safety
===============

In rails 3 all variables that are printed out to the view are escaped by default.

To render unsafe variables use the `raw` method:

```erb
<%= @tweet.body %>
<%= raw @tweet.body %>
```


Additional View Helpers
=======================

To create a div for each item in a set, also add the `dom_id(@tweet)` for each div. 

```erb
<% @tweets.each do |tweet| %>
	<%= div_for tweet do %>
		<%= tweet.body %>
	<% end %>
<% end %>
```

To truncate a string:

```erb
<%= truncate("I need brains!", :length => 10) %>
<%= truncate("I need brains!", :length => 10, separator: ' ') %>
```

To pluralize:

```erb
I see <%= pluralize(Zombie.count, "zombie") %>
```

To output as a title case:

```erb
His name was <%= @zombie.name.titleize %>
```

To list an array as list of items in a sentence:

```erb
Ash's zombie roles are <%= @role_names.to_sentence %>
```

To show a date in time ago format:

```erb
He was buried alive <%= time_ago_in_words @zombie.create_at %> ago.
```

To display currency in a a correct way:

```erb
Price is <%= number_to_currency 13.5 %>
```

To conver a number to human readable:

```erb
Ash is <%= number_to_human 1232311223 %> years old.
```