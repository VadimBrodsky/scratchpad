---
title: "Rails for Zombies: Level 4" 
layout: post
category: rails
date: 2015-03-06 23:41:31 
---

Controllers
===========

- The brains that control our Models & Views. 
- Controller is the layer between the view and the model.
- Located under `/app/controllers/tweets_controller.rb`.
- The methods inside the controllers are called actions.
- The `show` action is mapped to the `show` view for the model, it is typically used to call the models.
- To grand the view access to the variables from the controller, the variables must be instance variables `@variable`.
- To change the rendered template from the default configuration use the `render action: 'status'` method in the controller.

```ruby
# /app/controllers/tweets_controller.rb
class TweetsController < ApplicationController
	def show
		@tweet = Tweet.find(1)
	end
end
```

```erb
<% # /app/views/tweets/show.html.erb %>
<h1><%= @tweet.status %></h1>
<p>Posted by <%= @tweet.zombie.name %></p>
```

Controller Action Parameters
============================

To generalize the rendering of all data from the model, need to pass parameters to the view.

Params Recipe: `params = {id: '1'}`

```ruby
# /app/controllers/tweets_controller.rb
class TweetsController < ApplicationController
	def show
		@tweet = Tweet.find(params[:id])
		render action: 'status'
	end
end
```

```erb
<% # /app/views/tweets/status.html.erb %>
<h1><%= @tweet.status %></h1>
<p>Posted by <%= @tweet.zombie.name %></p>
```

Creating model data based on url parameters
===========================================

```ruby
# /tweets?status=I'm dead
params = { status: "I'm dead" }
@tweet = Tweet.create(status: params[:status])
```

A hash within a hash

```ruby
# /tweets?tweet[status]=I'm dead
params = { tweet: {status: "I'm dead" } }
@tweet = Tweet.create(status: params[:tweet][:status])
```

Alternative Syntax

```ruby
@tweet = Tweet.create(params[:tweet])
```

- In Rails 4 we are required to use strong parameters when creating or updating with multiple attributes.
- Need to specify the parameter key we require.
- and the attributes we will permit to be set.
- If multiple things we needed to permit, use an array.

```ruby
@tweet = Tweet.create(params.require(:tweet).permit(:status))
@tweet = Tweet.create(params.require(:tweet).permit([:status, :location]))
```


Action Responses with XML or JSON
=================================

```ruby
class TweetsController < ApplicationController
	def show
		@tweet = Tweed.find(params[:id])
		respond_to do |format|
			format.html # show.html.erb
			format.json { render json: @tweet }
			format.xml {render xml: @tweet}
		end
	end
end
```


Typical Controller Actions
==========================

- `index` - lists all the tweets.
- `show` - show a single tweet.
- `new` - show a new tweet form.
- `edit` - show an edit tweet form.
- `create` - create a new tweet.
- `update` - update a tweet.
- `destroy` - delete a tweet.

```ruby
class TweetsController < ApplicationController
	def index 
	def show
	def new
	def edit
	def create
	def update
	def destroy
end
```


Adding Authentication - Redirect and Flash
==========================================

- To store user information for the session use the `session`.
- The `session` works like a per user hash.
- The helper method `flash` is used to send messages back to the user.
- The `redurect_to` allows to redirect the browser to a different action.

```ruby
# /app/controllers/tweets_controller.rb
class TweetsControler < ApplicationController
	def edit
		@tweet = Tweet.find(params[:id])
		if session[:zombie_id] != @tweet.zombie._id
			flash[:notice] = "Sorry, you can't edit this tweet"
			redirect_to(tweets_path)
	end
end
```

Alternate Recipe for Redirect and Flash

```ruby
redirect_to(tweets_path, notice: "Sorry, go away")
```

Setting flash notice outlet in the layout, usually beside `yield`.

```erb
<% if flash[:notice] %>
	<div id="notice"><%= flash[:notice] %></div>
<% end %>
```


DRY up the Controller Actions
=============================

Many actions require the same information, for example calling the tweet from the parameter. This can be externalized to a method that will be called before the other actions using the `before_action` method.

The `before_action` can be more specific by adding the `:only` argument with an array or methods.

```ruby
class TweetsControlelr < ApplicationController
	before_action :get_tweet, only: [:edit, :update, :destroy]

	def get_tweet
		@tweet = Tweet.find(params[:id])
	end
end
```