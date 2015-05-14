---
title: "Changing the Version of Rails" 
layout: post
category: rails
date: 2015-03-05 22:07:10 
---

To change the version of rails:

- Generate a new app with `new`.
- Change the Rails gem version in the `Gemfile`.
- Run `rake rails:update`.
- Overwrite the conflicting files.

```bash
rails new my_app
bundle install
rake rails:update
```