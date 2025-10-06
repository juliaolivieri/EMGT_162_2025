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
  info:owner_name = "Alice"
  info:species = "Dog"
  health:meds = ["Heartgard"]
  behavior:tricks = ["Sit", "Stay", "Fetch"]
  meta:notes = "Loves swimming"

Row key: 2
  info:owner_name = "Bob"
  info:species = "Cat"
  care:shed_frequency = "Weekly"
  meta:notes = "Indoor only"

Row key: 3
  info:owner_name = "Cara"
  info:species = "Parrot"
  health:meds = ["Vitamin drops"]
  speech:words_known = ["Hello", "Pretty bird", "Bye-bye"]
  meta:notes = "Very talkative"

```

## Graph database

### Nodes:

```
(:Owner {name:"Alice"})
(:Pet {species:"Dog", breed:"Labrador"})
(:VetVisit {id:501, date:"2025-09-10"})
(:Medication {name:"Heartgard"})
(:Trick {name:"Fetch"})
(:Pet {species:"Parrot", name:"Cara’s Parrot"})

```

### Edges:

```
(:Owner {name:"Alice"}) -[:OWNS]-> (:Pet {species:"Dog"})
(:Pet {species:"Dog"}) -[:TOOK_MED]-> (:Medication {name:"Heartgard"})
(:Pet {species:"Dog"}) -[:LEARNED]-> (:Trick {name:"Fetch"})
(:Owner {name:"Cara"}) -[:OWNS]-> (:Pet {species:"Parrot"})
(:Pet {species:"Parrot"}) -[:KNOWS_WORD]-> (:Word {text:"Hello"})

```
