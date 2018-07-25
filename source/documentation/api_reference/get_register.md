Get information about a register.

```http
GET /register/ HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json

{
  "domain": "register.gov.uk",
  "total-records": 354,
  "total-entries": 358,
  "register-record": {
    "fields": [
      "local-authority-eng",
      "local-authority-type",
      "name",
      "official-name",
      "start-date",
      "end-date"
    ],
    "registry": "department-for-communities-and-local-government",
    "text": "Local authorities in England",
    "phase": "beta",
    "register": "local-authority-eng"
  },
  "custodian": "Mark Coram",
  "last-updated": "2017-07-04T10:55:43Z"
}
```
