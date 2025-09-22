# Lecture 8: Modifying data

```
INSERT INTO Customers
VALUES('1000000007',
					'Pacific Toys',
					'3601 Pacific Ave',
					'Stockton',
					'CA',
					'95211',
					'USA',
					'Julia Olivieri',
					'jolivieri@pacific.edu');


INSERT INTO Customers(cust_id,
     			      cust_name)					
VALUES('10000000078',
	   'Toys R Us');


INSERT INTO Customers(cust_id, cust_name, cust_address, cust_city, cust_state, cust_zip, cust_country, cust_contact, cust_email)
SELECT cust_id, cust_name, cust_address, cust_city, cust_state, cust_zip, cust_country, cust_contact, cust_email
FROM NewCustomers;

INSERT INTO Customers(cust_id, cust_name, cust_email)
SELECT prod_id, vend_id, prod_price
FROM Products;
```

Create new table

```
CREATE TABLE NewCustomers (
    cust_id      INT PRIMARY KEY,
    cust_name    VARCHAR(100),
    cust_address VARCHAR(150),
    cust_city    VARCHAR(50),
    cust_state   CHAR(2),
    cust_zip     VARCHAR(10),
    cust_country VARCHAR(50),
    cust_contact VARCHAR(100),
    cust_email   VARCHAR(100)
);

-- Insert new values
INSERT INTO NewCustomers (cust_id, cust_name, cust_address, cust_city, cust_state, cust_zip, cust_country, cust_contact, cust_email)
VALUES
(200000001, 'Happy Kids', '123 Rainbow Road', 'Orlando', 'FL', '32801', 'USA', 'Alice Brown', 'alice@happykids.com'),
(200000002, 'Toy Galaxy', '987 Star Lane', 'Houston', 'TX', '77002', 'USA', 'Robert King', 'robert@toygalaxy.com'),
(200000003, 'PlayWorld', '456 Fun Blvd', 'San Diego', 'CA', '92101', 'USA', 'Maria Lopez', 'maria@playworld.com'),
(200000004, 'Smart Toys', '654 Learning St', 'Boston', 'MA', '02108', 'USA', 'David Chen', 'dchen@smarttoys.com'),
(200000005, 'Adventure Toys', '321 Explorer Ave', 'Denver', 'CO', '80202', 'USA', 'Sophia Patel', 'sophia@adventuretoys.com');

```





