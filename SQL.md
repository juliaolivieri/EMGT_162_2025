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

Find the next five most expensive products:

```
SELECT *
FROM Products
ORDER BY prod_price DESC
LIMIT 5 OFFSET 5;
```

## WHERE

Find all products with a price of 3.49

```
SELECT *
FROM Products
WHERE prod_price = 3.49;
```

Find all products with a price less than 10, sorted by price

```
SELECT *
FROM Products
WHERE prod_price < 10
ORDER BY prod_price;
```

Find all products not made by vendor `DLL01`:

```
SELECT *
FROM Products
WHERE vend_id != "DLL01";
```

Another way

```
SELECT *
FROM Products
WHERE NOT vend_id = "DLL01";
```

Find all products with prices between 3.49 and 8.99 (inclusive)

```
SELECT *
FROM Products
WHERE prod_price BETWEEN 3.49 AND 8.99;
```

Find all customers without an email address in the database

```
SELECT *
FROM Customers
WHERE cust_email IS NULL;
```

Find products where the vendor id is `DLL01` and the price is less than or equal to 4

```
SELECT *
FROM Products
WHERE vend_id = "DLL01"
AND prod_price <= 4;
```

Find products where the vendor id is `DLL01` or `BRS01`

```
SELECT *
FROM Products
WHERE vend_id = "DLL01"
OR vend_id = "BRS01";
```

Do it another way

```
SELECT *
FROM Products
WHERE vend_id IN ("DLL01", "BRS01");
```

Find products where the vendor id is `DLL01` or `BRS01`, and the price is greater than or equal to 10

```
SELECT *
FROM Products
WHERE (vend_id = "DLL01"
OR vend_id = "BRS01")
AND prod_price >= 10;
```

Find products where the vendor id is `DLL01`, or the vendor id is `BRS01` and the price is greater than or equal to 10

```
SELECT *
FROM Products
WHERE vend_id = "DLL01"
OR (vend_id = "BRS01"
AND prod_price >= 10);
```

### Wildcard filtering

Find all products that start with the word "Fish"

```
SELECT *
FROM Products
WHERE prod_name LIKE "FISH%";
``` 

Find all products that include the phrase "bean bag"

```
SELECT *
FROM Products
WHERE prod_name LIKE "%bean bag%";
```

Find all products that begin with F and end with y

```
SELECT *
FROM Products
WHERE prod_name LIKE "F%y";
```

Find all products with names that end with "inch teddy bear"

```
SELECT *
FROM Products
WHERE prod_name LIKE "%inch teddy bear";
```

Find all products with names that match "__ inch teddy bear" (where underscore can be any character)

```
SELECT *
FROM Products
WHERE prod_name LIKE "__ inch teddy bear";
```

Find customers whos names start with J or M

```
SELECT *
FROM Customers
WHERE cust_contact LIKE "[JM]%";
```

## Aggregate Functions


