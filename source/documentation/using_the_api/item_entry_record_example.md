## The relationship between entries, items and records

Registers are made up of:

entries
items
records

Entries contain metadata about what and when data has changed. 

Each entry in a register has a relationship with one item, which contains data. An item is connected to an entry with an item hash.   

Records represent things that change over time. Records are identifiable by keys and correspond to the latest entry for a particular key, as indicated by the entry number.

### A worked example

The `country` register, and one of its keys, ‘CI’, provides a useful example. 

Using the `GET /items/{item-hash}` endpoint on the [90th entry to the `country` register](https://country.register.gov.uk/entries/90.json) returns the item, which reveals that the `official-name` field for this entry is ‘The Republic of Cote D’Ivoire’. 

The more recent [207th entry to the `country` register](https://country.register.gov.uk/entries/207.json) also relates to the key ‘CI’. However, this time the item hash addresses to an item that reveals that the `official-name` field for the corresponding item is ‘The Republic of Côte D’Ivoire’. The change to the accent above the ‘o’ required a new entry to the register.

Using the `GET /records/{key}` endpoint will return the most recent entry. For example, 'GET /records/CI` returns the 207th entry. 

Using the `GET /records/CI/entries` endpoint will return both the 90th and the 207th entries. Using the `GET /entries` endpoint will return all the entries there have ever been. 

