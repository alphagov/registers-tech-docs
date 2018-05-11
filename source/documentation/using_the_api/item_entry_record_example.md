## The entry/item/record relationship

An **entry** expresses a change in a register. For example, using the `GET /entries` endpoint for the `country` register will return all entries there have ever been to that register. The very [first entry to the `country` register](https://country.register.gov.uk/entries/1.json) introduced a change for the **primary key** ‘SU’, corresponding to the country of the USSR. 

Each entry in a register has a relationship with one **item**, which contains actual data. This relationship is expressed through the **item hash**, which addresses to a specific item. **Records** are identifiable by primary keys and correspond to the latest entry for a particular key, as indicated by the entry number.

### A worked example

The `country` register, and one of its primary keys, ‘CI’, provides a useful example. 

Using the `GET /items/{item-hash}` endpoint on the [90th entry to the `country` register](https://country.register.gov.uk/entries/90.json) returns the item, which reveals that the `official-name` field for this entry is “The Republic of Cote D’Ivoire”. Looking much later, the [207th entry to the `country` register](https://country.register.gov.uk/entries/207.json)  also relates to the primary key ‘CI’. However, this time the item hash addresses to an item that reveals that the `official-name` field for the corresponding item is “The Republic of Côte D’Ivoire”, and has a correction to an accent above the ‘o’.

Following the example above, using the `GET /records/{field-value}` endpoint for ‘CI’ [indicates the later spelling](https://country.register.gov.uk/records/CI.json) (“The Republic of Côte D’Ivoire”), because the record currently corresponds to the 207th entry to the `country` register, which is more recent than the 90th entry. 

Using the `GET /records/{field-value}` endpoint, where `{field-value}` is ‘CI’, [returns the record for ‘CI’, where the data is presented with the item already resolved](https://country.register.gov.uk/records/CI/.json). That is, the data is expressed as a function of the latest entry, which in this case is the 207th. Using the `GET /records/{field-value}/entries` endpoint, where `{field-value}` is again ‘CI’, [returns both the 90th and the 207th entries](https://country.register.gov.uk/records/CI/entries.json). 

To summarise this:

* entries contain metadata about what and when data has changed
* items contain actual data
* item hashes are unique for given items, and link given items and entries
* records correspond to the latest entry for a particular primary key 
