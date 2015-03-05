# Rails Parameters


Use the [[params hash]] to access the passed parameters.

```ruby
{ :controller => 'demo',
  :action => 'hello',
  :id => 1,
  :page => 3,
  :name => 'vadim' }
```

The `id` is special because is is part of the [[Default Route]] and positioned on the right side of the `?`.