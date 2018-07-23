## Getting updates

This guide assumes you know the current highest entry number for your copy of a register. 

You can regularly compare this value with new queries to a register to see if there are any updates.

### Return all new entries since your last update

You can use the [`GET /entries/` endpoint](#getentries) to return specific entries to a register. 

For example, your last highest entry number from the `government-organisation` register could
be 750. To find out if there are any new entries, you could make this request:

```http
GET /entries/?start=751 HTTP/1.1
Host: goverment-organisation.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

If you get a response that's not empty, you'll know there are updates.

You should also look at the `Link` header. The response to the example would contain this header:

```http
HTTP/1.1 200
Content-Type: application/json
Link: <?start=851&limit=100>; rel="next",<?start=651&limit=100>; rel="previous"
```

Here, there are more than 100 new entries since the last update. In this situation, you can follow the links in `rel="next"` until the `Link` header no longer contains one. 

### See what data is in each entry 

You can use the [`GET /items/{item-hash}` endpoint](#items) on the value in
the `item-hash` property 

You can read more about [this and how entries, items and records relate](how-entries-items-and-records-relate).
