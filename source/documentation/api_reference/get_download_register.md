Download the full contents of the register in a ZIP file.

```http
GET /download-register/ HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

This will download every entry and item as an individual JSON file. If you only want to download records, use `GET /records`.


