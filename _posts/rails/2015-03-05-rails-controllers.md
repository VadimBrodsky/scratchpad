---
title: "Rails Controllers" 
layout: post
category: rails
date: 2015-03-05 22:26:57 
---

When the action is empty Rails will render the corresponding view by default. This action can by specified explicitly by the [[Controller Action to Render Template]]

```ruby
def hello
end
```

```ruby
def show
  @user = User.find(params[:id])
end
```