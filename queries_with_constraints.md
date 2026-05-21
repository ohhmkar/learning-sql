# Queries with Constraints

In order to filter certain results from being returned, we need to use a WHERE clause in the query. The clause is applied to each row of data by checking specific column values to determine whether it should be included in the results or not.

```SQL
SELECT column, another_column, …
FROM mytable
WHERE condition
    AND/OR another_condition
    AND/OR …;
```

More complex clauses can be constructed by joining numerous AND or OR logical keywords (ie. num_wheels >= 4 AND doors <= 2). And below are some useful operators that you can use for numerical data (ie. integer or floating point):

| Operator            | Condition                                            | SQL Example                   |
| ------------------- | ---------------------------------------------------- | ----------------------------- |
| =, !=, <, <=, >, >= | Standard numerical operators                         | col_name != 4                 |
| BETWEEN … AND …     | Number is within range of two values (inclusive)     | col_name BETWEEN 1.5 AND 10.5 |
| NOT BETWEEN … AND … | Number is not within range of two values (inclusive) | col_name NOT BETWEEN 1 AND 10 |
| IN (…)              | Number exists in a list                              | col_name IN (2, 4, 6)         |
| NOT IN (…)          | Number does not exist in a list                      | col_name NOT IN (1, 3, 5)     |

When writing WHERE clauses with columns containing text data, SQL supports a number of useful operators to do things like case-insensitive string comparison and wildcard pattern matching. We show a few common text-data specific operators below:

| Operator   | Condition                                                                                             | Example                                                               |
| ---------- | ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| =          | Case sensitive exact string comparison (notice the single equals)                                     | col_name = "abc"                                                      |
| != or <>   | Case sensitive exact string inequality comparison                                                     | col_name != "abcd"                                                    |
| LIKE       | Case insensitive exact string comparison                                                              | col_name LIKE "ABC"                                                   |
| NOT LIKE   | Case insensitive exact string inequality comparison                                                   | col_name NOT LIKE "ABCD"                                              |
| %          | Used anywhere in a string to match a sequence of zero or more characters (only with LIKE or NOT LIKE) | col_name LIKE "%AT%"<br>(matches "AT", "ATTIC", "CAT" or even "BATS") |
| \_         | Used anywhere in a string to match a single character (only with LIKE or NOT LIKE)                    | col*name LIKE "AN*"<br>(matches "AND", but not "AN")                  |
| IN (…)     | String exists in a list                                                                               | col_name IN ("A", "B", "C")                                           |
| NOT IN (…) | String does not exist in a list                                                                       | col_name NOT IN ("D", "E", "F")                                       |
