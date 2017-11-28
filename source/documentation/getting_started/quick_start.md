## Quick start guide

1. [Find the base URL for the register(s) you want to use](https://registers.cloudapps.digital/registers). For example, for the 'Local authority eng' register: `https://local-authority-eng.register.gov.uk/`.
2. [Find the endpoints you want](#apireference). For example, `/record/BIR` in `https://local-authority-eng.register.gov.uk/record/BIR/`.
3. Add `.json`, `.yaml`, `.csv`, `.tsv`, or `.ttl` to the end of the request URL (before any query parameters) to choose the format of the response, or amend headers to `accept application/json` or equivalent.
4. Parse register data and use it in your product or service.

Most of the API functions return paginated results. Follow the specific guidance for each endpoint to get the page(s) of entries, items, and records you need. Use `page-size` to define the number of results you want and `page-index` to define the pages you want. The maximum `page-size` is 5000.
