## Getting updates

This guide assumes you know the current highest entry number for your copy of a register. 

You can regularly compare this value with new queries to a register to see if there are any updates.

### Return all new entries since your last update

You can use the [`GET /entries/` endpoint](#getentries) with the `start` and
`limit` parameters to return specific entries to a register. 

For example, your last highest entry number from the `country` register could
be 205. You could then use the following request to find out if there are any
new entries:

```http
GET /entries/?start=206 HTTP/1.1
Host: country.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

Example response:

```http
HTTP/1.1 200
Content-Type: application/json
Link <?start=106&limit=100>; rel="previous"

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

### See what data is in each entry 

You can use the [`GET /items/{item-hash}` endpoint](#items) on the value in
the `item-hash` property. 

Following the previous example, you could make a request using the
`item-hash` value in entry 208:

```http
GET /items/sha-256:f89f36ed8b2a1417237a8e95b810e8ab4ead844277ad7bc7794cb5f83732c976
Host: country.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

Example response:

```http
HTTP/1.1 200
Content-Type: application/json
{
  "country": "SZ",
  "official-name": "Kingdom of Eswatini",
  "name": "Eswatini",
  "citizen-names": "Swazi"
}
```

### If you have more updates than the value of `limit` 

[The `limit` parameter defaults to 100, and its maximum value is
5000](#get-entries). In the previous example, `limit` was 100. Here, if there
were more than 100 new entries since your last update, you would not get them
all. 

In this situation, you could set the `limit` parameter higher, but you may
still need to look at the `Link` header returned. If there are more new
entries than the value of `limit`, you'll see `rel="next"`. For example:

```http
HTTP/1.1 200
Content-Type: application/json
Link <?start=306&limit=100>; rel="next", <?start=106&limit=100>; rel="previous"

...
```

You could then make new requests, increasing the value of `start` each time, until
you no longer see a `Link` header returned with `rel="next"`.


