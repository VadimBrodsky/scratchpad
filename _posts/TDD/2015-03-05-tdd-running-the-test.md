---
title: "TDD: Running the Test" 
layout: post
category: TDD
date: 2015-03-05 22:42:02 
---

- To get the test to run need to add the Capybara DSL to the RSpec helper file.

```ruby
 # spec/spec_helper.rb
 RSpec.configure do |config|
   .
   .
   .
   config.include Capybara::DSL
 end
```

```bash
bundle exec rspec spec/requests/static_pages_spec.rb
bundle exec rspec spec
bundle exec rake spec
```