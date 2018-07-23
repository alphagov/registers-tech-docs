## Getting updates

This guide assumes you know the current highest entry number for your copy of a register. 

You can regularly compare this value with new queries to a register to see if there are any updates.

### Return all new entries since your last update

You can use the [`GET /entries/` endpoint](#getentries) to return specific entries to a register. This takes the parameters `start` and `limit`. 

For example, your last highest entry number from the `government-organisation` register could
be 750. You could then make a request to find out if there are any new entries. If you receive a response, you'll know there are updates.

Example request:

```http
GET /entries/?start=751 HTTP/1.1
Host: goverment-organisation.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

You should also look at the `Link` header in the response. 

Example response header:

```http
HTTP/1.1 200
Content-Type: application/json
Link: <?start=850&limit=100>; rel="next",<?start=650&limit=100>; rel="previous"
```

In the example, there are more than 100 new entries since the last update, as shown by `rel="next"`. 

In this situation, you can set the `limit` parameter higher. You can also make new requests, increasing the value of `start` each time, until you no longer see a `Link` header returned with `rel="next"`.

### See what data is in each entry 

You can use the [`GET /items/{item-hash}` endpoint](#items) on the value in
the `item-hash` property. 

Following the previous example, you could make a request using the
`item-hash` value in entry 208:

```http
GET /items/sha-256:f89f36ed8b2a1417237a8e95b810e8ab4ead844277ad7bc7794cb5f83732c976 HTTP/1.1 
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



