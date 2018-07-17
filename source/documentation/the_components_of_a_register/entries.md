### Entries

Entries contain metadata about what and when data has changed. 

Entries contain the properties `entry-number`,  `entry-timestamp`, `item-hash`
and `key`. 

The entry number is unique and defines an entry’s position within the ordered
list of changes. The entry timestamp is the time when an entry was introduced
to a given register, but it is no guarantee of the order of entries in a
register. The entry number is.

Each entry is connected to an item by a given item hash. Entries reference
items in the `item-hash` property using the hash derived from the
corresponding item's content.

Each key (in the `key` property) is a unique UTF-8 string which identifies
something in a register. 

Entries also contain the property `index-entry-number`, which is a unique
number that defines an entry's position within the ordered list of an index. 

The `index-entry-number` property depends on indexes, which are an
experimental and unreliable feature.

