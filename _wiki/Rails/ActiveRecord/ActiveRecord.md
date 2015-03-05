# ActiveRecord


- active record: a design pattern for relational databases.
- ActiveRecord: the Rails implementation of active record pattern.
- Retreive and manipulate data as objects, not as static row.

## Active record objects are intelligent

1. Understand the structure of the table.
2. Contain data from table rows.
3. Know how to create, read, update, and delete rows.
4. Can be manipulated as objects, then saved easily.

```ruby
user = User.new
user.first_name = "Joe"
user.save # SQL INSERT

user.last_name = "Smith"
user.save # SQL UPDATE

user.delete # SQL DELETE
```