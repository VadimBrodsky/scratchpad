---
title: "Rails for Zombies 2: Level 5"
layout: post
category: rails
date: 2015-03-12 20:48:46
---

Default Action Rendering
========================

By default rails will use the `show` action with the `show` view.

```ruby
# app/controllers/zombies_controller.rb
class ZombieController < ApplicationController
  def show
    @zombie = Zombie.find(params[:id])
  end
end
```

Will look for the `show` view in `app/views/zombies/show.html.erb`


Respond_to Block
================

To make the controller respond to other request use the `respond_to` block:

```ruby
# app/controllers/zombies_controller.rb
  ...
  @zombie = Zombie.find(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @zombie }
  end
  ...
```

To specify a custom render, if the condition is not satisfied it will still render the default `show` view.

```ruby
# app/controllers/zombies_controller.rb
...
  @zombie = Zombie.find(params[:id])
  respond_to do |format|
    format.html do
      if @zombie.decomp == 'Dead (again)'
        render :dead_again
      end
    end
    format.json { render json: @zombie }
  end
  ...
```

If the action only needs to respond to only one thing, don't need the `respond_to` block.

Only json:

```ruby
# app/controllers/zombies_controller.rb
...
  @zombie = Zombie.find(param[:id])
  render json: @zombie
...
```


HTTP Status Codes
=================

The default code is `:ok` 200.

| Code | Symbol                 |
|------|------------------------|
| 200  | `:ok`                  |
| 201  | `:created`             |
| 422  | `:unprocessable_untry` |
| 401  | `:unauthorized`        |
| 102  | `:processing`          |
| 404  | `:not_found`           |


```ruby
render json: @zombie.errors, status: :unprocessable_entry
```

Resource created, adds a URI location for the new resource.

```ruby
render json: @zombie, status: :created, location: @zombie
```


Custom Route and Action
=======================

```ruby
# config/ routes
match 'zombies/:id/decomp' => 'Zombies#decomp', :as => :decomp_zombie
```

or create a RESTful Route, this is equivalent.

```ruby
resource :zombies do
  resources :tweets
  get :decomp, on: :member
end
```


Two Types of Custom Routes
========================

1. `:member` - Acts on a single resource.
2. `:collection` - Acts on a collection of resources.

```ruby
get :decomp, on: :member   # /zombies/:id/decomp    decomp_zombie_path(@zombie)
put :decat, on: :member    # /zombies/:id/decay     decay_combie_path(@zombie)
```

```ruby
get :fresh, on: :collection     # /zombies/fresh    fresh_zombies_path
post :search, on: :collection   # /zombies/sear     search_zombies_path
```


Respond With JSON Status
========================

```ruby
# app/controller/zombies_controller.rb
class ZombiesController < ApplicationController
  def decomp
    @zombie = Zombie.find(param[:id])
    if @zombie.decomp == 'Dead (again)'
      render json: @zombie, status: :unprocessable_entity
    else
      render json: @zombie, status: :ok
    end
  end
end
```


Customize JSON Response
=======================

Only name

```ruby
@zombie.to_json(only: :name)
```

List of information to include

```ruby
@zombie.to_json(only: [:name, :age])
```

To exclude information

```ruby
@zombie.to_json(execpt: [:created_at, :updated_at, :id, :email, :bio])
```

Include data from relations

```ruby
@zombie.to_json(include: :brain, except: [:created_at, :updated_at, :id])
```


Set Default JSON Response
=========================

```ruby
# /app/models/zombie.rb
class Zombie < ActiveRecord::Base
  ...
  def as_json(options = nil)
    super(options || {include: :brain, except: [:created_at, :updated_at, :id]})
  end
end
```


Ajax Delete Link
================

When Delete is pressed do a fade out, instead of a page refresh:

1. Make the link a remote call
2. Allow the controller to accept JavaScript call
3. Write the JavaScript to send back to the client

To make a link into a remote call add the `remote: true` option.

```erb
<% # /app/views/zombies/index.html.erb %>
<%= link_to 'delete', zombie, method: :delete, remote: :true %>
```

To allow the controller to accept the JavaScript call

```ruby
# app/controllers/zombies_controller.rb
def destroy
  ...
  respond_to do |format|
    format.html { redirect_to zombies_url }
    format.json { head :ok }
    format.js  # can respond with js
  end
  ...
end
```

The JavaScript to send back to the client

```javascript
// app/views/zombies/destroy.js.erb
$('#<%= dom_id(@zombie) %>').fadeOut();
```


