# Migration Methods: Index Migration


## Add index

- Can also send an array of columns to add indexes to multiple columns.
- [[Index options|Migration File: Index Column Options]] are different than column options.
- Should always add index to all [[foreign keys|DB Terms: Foreign Key]].
- Should add index to columns that are used frequently to look up records, like username.

```ruby
add_index(table, column, options)
```

## Remove index:

```ruby
remove_index(table, column)
```