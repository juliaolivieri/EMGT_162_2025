# Lecture 10

## Aliases

```
SELECT cust_name, cust_contact
FROM Customers AS C
INNER JOIN Orders AS O
ON C.cust_id = O.cust_id
INNER JOIN OrderItems AS OI
ON O.order_num = OI.order_num
WHERE OI.prod_id = 'RGAN01';
```

## Self joins
```
-- Approach without self join

SELECT cust_name, cust_contact
FROM Customers
WHERE cust_name = (SELECT cust_name
											FROM Customers
											WHERE cust_contact = 'Jim Jones');

-- Approach with self join

SELECT c1.cust_name, c1.cust_contact
FROM Customers AS c1
INNER JOIN Customers AS c2
ON c1.cust_name = c2.cust_name
WHERE c2.cust_contact = 'Jim Jones';

```

## Left joins

```
-- Count how many orders were placed by each customer, including customers that have yet to place an order

SELECT cust_name, COUNT(order_num) AS num_orders
FROM Customers
LEFT JOIN Orders
ON Customers.cust_id = Orders.cust_id
GROUP BY cust_name
ORDER BY num_orders DESC;

-- List all products with order quantities, including products not ordered by anyone

SELECT prod_name, COUNT(order_num) AS num_orders
FROM Products
LEFT JOIN OrderItems
ON Products.prod_id = OrderItems.prod_id
GROUP BY prod_name
ORDER BY num_orders DESC;
```

