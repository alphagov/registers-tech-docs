## Quick start guide

Registers which are in beta are reliable and ready for use in products and services. Each register has an open, RESTful API which you can use to access the data in the register. 

You can follow this guide to quickly get started with GOV.UK Registers APIs. 

**1. Find the base URL for the register(s) you want to use.** 

You can find a full list of register base URLs [here](https://registers.cloudapps.digital/registers).

The following are some examples of base URLs:

| Register name | Base URL |
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

For example, `GET record/BIR` is the endpoint for Birmingham City Council in the `local-authority-eng` register, and 'BIR' is the `field-value`. 

**3. Choose the format of the response.**

You can choose from the following response formats:

* `.json` (JSON)
* `.yaml` (YAML) 
* `.csv` (CSV) 
* `.tsv` (TSV)
* `.ttl` (TTL)

You can specify a format by adding the appropriate extension to the request URL. For example, this is a valid request: 

```
curl https://country.register.gov.uk/record/GB.json
```

You can also specify a format by making a request with different headers. For example, this is also a valid request:

```
curl https://country.register.gov.uk/record/GB --header 'accept: application/json'
```

**4. Parse register data and use it in your product or service.**

Most of the API functions return paginated results. Follow the specific guidance for each endpoint to get the page(s) of entries, items, and records you need. Use `page-size` to define the number of results you want and `page-index` to define the pages you want. The maximum `page-size` is 5000.
