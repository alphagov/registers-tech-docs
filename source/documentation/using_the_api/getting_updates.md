## Getting updates

This guide assumes you know the current highest entry number for your copy of a register. 

You can regularly compare this value with new queries to a register to see if there are any updates.

### Return all new entries since your last update

You can use the [`GET /entries/` endpoint](#getentries) to return specific entries to a register. This takes the parameters `start` and `limit`. 

For example, your last highest entry number from the `government-organisation` register could
be 750. You could then make this request to find out if there are any new entries:

```http
GET /entries/?start=751 HTTP/1.1
Host: goverment-organisation.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

If you receive a response, you'll know there are updates.

You should also look at the `Link` header. The response to the example would contain this header:

```http
HTTP/1.1 200
Content-Type: application/json
Link: <?start=850&limit=100>; rel="next",<?start=650&limit=100>; rel="previous"
```

Here, there are more than 100 new entries since the last update, and `rel="next"` shows that these have been paginated. 

In this situation, you could set the `limit` parameter higher. You could also make new requests, increasing the value of `start` each time, until a `Link` header is returned without `rel="next"`.

### See what data is in each entry 

You can use the [`GET /items/{item-hash}` endpoint](#items) on the value in
the `item-hash` property 

You can read more about [this and how entries, items and records relate](how-entries-items-and-records-relate).



