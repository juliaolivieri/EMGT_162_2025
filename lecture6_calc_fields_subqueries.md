# Lecture 6

## Calculated Fields

Create an attribute for the Customers relation that has the following separated by commas: cust_name, cust_address, cust_city, cust_state, cust_zip. Name the attribute “full_address”

```
SELECT cust_name || ", " || cust_address || ", " || cust_city || ", " || cust_state || ", " || cust_zip AS full_address
FROM Customers;
```

The toy store is having a 50% off sale. Output each product name and the new discounted price, sorted by the discounted price.

```
SELECT prod_name, 0.5 * prod_price AS discounted_price
FROM Products
ORDER BY discounted_price;
```

Imagine the toy store buys each product from the vendor for 0.7 * prod_price, and sells it for prod_price. Create an attribute called “profit_margin” that shows the profit the company makes on each product.

```
SELECT prod_name, prod_price - 0.7 * prod_price AS profit_margin
FROM Products;
```

## Subqueries

Find the names of all products with the minimum price

```
SELECT *
FROM Products
WHERE prod_price = (SELECT MIN(prod_price)
											FROM Products);
```

Find the names of all products whose vendors are in the US

```
SELECT *
FROM Products
WHERE vend_id IN (SELECT vend_id
											FROM Vendors
											WHERE vend_country = "USA");
```

Find the names of all products in order 20007

```
SELECT *
FROM Products
WHERE prod_id IN (SELECT prod_id
											FROM OrderItems
											WHERE order_num = 20007);
```


