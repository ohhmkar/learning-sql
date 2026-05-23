# Alter

### Adding columns

The syntax for adding a new column is similar to the syntax when creating new rows in the CREATE TABLE statement.

You need to specify the data type of the column along with any potential table constraints and default values to be applied to both existing and new rows. In some databases like MySQL, you can even specify where to insert the new column using the FIRST or AFTER clauses, though this is not a standard feature.

```sql
--- Altering table to add new column(s)
ALTER TABLE mytable
ADD column DataType OptionalTableConstraint
    DEFAULT default_value;
```

### Removing columns

Dropping columns is as easy as specifying the column to drop, however, some databases (including SQLite) don't support this feature. Instead you may have to create a new table and migrate the data over.

```sql
--- Altering table to remove column(s)
ALTER TABLE mytable
DROP column_to_be_deleted;
```

### Renaming table

```sql
--- Altering table name
ALTER TABLE mytable
RENAME TO new_table_name;
```

# Drop

In some rare cases, you may want to remove an entire table including all of its data and metadata, and to do so, you can use the DROP TABLE statement, which differs from the DELETE statement in that it also removes the table schema from the database entirely.

```sql
-- Drop table statement
DROP TABLE IF EXISTS mytable;
```
