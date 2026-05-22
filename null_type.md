# Managing NULL Values

## NULL values in an SQL database

It's always good to reduce the possibility of `NULL` values in databases because they require special attention when constructing queries, evaluating constraints (certain functions behave differently with null values), and when processing the results.

An alternative to `NULL` values in your database is to have data-type appropriate default values, like `0` for numerical data, empty strings for text data, etc. But if your database needs to store incomplete data, then `NULL` values can be appropriate if the default values will skew later analysis (for example, when taking averages of numerical data).

Sometimes, it's also not possible to avoid `NULL` values, as we saw when outer-joining two tables with asymmetric data. In these cases, you can test a column for `NULL` values in a `WHERE` clause by using either the `IS NULL` or `IS NOT NULL` constraint.

```sql
-- Select query with constraints on NULL values
SELECT column, another_column
FROM mytable
WHERE column IS NOT NULL
  AND another_condition;
```
