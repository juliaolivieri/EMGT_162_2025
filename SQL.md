# SQL commands

Find all the information about each product

## SELECT

```
SELECT *
FROM Products;
```

Find the name and price of each product

```
SELECT prod_price, prod_name
FROM Products;
```

### DISTINCT 

List the distinct vendors that the products come from

```
SELECT DISTINCT vend_id
FROM Products;
```

Find every unique combination of vendor and price



```
SELECT DISTINCT vend_id, prod_price
FROM Products;
```

### ORDER BY

Find an alphabetically sorted list of products:

```
SELECT prod_name
FROM Products
ORDER BY prod_name;
```

Sort just the product names by price

```
SELECT prod_name
FROM Products
ORDER BY prod_price;
```

Sort all product information by vendor id, then product price

```
SELECT *
FROM Products
ORDER BY vend_id, prod_price;
```

Sort all product information by product price in descending order

```
SELECT *
FROM Products
ORDER BY prod_price DESC;
```

Sort all product information by vend id in ascending order, then product price in descending order

```
SELECT *
FROM Products
ORDER BY vend_id, prod_price DESC;
```

### LIMIT/OFFSET

Find the five most expensive products

```
SELECT *
FROM Products
ORDER BY prod_price DESC
LIMIT 5;
```

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


