Open registers are made up of items, entries and records.

### Items

Items are made up of fields and values containing information. They are the actual data contained within a register. For example, in the record for Great Britain in the country register, an item would be its country name, 'Great Britain' and its official citizen name, 'Brits'.

Items are connected to entries with an item hash, an algorithm that maps data of arbitrary size to a byte string of fixed size. A hash is unique to its item and no item will have the same item-hash as another item, unless the item contains exactly the same information. For example, in the country register the item hash `sha-256:d97d6b34bc572e334cbd7898f785b72947557d9dbea59977077f231274259f3b` links that item with entry 195, which in turn is tied to the record for Vatican City.

### Entries

Entries are the metadata which describes how a register evolves over time. They describe how and when items were introduced to the register.

For example, if a country changed its name, the country register would be updated. An entry would be created to point to the item with the new information. This entry would then describe the date/time and position of that item (with new name) in the register. That entry would become the current version of the record for that country. Older entries are also kept to show a history of a record. Entries are ordered by when they were added to a register.

Each register uses an unique identifier, which is a unique field only used in that register. It appears in every entry and always has the same name as the name of the register. It is used to tie entries to records.

### Records

Records are the current version of the register. For example, the country register contains 199 records, each up to date with the latest information of the 199 countries recognised by the Foreign and Commonwealth Office.
