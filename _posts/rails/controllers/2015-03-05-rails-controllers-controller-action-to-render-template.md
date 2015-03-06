---
title: "Rails Controllers: Controller Action to Render Template" 
layout: post
category: rails
date: 2015-03-05 22:28:20 
---

By default the Rails behavious the controller will look for a template with the same name as the action.

```ruby
def hello
end
```

This can also be done more explicitly:

```ruby
def index
  render(:template => 'demo/hello')
end
```

Or using a shorthand:

```ruby
def index
  render('demo/hello')
end
```

Rails can also assume the correct folder based on the controller name, for example `DemoController` would assume that the corresponding views will be under the `/app/views/demo/` folder.

```ruby
def index
  render('hello')
end
```