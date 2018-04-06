## Quick start guide

Each register has an open, RESTful API which you can use to access the data in the register. 

**1. Find the base URL for the register(s) you want to use.** 

You can find the base URL for each register on its API inspector. For example, for the `local-authority-eng` register the API inspector is located at `https://local-authority-eng.register.gov.uk/`. 

The following are some example of base URLs:

| Register ID | Base URL |
|----------|----------|
| `local-authority-eng`     | `https://local-authority-eng.register.gov.uk/`|
| `country` | `https://country.register.gov.uk/` |
| `allergen`  | `https://allergen.register.gov.uk/` |

**2. Find the endpoints you want to use.**

Using different endpoints, you can:

* [view information about a register](#get-register) 
* [get all records from a register](#get-records) 
* [find a specific record within a register](#get-record-field-value) 
* [get all entries for a single record](#get-record-field-value-entries) 
* [find all records that share a `field-value` for a particular field](#get-records-field-name-field-value) 
* [get all entries from a register](#get-entries)
* [find a specific entry from a register](#get-entry-entry-number)
* [find a specific item within a register](#get-item-item-hash)
* [download the full contents of a register in a ZIP file](#get-download-register) 

**3. Choose the format of the response.**

You can choose from the following response formats, and adding the appropriate suffix to the request URL:

| Format | Suffix | Media type |
|--------|--------|------------|
| JSON | .json | application/json |
| YAML | .yaml | text/ yaml |
| CSV | .csv | text/csv |
| TSV | .tsv | text/tsv |
| Turtle | .ttl | text/ttl |

For example, this is a valid request: 

```
curl https://country.register.gov.uk/record/GB.json
```

You can also specify a format by making a request with different headers. For example, this is also a valid request:

```
curl https://country.register.gov.uk/record/GB --header 'accept: application/json'
```

**4. Get register data and use it in your product or service.**

API calls on resource collections are paginated. Follow the specific guidance for each endpoint to get the page(s) of entries and records you need. For example, to paginate the records’ collection use `page-size` to define the amount of elements you want per page and `page-index` to define the page you want to get. The maximum `page-size` is 5000.
