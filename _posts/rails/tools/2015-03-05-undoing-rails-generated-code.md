---
title: "Undoing Rails Generated Code" 
layout: post
category: rails
date: 2015-03-05 22:11:05 
---

```bash
rails generate controller FooBarz baz qux
rails destroy controller Foobarz
```

```bash
rails generate model Foo bar:string baz:integer
rails destroy model Foo
```

```bash
rake db:migrate
rake db:rollback
rake db:migrate VERSION=0
```