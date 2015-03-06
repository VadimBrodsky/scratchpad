---
title: "Rails Console" 
layout: post
category: rails
date: 2015-03-05 22:07:41 
---

- Rails comes with a modified version of IRB.
- It has access to all of Rails methods and the app database.
- By default it start in the development environment.
- To start the console in a sandbox use the `--sandbox` flag, all changes will be rolled back on exit.

```bash
rails console
rails c
```

```bash
rails console --sandbox
```

```bash
rails console production
```