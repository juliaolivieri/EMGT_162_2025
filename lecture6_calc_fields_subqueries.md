# Lecture 6

## Calculated Fields

Create an attribute for the Customers relation that has the following separated by commas: cust_name, cust_address, cust_city, cust_state, cust_zip. Name the attribute “full_address”

```
SELECT cust_name || ", " || cust_address || ", " || cust_city || ", " || cust_state || ", " || cust_zip AS full_address
FROM Customers;
```
