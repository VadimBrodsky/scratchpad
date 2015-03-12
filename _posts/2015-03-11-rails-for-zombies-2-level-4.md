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

<= link_to "View yourself", zombie_url(@zombie) %>
```

To create a multipart email with both HTML and text, just create two files and rails will join them together.
