# ActiveRecord::Base


- ActiveRecord uses conventions in the file / table names as per [[Generating Models]].
- ActiveRecord also gives attributes to every column in the table, no need to write `attr_accessor`.

Define a configuration for a different table name:

```ruby
self.table_name = "admin_users"
```