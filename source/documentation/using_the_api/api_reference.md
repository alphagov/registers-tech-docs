## <a name="apireference">API reference</a>

### <a name="getregister">`GET /register`</a>	

Get information about a register.

```http
GET /register HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json

{
  "domain": "register.gov.uk",
  "total-records": 354,
  "total-entries": 358,
  "register-record": {
    "fields": [
      "local-authority-eng",
      "local-authority-type",
      "name",
      "official-name",
      "start-date",
      "end-date"
    ],
    "registry": "department-for-communities-and-local-government",
    "text": "Local authorities in England",
    "phase": "beta",
    "register": "local-authority-eng"
  },
  "custodian": "Mark Coram",
  "last-updated": "2017-07-04T10:55:43Z"
}
```

### <a name="get-records">`GET /records`</a>

Get all records from a register.

Parameters: 

* `page-index` (Optional): Collection page number. Defaults to 1.
* `page-size` (Optional): Collection page size. Defaults to 100. Maximum is 5000. 

```http
GET /records?page-index=1&page-size=3 HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json
Link: <?page-index=2&page-size=3>; rel="next"

{  
   "KIN":{  
      "index-entry-number":"357",
      "entry-number":"357",
      "entry-timestamp":"2017-01-26T12:34:10Z",
      "key":"KIN",
      "item":[  
         {  
            "local-authority-type":"NMD",
            "official-name":"Borough Council of King's Lynn and West Norfolk",
            "local-authority-eng":"KIN",
            "name":"King's Lynn and West Norfolk"
         }
      ]
   },
   "GLA":{  
      "index-entry-number":"356",
      "entry-number":"356",
      "entry-timestamp":"2016-11-01T14:16:54Z",
      "key":"GLA",
      "item":[  
         {  
            "local-authority-type":"SRA",
            "official-name":"Greater London Authority",
            "local-authority-eng":"GLA",
            "name":"Greater London",
            "start-date":"1905-06-22"
         }
      ]
   },
   "LND":{  
      "index-entry-number":"355",
      "entry-number":"355",
      "entry-timestamp":"2016-10-31T12:59:03Z",
      "key":"LND",
      "item":[  
         {  
            "local-authority-type":"CC",
            "official-name":"City of London Corporation",
            "local-authority-eng":"LND",
            "name":"City of London",
            "start-date":"1905-06-28"
         }
      ]
   }
}
```

### <a name="get-records-key">`GET /records/{key}`</a>

Get a specific record within a register based on a particular key.

Parameters: 

* `key` (Required): A unique UTF-8 string which identifies something in a register.

```http
GET /records/KIN HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json

{
  "KIN": {
    "index-entry-number": "357",
    "entry-number": "357",
    "entry-timestamp": "2017-01-26T12:34:10Z",
    "key": "KIN",
    "item": [
      {
        "local-authority-type": "NMD",
        "official-name": "Borough Council of King's Lynn and West Norfolk",
        "local-authority-eng": "KIN",
        "name": "King's Lynn and West Norfolk"
      }
    ]
  }
}
```

### <a name="get-records-key-entries">`GET /records/{key}/entries`</a>

Get all entries for a single record based on a particular key.

Parameters: 

* `key` (Required): A unique UTF-8 string which identifies something in a register.

```http
GET /records/KIN/entries HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json

[
  {
    "index-entry-number": "265",
    "entry-number": "265",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "key": "KIN",
    "item-hash": [
      "sha-256:5a8571fc6e78f8688c66b72ea45f921a7cd1562b9a9b5b9dab8f49f842d1e391"
    ]
  },
  {
    "index-entry-number": "357",
    "entry-number": "357",
    "entry-timestamp": "2017-01-26T12:34:10Z",
    "key": "KIN",
    "item-hash": [
      "sha-256:3f4da33a33c24de11cca3539f14ee663359608be0ba218d4fc05792c1d19c00f"
    ]
  }
]
```

### <a name="get-records-field-name-field-value">`GET /records/{field-name}/{field-value}`</a>

Get all records that share a `field-value` for a particular `field-name`.

Parameters: 

* `field-name` (Required): Field name. 
* `field-value` (Required): Field value. 
* `page-index` (Optional): Collection page number. Defaults to 1.
* `page-size` (Optional): Collection page size. Defaults to 100. Maximum is 5000. 

