## The relationship between entries, items and records

Registers are made up of:

* entries
* items
* records

Entries contain metadata about what and when data has changed. 

Each entry in a register has a relationship with one item, which contains data. An item is connected to an entry with an item hash.   

Records represent things that change over time. Records are identifiable by keys and correspond to the latest entry for a particular key, as indicated by the entry number.

### A worked example

The `country` register, and one of its keys, ‘CI’, provides a useful example. 

Using the `GET /entries/{entry-number}` where `{entry-number}` is '90' returns the [90th entry to the `country` register](https://country.register.gov.uk/entries/90.json), which contains metadata. Using the `GET /items/{item-hash}` endpoint on that entry's item hash returns [the corresponding item](https://country.register.gov.uk/items/sha-256:7c16257bd45b4716914010b39dd40e5a6b985b8928d7b8bb0fe3005d2f2b0fec.json), which reveals that the `official-name` field for the item is ‘The Republic of Cote D’Ivoire’. 

The more recent [207th entry to the `country` register](https://country.register.gov.uk/entries/207.json) also relates to the key ‘CI’. However, this time the item hash addresses to an item that reveals that the `official-name` field for [the corresponding item](https://country.register.gov.uk/items/sha-256:b3ca21b3b3a795ab9cd1d10f3d447947328406984f8a461b43d9b74b58cccfe8.json) is ‘The Republic of Côte D’Ivoire’. The need to change the accent above the ‘o’ required a new entry to the register.

Using the `GET /records/{key}` endpoint returns the most recent entry to the register for a given `{key}`, with the item data already resolved. For example, `GET /records/CI` returns the [207th entry and its corresponding item]( https://country.register.gov.uk/records/CI.json). 

Using the `GET /records/CI/entries` endpoint [returns all entries for the key 'CI'](https://country.register.gov.uk/records/CI/entries.json), meaning both the 90th and the 207th entries. 

