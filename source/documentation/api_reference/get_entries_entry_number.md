Get a specific entry from a register.

```http
GET /entries/204/ HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json

[
  {
    "index-entry-number": "204",
    "entry-number": "204",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "key": "NEW",
    "item-hash": [
      "sha-256:53187fa5562b658b68da23fcd64bd595688ead21da3ba443531ed21164be775e"
    ]
  }
]
```
