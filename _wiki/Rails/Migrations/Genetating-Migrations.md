# Genetating Migrations


- Migrations reside in the `/db/migrate` folder of the Rails application.
- To generate a migration use the [[Rails Generate]] command.
- Migration names are written in camel case:

```bash
rails generate migration DoNothingYet
```

- Rails generates a new migration when a model is generated.