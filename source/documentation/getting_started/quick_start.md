## Quick start guide

Each register has an open, RESTful API which you can use to access the data in the register. 

### Generate an API key 

Visit the [Create your API Key](https://registers-trial.service.gov.uk/api_users/new) page and fill in the requested information. Your API key will be emailed to you. 

Your API key can be used for all registers. 

### Authenticate with your API key

You should include your key in all requests using the `Authorization` header:

```
curl https://country.register.gov.uk/record/GB.json --header "Authorization: <YOUR-API-KEY>"
```

### Find the base URL(s) you need

Find the base URL for each register on its API inspector. For example, the API inspector for the `local-authority-eng` register is located at `https://local-authority-eng.register.gov.uk/`. 

The following are some examples of base URLs:

| Register ID | Base URL |
|----------|----------|
| `local-authority-eng`     | `https://local-authority-eng.register.gov.uk/`|
| `country` | `https://country.register.gov.uk/` |
| `allergen`  | `https://allergen.register.gov.uk/` |

### Find the endpoints you need 

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

### Choose the format of the response

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
curl https://country.register.gov.uk/record/GB.json
```

You can also specify a format by making a request with different headers. For example:

```
curl https://country.register.gov.uk/record/GB --header 'accept: application/json'
```

### Get register data and use it in your product or service

API calls on resource collections are paginated. Follow the specific guidance for each endpoint to get the page(s) of entries and records you need. For example, to paginate the records’ collection use `page-size` to define the amount of elements you want per page and `page-index` to define the page you want to get. The maximum `page-size` is 5000.

