# NoSQL Database examples

## Data table

| pet_id | owner_name | species | breed        | birth_date | meds                         | vet_visits | tricks                   | shed_frequency | words_known                         | notes              |
| ------ | ---------- | ------- | ------------ | ---------- | ---------------------------- | ---------- | ------------------------ | -------------- | ----------------------------------- | ------------------ |
| 1      | Alice      | Dog     | Labrador     | 2020-05-10 | ["Heartgard"]                | 2          | ["Sit", "Stay", "Fetch"] | (none)         | (none)                              | Loves swimming     |
| 2      | Bob        | Cat     | Siamese      | 2022-01-15 | (none)                       | 1          | (none)                   | "Weekly"       | (none)                              | Indoor only        |
| 3      | Cara       | Parrot  | African Grey | 2018-03-12 | ["Vitamin drops"]            | (none)     | (none)                   | (none)         | ["Hello", "Pretty bird", "Bye-bye"] | Very talkative     |
| 4      | Deepa      | Snake   | Corn Snake   | 2021-10-05 | (none)                       | 3          | (none)                   | "Rarely"       | (none)                              | Eats frozen mice   |
| 5      | Evan       | Dog     | Beagle       | 2019-12-20 | ["Heartgard", "Flea collar"] | (none)     | ["Roll over"]            | (none)         | (none)                              | Friendly with kids |

## Key-Value Database

```
{
  "pet:1": {
    "owner_name": "Alice",
    "species": "Dog",
    "breed": "Labrador",
    "birth_date": "2020-05-10",
    "meds": ["Heartgard"],
    "vet_visits": 2,
    "tricks": ["Sit", "Stay", "Fetch"],
    "notes": "Loves swimming"
  },
  "pet:2": {
    "owner_name": "Bob",
    "species": "Cat",
    "breed": "Siamese",
    "birth_date": "2022-01-15",
    "shed_frequency": "Weekly",
    "notes": "Indoor only"
  },
  "pet:3": {
    "owner_name": "Cara",
    "species": "Parrot",
    "breed": "African Grey",
    "birth_date": "2018-03-12",
    "meds": ["Vitamin drops"],
    "words_known": ["Hello", "Pretty bird", "Bye-bye"],
    "notes": "Very talkative"
  },
  "pet:4": {
    "owner_name": "Deepa",
    "species": "Snake",
    "breed": "Corn Snake",
    "birth_date": "2021-10-05",
    "shed_frequency": "Rarely",
    "vet_visits": 3,
    "notes": "Eats frozen mice"
  },
  "pet:5": {
    "owner_name": "Evan",
    "species": "Dog",
    "breed": "Beagle",
    "birth_date": "2019-12-20",
    "meds": ["Heartgard", "Flea collar"],
    "tricks": ["Roll over"],
    "notes": "Friendly with kids"
  }
}

```

## Document Database

```
[
  {
    "pet_id": 1,
    "owner_name": "Alice",
    "species": "Dog",
    "breed": "Labrador",
    "birth_date": "2020-05-10",
    "meds": ["Heartgard"],
    "vet_visits": 2,
    "tricks": ["Sit", "Stay", "Fetch"],
    "notes": "Loves swimming"
  },
  {
    "pet_id": 2,
    "owner_name": "Bob",
    "species": "Cat",
    "breed": "Siamese",
    "birth_date": "2022-01-15",
    "shed_frequency": "Weekly",
    "notes": "Indoor only"
  },
  {
    "pet_id": 3,
    "owner_name": "Cara",
    "species": "Parrot",
    "breed": "African Grey",
    "birth_date": "2018-03-12",
    "meds": ["Vitamin drops"],
    "words_known": ["Hello", "Pretty bird", "Bye-bye"],
    "notes": "Very talkative"
  },
  {
    "pet_id": 4,
    "owner_name": "Deepa",
    "species": "Snake",
    "breed": "Corn Snake",
    "birth_date": "2021-10-05",
    "shed_frequency": "Rarely",
    "vet_visits": 3,
    "notes": "Eats frozen mice"
  },
  {
    "pet_id": 5,
    "owner_name": "Evan",
    "species": "Dog",
    "breed": "Beagle",
    "birth_date": "2019-12-20",
    "meds": ["Heartgard", "Flea collar"],
    "tricks": ["Roll over"],
    "notes": "Friendly with kids"
  }
]

```

## Column Family Database

