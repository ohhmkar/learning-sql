# Filtering and Sorting

## Distinct Values

SQL provides a convenient way to discard rows that have a duplicate column value by using the `DISTINCT` keyword.

> [!TIP]
> Select query with unique results

```sql
SELECT DISTINCT column, another_column
FROM mytable
WHERE condition(s);
```

## Ordering Results

> [!TIP]
> Select query with ordered results

```sql
SELECT column, another_column
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC;
```

## Limiting Results to a Subset

Another clause which is commonly used with the `ORDER BY` clause are the `LIMIT` and `OFFSET` clauses, which are a useful optimization to indicate to the database the subset of the results you care about.
The `LIMIT` will reduce the number of rows to return, and the optional `OFFSET` will specify where to begin counting the number rows from.

> [!NOTE]
> Select query with limited rows

```sql
SELECT column, another_column
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;
```
