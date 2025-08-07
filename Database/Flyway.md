Flyway updates a database from one version to the next using migrations. 

Migrations can be written in SQL with database-specific syntax, or in Java for advanced database transformations.

Migrations can be versioned or repeatable. Versioned has a unique version and is applied exactly once. Repeatable doesn't have a version. They're reapplied every time their checksum changes.

Within a single migration run, repeatable migrations are always applied last, after pending versioned migrations have been executed.

Repeatable migrations are applied in order of their description. For a single migration, all statements are run within a single database transaction.

This tutorial uses flyway Maven Plugin

```
```