Ajax Create Form
================

Create an Ajax form which will create a new zombie and add it to the list

1. Write format.js in the controller
2. Refactor the view and create the form
3. Create the JavaScript

To allow Ajax save data

```ruby
# app/controllers/zombie_controller.rb
def create
  respond_to do |format|
    if @zombie.save
      format.html { ... }
      format.json { ... }
    else
      format.html { ... }
      format.json { ... }
    end
    format.js  # can accept data with js
  end
end
```

Refactor the view:

The loop can be separated into its own file - `/app/views/zombies/_zombie.html.erb`. This partial can be called using the class name, due to the naming convention.

```erb
<div id="zombies">
  <% @zombies.each do |zombie| %>
    <%= render zombie %>
  <% end >%
</div>
```

The above can be simplified, rails will imply the need for a loop:

```erb
<div id="zombies">
  <%= render @zombies %>
</div>
```

Add an Ajax form:

```erb
<%= form_for(Zombie.new, remote: true) do |f| %>
  <div class="field"
    <%= f.label :name %><br />
    <%= f.text_field :name %>
  </div>
  <div class="actions">
    <%= f.submit %>
  </div>
<% end %>
```

Add the JavaScript to view the added information. This example relies on jQuery UI for the effects.

```javascript
// app/views/create.js.erb
<% if @zombie.new_record? %>
  $('input#zombie_name').effect('highlight', { color: 'red' });
<% else %>
  $('div#zombies').append("<%= escape_javascript(render @zombie) %>");
  $('div#<%= dom_id(@zombie) %>').effect('highlight');
<% end %>
```


Ajax Custom Form
================

Set a custom decomposition state on a zombie show page:

1. Create new custom route for our action
2. Define the form
3. Create action in the controller
4. Write the JavaScript to send back to the client

Create a new route for the action

```ruby
# /config/routes.rb
resources :zombies do
    resources :tweets
    get :decomp, on: :member
    put :custom_decomp, on: :member
end
```

Update the view

```erb
<strong> Decomposition Phase:</strong>
<span id="decomp"><%= @zombie.decomp %></span>
```

Create the form

```erb
<div id="custom_phase">
  <%= form_for @zombie, url: custom_decomp_zombie_path(@zombie), remote: true do |f| %>
    <strong>Custom Phase</strong>
    <%= f.text_field :decomp %>
    <%= f.sublit "Set" %>
  <% end %>
</div>
```

Create the action in the controller, don't need a `respond_to` block because the response is only in js.

```ruby
def custom_decomp
  @zombie = Zombie.find(params[:id])
  @zombie.decomp = params[:zombie][:decomp]
  @zombie.save
end
```

JavaScript to update the client

```javascript
// /app/views/zombies/advance_decomp.js.erb
$('#decomp').text('<%= @zombie.decomp %>').effect('highlight', {}, 3000);

<% if @zombie.decomp == 'Dead (again)' %>
  $('div#custom_phase').fadeOut();
<% end %>
```


Custom Action on the Client using JSON with an API
==================================================

Do the same as above, but use JSON with client side JavaScript

1. Define the form
2. Modify the custom_decomp action
3. Write the client side JavaScript using CoffeeScipt

Define the form, this time no `remote: true`

```erb
<div id="custom_phase2">
  <%= form_for @zombie, url: custom_decomp_zombie_path(@zombie) do |f| %>
    <strong>Custom Phase via JSON</strong>
    <%= f.text_field :decomp %>
    <%= f.submit "Set" %>
  <% end %>
</div>
```

Add the `respond_to` block to the action

```ruby
# /app/controllers/zombies_controller.rb
def custom_decomp
  ...
  respond_to do |format|
    format.js
    format.json { render json: @zombie.to_json(only: :decomp) }
  end
end
```

Client side CoffeeScript

```coffeescript
# /app/assets/javascripts/zombies.js.coffee
$(document).ready ->
  $('div#custom_phase2 form').submit (event) ->
    event.preventDefault()

    url = $(this).attr('action')
    custom_decomp = $('$div#custom_phase2 #zombie_decomp').val()

    $.ajax
      type: 'put'
      url: url
      data: { zombie: { decomp: custom_decomp } }
      dataType: 'json'
      success: (json) ->
        $('#decomp').text(json.decomp).effect('highlight')
        $('div#custom_phase2').fadeOut() if json.decomp == "Dead (again)"
```
