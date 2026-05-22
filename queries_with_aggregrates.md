# Queries with Aggregates

SQL also supports the use of aggregate expressions (or functions) that allow you to summarize information about a group of rows of data.

```sql
-- Select query with aggregate functions over all rows
SELECT AGG_FUNC(column_or_expression) AS aggregate_description
FROM mytable
WHERE constraint_expression;
```

| Function                      | Description                                                                                                                                                                                     |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `COUNT(*)` or `COUNT(column)` | A common function used to count the number of rows in the group if no column name is specified. Otherwise, counts the number of rows in the group with non-NULL values in the specified column. |
| `MIN(column)`                 | Finds the smallest numerical value in the specified column for all rows in the group.                                                                                                           |
| `MAX(column)`                 | Finds the largest numerical value in the specified column for all rows in the group.                                                                                                            |
| `AVG(column)`                 | Finds the average numerical value in the specified column for all rows in the group.                                                                                                            |
| `SUM(column)`                 | Finds the sum of all numerical values in the specified column for the rows in the group.                                                                                                        |

## Grouped Aggregate Functions

In addition to aggregating across all the rows, you can instead apply the aggregate functions to individual groups of data within that group (i.e. box office sales for Comedies vs Action movies).
This would then create as many results as there are unique groups defined by the `GROUP BY` clause.

```sql
-- Select query with aggregate functions over groups
SELECT AGG_FUNC(column_or_expression) AS aggregate_description
FROM mytable
WHERE constraint_expression
GROUP BY column;
```

The `GROUP BY` clause works by grouping rows that have the same value in the column specified.
