# Exploratory Data Analysis in SQL

## step 1: see the ER diagram to know the what are the tables, their columns and their relationships (primary keys, foregin keys, one to one or one to many...)
## step 2: check the datatype and rows numbers.
    df.head() => SELECT * FROM table_name LIMIT 5;
## step 3: knowing how many null values in the table
    SELECT count(*) - count(col_name) AS missing
        FROM table_name

 Reminder:
| Code | Note   |
|------|--------|
| NULL | missing|
| IS NULL, IS NOT NULL | don't use = NULL|
|count(*) | number of rows|
|count(col_name) | number of non-NULL values|
|count(DISTINCT col_name) | number of different non-NULL values|
|SELECT DISTINCT col_name | distinct valuesm, including NULL|

### Imputation method in SQL: coalesce
- Operates row by row
- Returns first non-NULL value

Idea: add a second column with data to imputate the null values and then use the coalesce function

coalesce(col_1, col_2, fallback_value)
e.g. coalesce(industry, sector, 'Unknown') AS industry2 (usually keep the original col)


### Typecasting
```Python

```

```SQL
SELECT CAST (value AS new_type);
```



### Join tables

#### Merging:
```Python
df_merged = pd.merge(df1, df2, on='key_col', how='inner')
```
```sql
SELECT
    col(s)
FROM df1 INNER JOIN df2
ON df1.key = df2.key
```

#### Concatenating:
```Python

```






#### Groupby
```Python
df.groupby(["col_name_1"])["col_name_2"].sum() / .count() ...
```

```SQL
SELECT COUNT(col_name_2), col_name_1
FROM table_name
GROUP BY col_name_1;
```

