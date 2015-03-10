---
title: "Rails for Zombies: Level 5" 
layout: post
category: rails
date: 2015-03-07 00:46:34 
---

Routing in Rails
================

- In order to map the action to the correct paths in the views we need to defines routes in the router.
- Crating a RESTFUL resource, one line of `resources` creates all of the standard actions fot a RESTFUL resrouce.
- Located under `app/config/routes.rb`.

```ruby
# /config/routes.rb
ZombieTwitter::Application.routes.draw do
	resrouces :tweets
end
```

Route Mathing
=============

- Can add route aliases for actions, for example `/new_tweet` and `/tweets/new`.
- Also known as Named Routes.
- Need to specify what method to accept, path of the custom URL and a sting that specifies the controller name and the action.
- To get the `link_to` helper to work with named routes, need to pass an addtional argument `as: 'helper_name'` to the named route definition.

```ruby
# /config/routes.rb
ZombieTwitter::Application.routes.draw do
	resrouces :tweets
	get '/new_tweet' => 'tweets#new'
	get '/all' => 'tweets#index' as: 'all_tweets'
end
```

```erb
<%= link_to "All Tweets", all_tweets_path %>
```


Route Redirecting
=================

- Redirect from all to tweets.

```ruby
# /config/routes.rb
ZombieTwitter::Application.routes.draw do
	get '/all' => redirect('/tweets')
end
```


Root Route
=========

- The root of the domain.
- Need to specify which controller and which action is triggered on root.

```ruby
root to: "tweets#index"
```

```erb
<%= link_to "All Tweets", root_path %>
```


Root Parameters
===============

Find all zombie tweets in this zip code, repond to parmeter.

```ruby
# /app/controllers/tweets_controller.rb
def index
	if params[:zipcode]
		@tweets = Tweet.where(zipcode: params[:zipcode])
	else
		@tweets = Tweet.all
	end
	respond_to do |format|
		format.html # index.html.erb
		format.xml { render xml: @tweets }
	end
end
```

Need to specifiy the name of the parameter that the application expects in the router.

```ruby
get '/local_tweets/:zipcode' => 'tweets#index'
```

name this route to be used with `link_to`

```ruby
get '/local_tweets/:zipcode' => 'tweets#index, as: 'local_tweets'
```

```erb
<%= link_to "Tweets in 32828", local_tweets_path(32828) %>
```

To show the tweets for these zombies / users:

```
# at the end of the router file
get ':name' => 'tweets#index', as: 'zombie_tweets'
```

```erb
<%= link_to 'Gregg', zombie_tweets_path('gregg') %>
```

in the controller:

```ruby
# /app/controllers/tweets_controllers.rb
def index
	if params[:name]
		@zombie = Zombie.where(name: params[:name]).first
		@tweers = @zombie.tweets
	else
		@tweets = Tweet.all
	end
end
```