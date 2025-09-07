## SQL commands

### SELECT

```
-- Select query for a specific columns
SELECT column, another_column, …
FROM mytable;

-- Select query for all columns
SELECT * 
FROM mytable;
```

Examples:

```
SELECT prod_id, prod_name, prod_price
FROM Products;

SELECT *
FROM Products;
```

```
SELECT DISTINCT vend_id
FROM Products;
```

```
SELECT prod_name
FROM Products
LIMIT 5;

SELECT prod_name
FROM Products
LIMIT 5 OFFSET 5;
```

### WHERE

```
-- Select query with constraints
SELECT column, another_column, …
FROM mytable
WHERE condition
    AND/OR another_condition
    AND/OR …;


```
