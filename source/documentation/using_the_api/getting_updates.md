## Getting updates

You can use [the `GET /download-register/` endpoint](#download) to download a full new copy of a register.

### See how many updates have been made to a register

You can use the [`GET /records/` endpoint](#getrecord) to return all the records from a register. In each record, there is an [`entry-number` property](#entries). The largest value for this is the current size of a register. You can compare this with a local copy. 

Similarly, you can use the [`GET /register/` endpoint](#getregister) to return the `total-entries` property for a register. You can compare this with the same value in a local copy.

### Return all entries since your last update

You can use the [`GET /entries/` endpoint](#getentries) with the optional `start` and `limit` parameters to return specific entries to a register. For example, your highest `entry-number` for your copy of the `country` register could be 205, and you may know that there have been 3 updates to the register since you obtained your copy. You could use the following request, setting `start` to `206` and `limit` to `208`:

```http
GET /entries?start=206&limit=208/ HTTP/1.1
Host: country.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json
Link: <?start=206&limit=208>; rel="next"

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

To see what the actual update is for each of these entries, you can use the [`GET /items/{item-hash}` endpoint](#items) on the value in the `item-hash` property. 

For example, you could use the following request for entry 208:

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


