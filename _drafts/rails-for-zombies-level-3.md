---
title: "Rails for Zombies: Level 3" 
layout: post
category: rails
date: 2015-03-06 22:54:31 
---

Views - Visual represtnation of the app
=======================================

- User interface of the application - the rendered HTML.
- Views are located under `/app/views/tweets/index.html.erb`
- The boilerlate html code is under `/app/views/layouts/application.html.erb`
- By default Rails uses the Erb templating language.
- To evaluate Ruby code inside of an Erb template use the `<% ... %>` tags.
- To evaluate and print Ruby code use the `<%= ... %>` tags.
- To use the view code inide the application layout use the `<%= yield %>` tag.

```erb
<% tweet = Tweet.find(1) %>
<h1><%= tweet.status %></h1>
<p>Posted by <%= tweet.zombie.name %></p>
```

Rails Link Helper Methods
=========================

To create an anchor tag use the `link_to` method.

```erb
<%= link_to 'link text', 'url' %>
<%= link_to tweet.zombie.name, zombie_path(tweet.zombie) %>
```

shorter syntax -- rails know that we want to trigger the show_zombie view page, so we can pass the whole instance as the url.

```erb
<%= link_to text_to_show, model_instace %>
<%= link_to tweet.zombie.name, tweet.zombie %>
```

| Action          | Code             | The Url       |
|-----------------|------------------|---------------|
| List all tweets | `tweets_path`    | `/tweets`     |
| New tweet form  | `new_tweet_path` | `/tweets/new` |

These paths need a tweet: `tweet = Tweet.find(1)`

| Action          | Code                     | The Url         |
|-----------------|--------------------------|-----------------|
| Show a tweet    | `tweet`                  | `/tweets/1`     |
| Edit a tweet    | `edit_tweet_path(tweet)` | `/tweet/1/edit` |
| Delete a tweet  | `tweet, method: :delete` | `/tweets/1`     |


Looping in Erb
==============

Useful when there is a need to output the same kind of data in sequence.

```erb
<% Tweet.all.each do |tweet| %>
	<td><%= tweet.status %></td>
	<td><%= tweet.zombie.name %></td>
	<td><%= link_to "Edit", edit_tweet_path(tweet) %></td>
	<td><%= link_to "Destroy", tweet, method: :delete %></td>
<% end %>
```
Loops with conditiona

```erb
<% tweets = Tweet.all %>
<% tweets.each do |tweet| %>
	...
<% end %>
<% if tweets.size == 0 %>
	<em>No Tweets Found</em>
<% end %>
```