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
the `item-hash` property 

You can read more about [this and how entries, items and records relate](how-entries-items-and-records-relate).



