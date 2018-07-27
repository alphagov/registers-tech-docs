To follow this guidance, you need to know the current highest entry number for your copy of a register. 

If there are new entries to the register, you can query the register to return the new entries.

### Return all new entries since your last update

You can use the [`GET /entries/` endpoint](/api_reference/get_entries#getentries) to return specific entries to a register. 

For example, your last highest entry number from the `government-organisation` register could be 750. To find out if there are any new entries, you could make this request:

```http
GET /entries/?start=751 HTTP/1.1
Host: goverment-organisation.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

If there are no updates, you will receive an empty response. If there are updates, you will receive the new entries in the response.

The response to the previous example contains:

```http
HTTP/1.1 200
Content-Type: application/json
Link: <?start=851&limit=100>; rel="next",<?start=651&limit=100>; rel="previous"
```

In this example, there are more than 100 new entries since the last update, as shown by the `Link` header. In this situation, you can follow the links in `rel="next"` until the `Link` header no longer contains that link. 

### See what data is in each entry 

You can use the [`GET /items/{item-hash}` endpoint](/api_reference/get_items_item_hash#items) on the value in
the `item-hash` property. 

You can read more about [this and how entries, items and records relate](/the_components_of_a_register/#how-entries-items-and-records-relate).

