---
title: "Rails for Zombies 2: Level 4"
layout: post
date:category:
 2015-03-11 20:25:22
---

Creating a Mailer
=================

Rails can create and send mailers.

**Objective**: Create email for decomposition change and lost brain.

This will create the `ZombieMailer` and two views:

```bash
rails g mailer ZombieMailer decomp_change lost_brain
```

The mailer file is like a controller for mailers:

```ruby
# app/mailers/zombie_mailer.rb
class ZombieMailer < ActionMailer::Base
  default from: "from@example.com"

  def decomp_change(zombie)
    @zombie = zombie
    @last_tweet = @zombie.tweets.last

    attachments['z.pdf'] = File.read("#{Rails.root}/public/zombie.pdf")
    mail to: @zombie.email, subject: 'Your decomp stage has changed'
  end
  ...
end
```

Additional setting can be set in the action or as a default:

```ruby
cc: "my@email.com"
bcc: "my@email.com"
rely_to: "my@email.com"
```

To create the email itself need to use the mailer views

```erb
# app/views/zombie_mailer/decomp_change.text.erb
Greeting <%= @zombie.name %>,

  Your decomposition state is now <%= @zombie.decomp %> and your last tweet was : <%= @last_tweet.body %>

Good Luck!
```

To create an HTML email, rename the extension from text to HTML

```erb
# app/views/zombie_mailer/decomp_change.html.erb
<h1>Greeting <%= @zombie.name %>,</h1>

<p>Your decomposition state is now <%= @zombie.decomp %> and your last tweet was : <%= @last_tweet.body %></p>

<%= link_to "View yourself", zombie_url(@zombie) %>
```

To create a multipart email with both HTML and text, just create two files and rails will join them together.

The model is in charge of triggering the mail sending

```ruby
class Zombie <ActiveRecord::Base
  after_save :decomp_change_notification, if: :decomp_changed?

  private

  def decomp_change_notification
    ZombieMailer.decomp_change(self).deliver
  end
end
```


Mad Mini
========

Service for mass mailing and email marketing that integrates wit rails.

Gemfile `gem 'madmimi'` then `bundle install`.

```ruby
mimi = MadMimi.new('<email>', '<api_key>')
mimi.add_to_list('joe@example.com', 'newsletter')
mimi.remove_from_list('joe@example.com', 'newsletter')
mimi.memberships('joe@example.com')
```


Asset Pipeline
==============

Starting with rails 3.1 asset pipeline was added to manage stylesheets, images and javascripts.

These folders can have assets:

- `/app/assets/` stylesheets, javascripts, images -- app specific code
- `/lib/assets/` stylesheets, javascripts, images -- my shared code
- `/vendor/assets/` stylesheets, javascripts, images -- 3rd party code

Rails will look in all three places when using `/assets/custom.png`


Asset Tag Helpers
=================

Special tags that will set correct paths and set fingerprints:

```erb
<%= javascript_include_tag "custom" %>
<%= stylesheet_link_tag "style" %>
<%= image_tag "rails.png" %>
```

To use fingerprint caching in CSS files add the Erb extension and use the `asset_path` helper method:

```erb
# app/assets/stylesheets/zombie.css
form.new_zombie input.submit {
  background-image: url(<%= asset_path('button.png') %>)
}
```


Default Asset Generation
========================

To remove either sass or coffee script remove the gems from the Gemfile and re-run `bundle install`.

The `application.js` includes all the js assets via sprockets. It uses a manifest.

Sprockets for JS:

```javascript
// /app/assets/javascript/application.js
//= require jquery      // jQuery framework
//= require jquery_ujs  // Rails specific unobtrusive JS
//= require shard       // From lib folder
//= require friend      // From vendor folder
//= require self        // This file to set proper source order
//= require_tree .      // All files in this directory
```

Sprockets for CSS:

```css
/* /app/assets/stylesheets/application.css
/*
 *= require rest
 *= require_self
 *= require_tree .
*/
```

To precompile all files into `/public/assets/` run `rake assets:precompile`. It will also minify all code.