```http
GET /records/local-authority-type/CTY?page-index=1&page-size=3 HTTP/1.1 
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json
Link: <?page-index=2&page-size=3>; rel="next"

{  
   "NTH":{  
      "index-entry-number":"269",
      "entry-number":"269",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"NTH",
      "item":[  
         {  
            "local-authority-type":"CTY",
            "official-name":"Northamptonshire County Council",
            "local-authority-eng":"NTH",
            "name":"Northamptonshire"
         }
      ]
   },
   "WAR":{  
      "index-entry-number":"334",
      "entry-number":"334",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"WAR",
      "item":[  
         {  
            "local-authority-type":"CTY",
            "official-name":"Warwickshire County Council",
            "local-authority-eng":"WAR",
            "name":"Warwickshire"
         }
      ]
   },
   "HRT":{  
      "index-entry-number":"208",
      "entry-number":"208",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"HRT",
      "item":[  
         {  
            "local-authority-type":"CTY",
            "official-name":"Hertfordshire County Council",
            "local-authority-eng":"HRT",
            "name":"Hertfordshire"
         }
      ]
   },
```

### <a name="get-entries">`GET /entries`</a>

Get all entries from a register.

Parameters: 

* `start` (Optional): Collection page number. Defaults to 1.
* `limit` (Optional): Collection page size. Defaults to 100. Maximum is 5000. 

```http
GET /entries HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json
Link: <?start=101&limit=100>; rel="next"


[  
   {  
      "index-entry-number":"1",
      "entry-number":"1",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"BAS",
      "item-hash":[  
         "sha-256:6c4c815895ea675857ee4ec3fb40571ce54faf5ebcdd5d73a2aae347d4003c31"
      ]
   },
   {  
      "index-entry-number":"2",
      "entry-number":"2",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"BBD",
      "item-hash":[  
         "sha-256:37dd060a3efa6d5bf16f876e08fa867210f424e2e4a7989d0322218f6772332d"
      ]
   },
   {  
      "index-entry-number":"3",
      "entry-number":"3",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"BDF",
      "item-hash":[  
         "sha-256:01cda95d102807943d68f71bbe7b9b290dec2ebdb15967ca66820f825ece5831"
      ]
   },
   {  
      "index-entry-number":"4",
      "entry-number":"4",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"BIR",
      "item-hash":[  
         "sha-256:bdc17a29807f47a94cf612abf92fcadd2d83176f9ea419b4eeda23af2cf25ef9"
      ]
   },
   {  
      "index-entry-number":"5",
      "entry-number":"5",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"BMH",
      "item-hash":[  
         "sha-256:37ca110698ea569fc229e5042830384890ab1095737f1630c9de30692cfcf973"
      ]
   },
   {  
      "index-entry-number":"6",
      "entry-number":"6",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"BNH",
      "item-hash":[  
         "sha-256:792c58bf07b54a3a072c8c8a7e9b0681490e3cc76ee6e95da20434520b66d9c7"
      ]
   },
   {  
      "index-entry-number":"7",
      "entry-number":"7",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"BNS",
      "item-hash":[  
         "sha-256:99d5b1631c6241b31d4c22a867802035763649efa50cc8e4c5c25a71e484d412"
      ]
   },
   {  
      "index-entry-number":"8",
      "entry-number":"8",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"BOL",
      "item-hash":[  
         "sha-256:2cfa1b4bd729bde785a1fdb004c6be6a04eda3ed0ac1198401ef144b218545e0"
      ]
   },
   {  
      "index-entry-number":"9",
      "entry-number":"9",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"BPL",
      "item-hash":[  
         "sha-256:0cd1103a9b0e4dcd774f6c52a4d541e8a029e78ae609b46eb1d0546df9587a6a"
      ]
   },
   {  
      "index-entry-number":"10",
      "entry-number":"10",
      "entry-timestamp":"2016-10-21T16:11:20Z",
      "key":"BRC",
      "item-hash":[  
         "sha-256:00a2c66ab69086fd9ed8d43a46e04d1577340468bd43e8fb46dcf4d6ae59c439"
      ]
   }
]
```

### <a name="get-entries-entry-number">`GET /entries/{entry-number}`</a>

Get a specific entry from a register.

```http
GET /entries/204 HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json

[
  {
    "index-entry-number": "204",
    "entry-number": "204",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "key": "NEW",
    "item-hash": [
      "sha-256:53187fa5562b658b68da23fcd64bd595688ead21da3ba443531ed21164be775e"
    ]
  }
]
```

### <a name="items">`GET /items/{item-hash}`</a>

Get a specific item within a register.

```http
GET /items/sha-256:6c4c815895ea675857ee4ec3fb40571ce54faf5ebcdd5d73a2aae347d4003c31 HTTP/1.1
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

### <a name="items">`GET /download-register`</a>

Download the full contents of the register in a ZIP file.

```http
GET /download-register HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

This will download every entry and item as an individual JSON file. If you only want to download records, use `GET /records`.


