1. Find out [what open registers are available](#availablereg) and which you want to use.
2. Each open register has a read-only API. No authentication is required.
3. [Find the endpoints you want](#apireference).
4. Add `.json`, `.yaml`, `.csv`, `.tsv`, or `.ttl` to the end of the request URL (before any query parameters) to choose the format of the response, or amend headers to `accept application/json` or equivalent.
5. Parse register data and use it in your product or service.

Most of the API functions return paginated results. Follow the specific guidance for each endpoint to get the page(s) of entries, items, and records you need. Use `page-size` to define the number of results you want and `page-index` to define the pages you want. The maximum `page-size` is 5000.
