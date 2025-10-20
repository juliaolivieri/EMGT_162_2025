# Lecture 12 exercise solutions

| customer_id | name  | email                                   | phone    | last_purchase | cart_items          | support_tickets | loyalty_points | notes                                |
| ----------- | ----- | --------------------------------------- | -------- | ------------- | ------------------- | --------------- | -------------- | ------------------------------------ |
| 1           | Alice | [alice@site.com](mailto:alice@site.com) | 555-1234 | 2025-09-10    | [“Headphones”]      | 2               | 320            | (none)                               |
| 2           | Bob   | (none)                                  | (none)   | (none)        | []                  | (none)          | (none)         | “Browsed site once, no account.”     |
| 3           | Cara  | [cara@site.com](mailto:cara@site.com)   | 555-7890 | 2025-09-20    | [“Laptop”, “Mouse”] | (none)          | 500            | “VIP customer, follow-up via email.” |
| 4           | Deepa | [deepa@shop.co](mailto:deepa@shop.co)   | (none)   | 2025-09-01    | [“Coffee Maker”]    | 1               | (none)         | (none)                               |

## Key-value Database

```
{
  "customer:1": {
    "name": "Alice",
    "email": "alice@site.com",
    "phone": "555-1234",
    "last_purchase": "2025-09-10",
    "cart_items": ["Headphones"],
    "support_tickets": 2,
    "loyalty_points": 320
  },
  "customer:2": {
    "name": "Bob",
    "notes": "Browsed site once, no account."
  },
  "customer:3": {
    "name": "Cara",
    "email": "cara@site.com",
    "phone": "555-7890",
    "cart_items": ["Laptop", "Mouse"],
    "loyalty_points": 500,
    "notes": "VIP customer, follow-up via email."
  },
  "customer:4": {
    "name": "Deepa",
    "email": "deepa@shop.co",
    "last_purchase": "2025-09-01",
    "cart_items": ["Coffee Maker"],
    "support_tickets": 1
  }
}

```

## Document Database

```
[
  {
    "customer_id": 1,
    "name": "Alice",
    "email": "alice@site.com",
    "phone": "555-1234",
    "last_purchase": "2025-09-10",
    "cart_items": ["Headphones"],
    "support_tickets": 2,
    "loyalty_points": 320
  },
  {
    "customer_id": 2,
    "name": "Bob",
    "notes": "Browsed site once, no account."
  },
  {
    "customer_id": 3,
    "name": "Cara",
    "email": "cara@site.com",
    "phone": "555-7890",
    "last_purchase": "2025-09-20",
    "cart_items": ["Laptop", "Mouse"],
    "loyalty_points": 500,
    "notes": "VIP customer, follow-up via email."
  },
  {
    "customer_id": 4,
    "name": "Deepa",
    "email": "deepa@shop.co",
    "last_purchase": "2025-09-01",
    "cart_items": ["Coffee Maker"],
    "support_tickets": 1
  }
]
```

## Column-Family Store

```
Row key: 1
  info:name = "Alice"
  info:email = "alice@site.com"
  info:phone = "555-1234"
  purchases:last_purchase = "2025-09-10"
  purchases:cart_items = ["Headphones"]
  support:tickets = 2
  loyalty:points = 320

Row key: 2
  info:name = "Bob"
  notes:text = "Browsed site once, no account."

Row key: 3
  info:name = "Cara"
  info:email = "cara@site.com"
  purchases:last_purchase = "2025-09-20"
  purchases:cart_items = ["Laptop", "Mouse"]
  loyalty:points = 500
  notes:text = "VIP customer, follow-up via email."

Row key: 4
  info:name = "Deepa"
  purchases:cart_items = ["Coffee Maker"]
  support:tickets = 1

```

## Graph Database

### Nodes

```
(:Customer {name:"Alice", email:"alice@site.com"})
(:Product {name:"Headphones"})
(:Ticket {id:201})
(:Customer {name:"Cara"})
(:Product {name:"Laptop"})
(:Product {name:"Mouse"})
(:Customer {name:"Deepa"})
(:Product {name:"Coffee Maker"})

```

### Edges

```
(:Customer {name:"Alice"}) -[:PURCHASED {date:"2025-09-10"}]-> (:Product {name:"Headphones"})
(:Customer {name:"Cara"}) -[:ADDED_TO_CART]-> (:Product {name:"Laptop"})
(:Customer {name:"Cara"}) -[:ADDED_TO_CART]-> (:Product {name:"Mouse"})
(:Customer {name:"Deepa"}) -[:PURCHASED]-> (:Product {name:"Coffee Maker"})
(:Customer {name:"Alice"}) -[:HAS_TICKET]-> (:Ticket {id:201})
(:Customer {name:"Deepa"}) -[:HAS_TICKET]-> (:Ticket {id:202})

```
