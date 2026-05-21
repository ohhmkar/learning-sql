# Learning SQL

### SELECT

#### Selecting all elements

```SQL
SELECT * FROM table_name;
```

#### Specific columns

```SQL
SELECT column1, column2, column3
FROM table_name;
```

#### Unique rows in columns

```SQL
SELECT column_name FROM table_name; --- this is selecting all genres

SELECT DISTINCT column_name FROM table_name --- this is selecting unqiue genres
```

##### Example Usage

```SQL
SELECT * from shows;

SELECT name, genre
FROM shows;
```

### WHERE

> [!NOTE]  
> The `WHERE` keyword always goes after the `FROM` part of the query.

Comparison operators:

1. `=` equal to
2. `=` not equal to
3. `>` greater than
4. `<` less than
5. `>=` greater than or equal to
6. `<=` less than or equal to

```SQL
--- Example
select * from shows where tomatometer < 60
```

### LIKE

The `LIKE` operator can be used to search for a pattern in a column. It’s used in the `WHERE` clause:

The `%` can be used in different ways:

`A%` matches values that begin with letter 'A'.

`%z` matches values that end with 'z'.

We can also use `%` both before and after a pattern:

```SQL
SELECT *
FROM shows
WHERE name LIKE '%the%';
```

Here, any show that contains the word "the" in its name will be returned.

### BETWEEN

The `BETWEEN` operator is used in a `WHERE` clause to filter the result set within a certain range. The range must be separated by an `AND` keyword.

> [!TIP]
> For example, this query filters the result to only include shows between the years 2020 and 2025 (inclusive):

```SQL
SELECT *
FROM shows
WHERE year
BETWEEN 2020 AND 2025;
```

In this statement, `BETWEEN` filters the result to only include shows with names that begin with the letter 'A' up to 'D':

```SQL
SELECT *
FROM shows
WHERE name
BETWEEN 'A' AND 'D';
```

### ORDER BY

The `ORDER BY` statement sorts rows of data in ascending or descending order. By default, this command sorts the data in ascending order.

```SQL
SELECT name, genre, stream, year
FROM shows
ORDER BY year;
```

This results into selecting 4 columns from our table but if you look closely, the `year` column is sorted into ascending order.

It will look something like:

| name             | genre       | stream      | year |
| ---------------- | ----------- | ----------- | ---- |
| Sex and the City | Drama       | HBO         | 1998 |
| The Sopranos     | Crime Drama | HBO         | 1999 |
| One Piece        | Anime       | Crunchyroll | 1999 |
| Bleach           | Anime       | Crunchyroll | 2004 |

Let’s say we want to get all the latest shows this time, we will have to sort the `year` column into descending order using the `DESC` command:

```SQL
SELECT name, genre, stream, year
FROM shows
ORDER BY year DESC;
```

It will look something like:

| name             | genre          | stream  | year |
| ---------------- | -------------- | ------- | ---- |
| The Last of Us   | Thriller Drama | HBO     | 2023 |
| Tokyo Vice       | Crime Drama    | HBO     | 2022 |
| Wednesday        | Black Comedy   | Netflix | 2022 |
| The Bear         | Drama          | Hulu    | 2022 |
| Band of Brothers | War Drama      | HBO     | 2022 |
