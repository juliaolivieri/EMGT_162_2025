# NoSQL Exercise

We will consider how to represent the information in this table using the different NoSQL database types:

| customer_id | name  | email                                   | phone    | last_purchase | cart_items          | support_tickets | loyalty_points | notes                                |
| ----------- | ----- | --------------------------------------- | -------- | ------------- | ------------------- | --------------- | -------------- | ------------------------------------ |
| 1           | Alice | [alice@site.com](mailto:alice@site.com) | 555-1234 | 2025-09-10    | [“Headphones”]      | 2               | 320            | (none)                               |
| 2           | Bob   | (none)                                  | (none)   | (none)        | []                  | (none)          | (none)         | “Browsed site once, no account.”     |
| 3           | Cara  | [cara@site.com](mailto:cara@site.com)   | 555-7890 | 2025-09-20    | [“Laptop”, “Mouse”] | (none)          | 500            | “VIP customer, follow-up via email.” |
| 4           | Deepa | [deepa@shop.co](mailto:deepa@shop.co)   | (none)   | 2025-09-01    | [“Coffee Maker”]    | 1               | (none)         | (none)                               |


1. Represent as key-value database.
2. Represent as Document database.
3. Represent as Column-family database.
4. Represent as Graph database (you can just write out a few of the nodes and relationships).
5. Which do you think makes the most sense for this data?
