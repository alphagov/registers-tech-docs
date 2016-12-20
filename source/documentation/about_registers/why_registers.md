## Why use a register?

A register has [distinct characteristics](https://gds.blog.gov.uk/2015/10/13/the-characteristics-of-a-register/) that make it different from a traditional database, for example.

A register:  

* is canonical so it is the only place where government holds that data
* only contains the data it was created to record and is append-only
* is a live list and can be read by an API
* uses standard names
* can prove the integrity of the data within it
* only contains raw, not derived, data
* must have a someone responsible for its maintenance, known as a custodian

Registers are append-only. Some registers use an `end-date` field to note when an entry ceases to be valid. For example, in the country register, the end-date contains the date when a country was dissolved or changed its name.
