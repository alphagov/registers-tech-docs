## Quick start guide

### Generate an API key

[Create your API key](https://www.registers.service.gov.uk/api_users/new) and fill in the requested information. Your API key will be displayed and emailed to you. 

Your API key can be used for all registers. 

### Authenticate with your API key 

You should include your key in all requests using the `Authorization` header:

`curl https://country.register.gov.uk/record/GB.json --header 'Authorization: YOUR-API-KEY-HERE'`

### Find the base URL for register(s) 

Find the base URL for each register on its API inspector. For example, the API inspector for the `local-authority-eng` register is located at `https://local-authority-eng.register.gov.uk/`. 

The following are some examples of base URLs:

| Register ID | Base URL |
|----------|----------|
| `local-authority-eng`     | `https://local-authority-eng.register.gov.uk/`|
| `country` | `https://country.register.gov.uk/` |
| `allergen`  | `https://allergen.register.gov.uk/` |

### Choose an endpoint  

Using different endpoints, you can:

* [view information about a register](#get-register) 
* [get all records from a register](#get-records) 
* [get a specific record within a register based on a particular key](#get-records-key) 
* [get all entries for a single record based on a particular key](#get-records-key-entries) 
* [get all records that share a `field-value` for a particular field](#get-records-field-name-field-value) 
* [get all entries from a register](#get-entries)
* [get a specific entry from a register](#get-entries-entry-number)
* [get a specific item within a register](#get-items-item-hash)
* [download the full contents of a register in a ZIP file](#get-download-register) 

### Choose a response format 

Choose a response format by adding the appropriate suffix to the request URL:

| Format | Suffix | Media type |
|--------|--------|------------|
| JSON | .json | application/json |
| YAML | .yaml | text/ yaml |
| CSV | .csv | text/csv |
| TSV | .tsv | text/tsv |
| Turtle | .ttl | text/ttl |

For example: 

```
curl https://country.register.gov.uk/records/GB.json --header 'Authorization: YOUR-API-KEY-HERE'
```

You can also specify a format by making a request with the `Accept` header. For example:

```
curl https://country.register.gov.uk/records/GB --header 'Accept: application/json' --header 'Authorization: YOUR-API-KEY-HERE'
```

### Pagination 

API calls on resource collections are paginated. Follow the specific guidance for each endpoint to get the page(s) of entries and records you need. For example, to paginate the records’ collection use `page-size` to define the amount of elements you want per page and `page-index` to define the page you want to get. The maximum `page-size` is 5000.
