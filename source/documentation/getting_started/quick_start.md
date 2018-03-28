## Quick start guide

Registers which are in beta are reliable and ready for use in products and services. Each register has an open, RESTful API which you can use to access the data in the register. 

You can follow this guide to quickly get started with GOV.UK Registers APIs. 

**1. Find the base URL for the register(s) you want to use.** 

You can find a full list of register base URLs on our [Registers collection page] (https://registers.cloudapps.digital/registers), but the following are some examples:

| Register name | Base URL |
|----------|----------|
| `local-authority-eng`     | `https://local-authority-eng.register.gov.uk/`|
| `country` | `https://country.register.gov.uk/` |
| `allergen`  | `https://allergen.register.gov.uk/` |

**2. Find the endpoints you want to use.**

For example, `GET record/BIR` is the endpoint for Birmingham City Council in the `local-authority-eng` register.

| Endpoint | Description |
|----------|----------|
| [`GET /register`](#get-register)     | View information about a register. |
| [`GET /records`](#get-records) | Get all records from a register. |
| [`GET /record/{field-value}`](#get-record-field-value)  | Find a specific record within a register. |
| [`GET /record/{field-value}/entries`](#get-record-field-value-entries)  | Get all entries for a single record. |
| [`GET /records/{field-name}/{field-value}`](#get-records-field-name-field-value) | Find all records that share a field-value for a particular field. |
| [`GET /entries`](#get-entries)  | Get all entries from a register. |
| [`GET /entry/{entry-number}`](#get-entry-entry-number)     | Find a specific entry from a register. |
| [`GET /item/{item-hash}`](#get-item-item-hash) | Find a specific item within a register. |
| [`GET /download-register`](#get-download-register)  | Download the full contents of a register in a ZIP file. |

**3. Add `.json`, `.yaml`, `.csv`, `.tsv`, or `.ttl` to the end of the request URL (before any query parameters) to choose the format of the response, or amend headers to `accept application/json` or equivalent.**

**4. Parse register data and use it in your product or service.**

Most of the API functions return paginated results. Follow the specific guidance for each endpoint to get the page(s) of entries, items, and records you need. Use `page-size` to define the number of results you want and `page-index` to define the pages you want. The maximum `page-size` is 5000.
