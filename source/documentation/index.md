# API documentation for registers

Each register has an open API you can use to access the data without any authentication. There are no rate limits.

Each register API allows you to:  

* find out information about a register
* get all the records from a register
* find records that share attributes with each other
* download the whole or part of a register
* find a single record, entry or item

The base URL for each register API is of the form: https://{register name}.register.gov.uk/

You can find the base URL for each register by looking at the list of [available registers](https://registers.cloudapps.digital/registers).

Most of the APIs return paginated results. See the API reference to get the page(s) of entries, items, and records you need.

Registers only provide raw data. You cannot use the APIs to search a register or match data. Depending on your requirements, you may have to build indexes on top of a register to fulfill specific requests.

[Contact the GDS registers team](https://registers.cloudapps.digital/support.html) if you have any problems or questions that are not covered in this guide.
