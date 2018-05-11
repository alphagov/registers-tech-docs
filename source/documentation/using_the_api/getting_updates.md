## Getting updates

You can find the latest entry number by looking at the register information (use the [`GET /register` endpoint](#getregister)) and comparing the most recent entry number with your own copy.

Example request: `https://local-authority-eng.register.gov.uk/register`

Download a full new copy of the register by using [the `GET /download-register` endpoint](#download).

Download all updates for one record by [using the `GET /records/{field-value}/entries` endpoint](#record-entries):

Example URL: `https://local-authority-eng.register.gov.uk/records/KIN/entries`

Example request: `curl --request GET --url https://local-authority-eng.register.gov.uk/records/KIN/entries --header 'Accept: application/json'`

Example response:

```
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

You can then download the latest item, for example entry 204 in the above example. Use the [`GET /items/{item-hash}
` endpoint](#items) for downloading items. 

