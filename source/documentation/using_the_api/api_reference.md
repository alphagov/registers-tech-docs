## <a name="apireference"></a>API reference

### GET /register

View information about a register, including:  

* the internet domain the register is on
* when the register was last updated
* how many entries and records the register contains

Example URL: https://country.register.gov.uk/register

Example request: `curl --request GET --url https://country.register.gov.uk/register --header 'accept: application/json'`

Example response:

```
{  
   "domain":"register.gov.uk",
   "total-records":199,
   "total-entries":206,
   "register-record":{  
      "fields":[  
         "country",
         "name",
         "official-name",
         "citizen-names",
         "start-date",
         "end-date"
      ],
      "registry":"foreign-commonwealth-office",
      "text":"British English-language names and descriptive terms for countries",
      "phase":"beta",
      "register":"country",
      "entry-timestamp":"2016-08-04T14:45:41Z",
      "key":"country",
      "index-entry-number":"2",
      "entry-number":"2"
   },
   "last-updated":"2017-03-29T14:22:30Z"
}
```

### GET /records

Get all records from the register. For example, all of the countries from the country register.

*Note: Results from this API call are paginated. This call will return the first 100 records from the first page of the register. Use `page-size` to define the number of records you want and `page-index` to define the pages you want. The maximum `page-size` is 5000.*

Example URL: https://local-authority-eng.register.gov.uk/records

Example request: `curl --request GET --url 'https://local-authority-eng.register.gov.uk/records?page-index=1&page-size=3' --header 'accept: application/json'`

Example response:

```
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

### GET /record/{field-value}

Find a specific record within a register. For example, the record for Vatican City in the country register.

*Note: You must have the exact field value of the unique identifier for the record to get a match from the register. In the country register, for example, the field value of the unique identifier, the ICO country code, must be in capital letters.*

Example URL: https://country.register.gov.uk/record/VA

Example request: `curl --request GET --url https://country.register.gov.uk/record/VA --header 'accept: application/json'`

Example response:

```
{  
   "VA":{  
      "index-entry-number":"204",
      "entry-number":"204",
      "entry-timestamp":"2016-04-05T13:23:05Z",
      "key":"VA",
      "item":[  
         {  
            "country":"VA",
            "official-name":"Vatican City State",
            "name":"Vatican City",
            "citizen-names":"Vatican citizen"
         }
      ]
   }
}
```

### GET /records/{field-name}/{field-value}  

Find all records that share a field-value for a particular field. For example, all schools marked as Quaker schools from the school register.

*Note: Results from this API call are paginated. This call will return the first 100 records from the first page of the register. Use `page-size` to define the number of records you want and `page-index` to define the pages you want. The maximum `page-size` is 5000.*

Example URL: https://local-authority-eng.register.gov.uk/records/local-authority-type/CTY

Example request: `curl --request GET --url https://local-authority-eng.register.gov.uk/records/local-authority-type/CTY --header 'accept: application/json'`

Example response:

```
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

### GET /entries

Get all entries from the register. For example, all updates there have ever been to the country register.

*Note: Results from this API call are paginated. This call will return the first 100 entries from the first page of the register. Use `page-size` to define the number of entries you want and `page-index` to define the pages you want. The maximum `page-size` is 5000.*

Example URL: https://local-authority-eng.register.gov.uk/entries?start=1&limit=10

Example request: `curl --request GET --url 'https://local-authority-eng.register.gov.uk/entries?start=1&limit=10' --header 'accept: application/json'`

Example response:

```
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

### GET /entry/{entry-number}

Find a specific entry from a register. For example, an update to the record for the USSR in the country register. An entry can include multiple items, which will return in a list of `item-hash`

Example URL: https://country.register.gov.uk/entry/204

Example request: `curl --request GET --url https://country.register.gov.uk/entry/204 --header 'accept: application/json'`

Example response:

```
[  
   {  
      "index-entry-number":"204",
      "entry-number":"204",
      "entry-timestamp":"2016-04-05T13:23:05Z",
      "key":"VA",
      "item-hash":[  
         "sha-256:466d194d5100532edd115e3f0035967b09bc7b7f5fc444166df6f4a5f7cb9127"
      ]
   }
]
```

### <a name="items"></a>GET /item/{item-hash}

Find a specific item within a register.

Example URL: https://country.register.gov.uk/item/sha-256:466d194d5100532edd115e3f0035967b09bc7b7f5fc444166df6f4a5f7cb9127

Example request: `curl --request GET --url https://country.register.gov.uk/item/sha-256:466d194d5100532edd115e3f0035967b09bc7b7f5fc444166df6f4a5f7cb9127 --header 'accept: application/json'`

Example response:

```
{
  "country": "VA",
  "official-name": "Vatican City State",
  "name": "Vatican City",
  "citizen-names": "Vatican citizen"
}
```

### <a name="downloadreg"></a>GET /download-register

Download the full contents of the register in a ZIP file.

*Note: This will download every entry and item as an individual JSON file. If you only want to download records, use `GET /records`.*

Example URL: https://local-authority-eng.register.gov.uk/download-register

Example request: `curl -o country.zip --request GET --url https://local-authority-eng.register.gov.uk/download-register`

## Getting updates

You can download the new entries in 2 ways:  

* download another copy of the full register
* download individual updated entries for the records you are using

### Check for updates

Path: GET /register

You can find the latest entry number by looking at the register information and comparing the most recent entry number with your own copy.

Example request: https://country.register.gov.uk/register

### Download a full new copy of the register

See [endpoint for downloading register](#downloadreg).

### Download all updates for one record

Path: GET /record/{field-value}/entries

Get all entries for a single record.

Example URL: https://country.register.gov.uk/record/VA/entries

Example request: `curl --request GET --url https://country.register.gov.uk/record/VA/entries --header 'accept: application/json'`

Example response:

```
[
  {
    "entry-number": "195",
    "entry-timestamp": "2016-04-05T13:23:05Z",
    "item-hash": "sha-256:d97d6b34bc572e334cbd7898f785b72947557d9dbea59977077f231274259f3b"
  },
  {
    "entry-number": "204",
    "entry-timestamp": "2016-04-05T13:23:05Z",
    "item-hash": "sha-256:466d194d5100532edd115e3f0035967b09bc7b7f5fc444166df6f4a5f7cb9127"
  }
]
```

You can then download the latest item, for example entry 204 in the above example. Follow the [guidance for downloading items](#items).
