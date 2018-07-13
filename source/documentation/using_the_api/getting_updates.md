## Getting updates

You can use the [`GET /register/` endpoint](#getregister) to return the `total-entries` property for a register. If you keep track of this value, you can compare it with a new query to the register to find out if there are any updates.

### Return all entries since your last update

You can use the [`GET /entries/` endpoint](#getentries) with the `start` and `limit` parameters to return specific entries to a register. For example, your highest `entry-number` for a local copy of the `country` register could be 205. You could then use the following request to find out how many updates there have been since (if any):

```http
GET /entries?start=206/ HTTP/1.1
Host: country.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json
Link: <?start=206>; rel="next"

[
  {
    "index-entry-number": "206",
    "entry-number": "206",
    "entry-timestamp": "2017-03-29T14:22:30Z",
    "key": "GM",
    "item-hash": [
      "sha-256:0429375c4fb403288ef816e5dd38a24f192e35b8f55e40cc6266eb25eaef77b1"
    ]
  },
  {
    "index-entry-number": "207",
    "entry-number": "207",
    "entry-timestamp": "2017-10-25T09:52:52Z",
    "key": "CI",
    "item-hash": [
      "sha-256:b3ca21b3b3a795ab9cd1d10f3d447947328406984f8a461b43d9b74b58cccfe8"
    ]
  },
  {
    "index-entry-number": "208",
    "entry-number": "208",
    "entry-timestamp": "2018-06-13T13:54:40Z",
    "key": "SZ",
    "item-hash": [
      "sha-256:f89f36ed8b2a1417237a8e95b810e8ab4ead844277ad7bc7794cb5f83732c976"
    ]
  }
]
```

To see what data is in the updates for each of these entries, you can use the [`GET /items/{item-hash}` endpoint](#items) on the value in the `item-hash` property. 

Following the example above, you could use the following request for entry 208:

```http
GET /items/sha-256:f89f36ed8b2a1417237a8e95b810e8ab4ead844277ad7bc7794cb5f83732c976
Host: country.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
{
  "country": "SZ",
  "official-name": "Kingdom of Eswatini",
  "name": "Eswatini",
  "citizen-names": "Swazi"
}
```

### Return all updates for a particular key 

You can use the [`GET /records/{key}/entries/` endpoint](#get-record-key-entries) to download all updates for a record according to a particular key. 

For example, for the `KIN` key in the `local-authority-register`:

```http
GET /records/KIN/entries/ HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json

[
  {
    "index-entry-number": "195",
    "entry-number": "195",
    "entry-timestamp": "2016-04-05T13:23:05Z",
    "key": "KIN",
    "item-hash": [
      "sha-256:d97d6b34bc572e334cbd7898f785b72947557d9dbea59977077f231274259f3b"
    ]
  },
  {
    "index-entry-number": "204",
    "entry-number": "204",
    "entry-timestamp": "2016-04-05T13:23:05Z",
    "key": "KIN",
    "item-hash": [
      "sha-256:466d194d5100532edd115e3f0035967b09bc7b7f5fc444166df6f4a5f7cb9127"
    ]
  }
]
```
