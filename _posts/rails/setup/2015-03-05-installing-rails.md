---
title: "Installing Rails" 
layout: post
category: rails
date: 2015-03-05 22:05:15 
---

1. Installing Rails
2. Install Bundler gem first.
3. Rehash the rbenv environment to load bundler.
4. Install the Rails gem.
5.
  - Optionally install without docs: `--no-ri --no-rdoc`
  - Install a specific version: `--version 4.0.0`
6. Install the MySQL gem.

```bash
gem install bundler
rbenv rehash
bundle -v
gem install rails
rbenv rehash
rails -v
gem install mysql2
```