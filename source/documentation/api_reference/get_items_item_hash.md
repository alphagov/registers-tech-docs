Get a specific item within a register.

```http
GET /items/sha-256:6c4c815895ea675857ee4ec3fb40571ce54faf5ebcdd5d73a2aae347d4003c31/ HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json

{
  "local-authority-type": "UA",
  "official-name": "Bath and North East Somerset Council",
  "local-authority-eng": "BAS",
  "name": "Bath and North East Somerset",
  "start-date": "1996-04-01"
}
```