```
Row key: 1
  info:owner_name      = "Alice"
  info:species         = "Dog"
  info:breed           = "Labrador"
  info:birth_date      = "2020-05-10"
  health:meds          = ["Heartgard"]
  health:vet_visits    = 2
  behavior:tricks      = ["Sit","Stay","Fetch"]
  meta:notes           = "Loves swimming"

Row key: 2
  info:owner_name      = "Bob"
  info:species         = "Cat"
  info:breed           = "Siamese"
  info:birth_date      = "2022-01-15"
  care:shed_frequency  = "Weekly"
  meta:notes           = "Indoor only"

Row key: 3
  info:owner_name      = "Cara"
  info:species         = "Parrot"
  info:breed           = "African Grey"
  info:birth_date      = "2018-03-12"
  health:meds          = ["Vitamin drops"]
  speech:words_known   = ["Hello","Pretty bird","Bye-bye"]
  meta:notes           = "Very talkative"

Row key: 4
  info:owner_name      = "Deepa"
  info:species         = "Snake"
  info:breed           = "Corn Snake"
  info:birth_date      = "2021-10-05"
  care:shed_frequency  = "Rarely"
  health:vet_visits    = 3
  meta:notes           = "Eats frozen mice"

Row key: 5
  info:owner_name      = "Evan"
  info:species         = "Dog"
  info:breed           = "Beagle"
  info:birth_date      = "2019-12-20"
  health:meds          = ["Heartgard","Flea collar"]
  behavior:tricks      = ["Roll over"]
  meta:notes           = "Friendly with kids"

```

## Graph database

### Nodes:

```

(:Owner {name:"Alice"})
(:Owner {name:"Bob"})
(:Owner {name:"Cara"})
(:Owner {name:"Deepa"})
(:Owner {name:"Evan"})

(:Pet {id:1, name:"Alice's Dog", species:"Dog", breed:"Labrador", birth_date:"2020-05-10", vet_visits:2, notes:"Loves swimming"})
(:Pet {id:2, name:"Bob's Cat", species:"Cat", breed:"Siamese", birth_date:"2022-01-15", shed_frequency:"Weekly", notes:"Indoor only"})
(:Pet {id:3, name:"Cara's Parrot", species:"Parrot", breed:"African Grey", birth_date:"2018-03-12", notes:"Very talkative"})
(:Pet {id:4, name:"Deepa's Snake", species:"Snake", breed:"Corn Snake", birth_date:"2021-10-05", shed_frequency:"Rarely", vet_visits:3, notes:"Eats frozen mice"})
(:Pet {id:5, name:"Evan's Dog", species:"Dog", breed:"Beagle", birth_date:"2019-12-20", notes:"Friendly with kids"})

(:Medication {name:"Heartgard"})
(:Medication {name:"Flea collar"})
(:Medication {name:"Vitamin drops"})

(:Trick {name:"Sit"})
(:Trick {name:"Stay"})
(:Trick {name:"Fetch"})
(:Trick {name:"Roll over"})

(:Word {text:"Hello"})
(:Word {text:"Pretty bird"})
(:Word {text:"Bye-bye"})

```

### Edges:

```
(:Owner {name:"Alice"}) -[:OWNS]-> (:Pet {id:1})
(:Owner {name:"Bob"})   -[:OWNS]-> (:Pet {id:2})
(:Owner {name:"Cara"})  -[:OWNS]-> (:Pet {id:3})
(:Owner {name:"Deepa"}) -[:OWNS]-> (:Pet {id:4})
(:Owner {name:"Evan"})  -[:OWNS]-> (:Pet {id:5})

(:Pet {id:1}) -[:TOOK_MED]-> (:Medication {name:"Heartgard"})
(:Pet {id:3}) -[:TOOK_MED]-> (:Medication {name:"Vitamin drops"})
(:Pet {id:5}) -[:TOOK_MED]-> (:Medication {name:"Heartgard"})
(:Pet {id:5}) -[:TOOK_MED]-> (:Medication {name:"Flea collar"})

(:Pet {id:1}) -[:LEARNED]-> (:Trick {name:"Sit"})
(:Pet {id:1}) -[:LEARNED]-> (:Trick {name:"Stay"})
(:Pet {id:1}) -[:LEARNED]-> (:Trick {name:"Fetch"})
(:Pet {id:5}) -[:LEARNED]-> (:Trick {name:"Roll over"})

(:Pet {id:3}) -[:KNOWS_WORD]-> (:Word {text:"Hello"})
(:Pet {id:3}) -[:KNOWS_WORD]-> (:Word {text:"Pretty bird"})
(:Pet {id:3}) -[:KNOWS_WORD]-> (:Word {text:"Bye-bye"})

```

