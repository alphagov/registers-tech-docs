## <a name="apireference"></a>API reference

Each register has a read-only API that allows you to:
* find out information about a register
* get all the records from a register
* find records that share attributes with each other
* download the whole or part of a register
* find a single record, entry or item

The base URL for each register API is of the form: https://{register name}.register.gov.uk/

See the [list of available open registers](#availablereg) to find out the base URL for each register.

Most of the APIs return paginated results. Follow the specific guidance for each endpoint to get the page(s) of entries, items, and records you need.  

### Find out more about a register

Path: GET /register

View information about a register, including:  

* the internet domain the register is on
* when the register was last updated
* how many entries and records the register contains

Example URL: https://country.register.gov.uk/register

Example request: `curl --request GET --url https://country.register.gov.uk/register --header 'accept: application/json'`

Example response:

```
{
  "domain": "register.gov.uk",
  "total-records": 199,
  "total-entries": 204,
  "register-record": {
    "entry-number": "2",
    "entry-timestamp": "2016-08-04T14:45:41Z",
    "item-hash": "sha-256:610bde42d3ae2ed3dd829263fe461542742a10ca33865d96d31ae043b242c300",
    "text": "British English-language names and descriptive terms for countries",
    "phase": "beta",
    "fields": [
      "country",
      "name",
      "official-name",
      "citizen-names",
      "start-date",
      "end-date"
    ],
    "register": "country",
    "registry": "foreign-commonwealth-office"
  },
  "last-updated": "2016-04-05T13:23:05Z"
}
```

### Get all records

Path: GET /records

Get all records from the register. For example, all of the countries from the country register.

*Note: Results from this API call are paginated. This call will return the first 100 records from the first page of the register. Use `page-size` to define the number of records you want and `page-index` to define the pages you want. The maximum `page-size` is 5000.*

Example URL: https://local-authority-eng.register.gov.uk/records

Example request: `curl --request GET --url 'https://local-authority-eng.register.gov.uk/records?page-index=1&page-size=3' --header 'accept: application/json'`

Example response:

```
{
  "WYC": {
    "entry-number": "345",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:98dfc01067abd5ef237b98d225b44a13d2acb5015334c006aec50f9792e554c7",
    "name": "Wychavon",
    "official-name": "Wychavon District Council",
    "local-authority-eng": "WYC",
    "local-authority-type": "NMD"
  },
  "WYE": {
    "entry-number": "346",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:0ae4443fcb4f35e8ec4aabe09fe0ad21bc44342979d22a11e3503bf68b15c404",
    "name": "Wyre Forest",
    "official-name": "Wyre Forest District Council",
    "local-authority-eng": "WYE",
    "local-authority-type": "NMD"
  },
  "ADU": {
    "entry-number": "348",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:e12026ce69abe71ea0fdde46d2b8916be218678ad227a8324075117565bec7ea",
    "name": "Adur",
    "official-name": "Adur District Council",
    "local-authority-eng": "ADU",
    "local-authority-type": "NMD"
  }
}
```

### View a specific record

Path: GET /record/{field-value}

Find a specific record within a register. For example, the record for Vatican City in the country register.

*Note: You must have the exact field value of the unique identifier for the record to get a match from the register. In the country register, for example, the field value of the unique identifier, the ICO country code, must be in capital letters.*

Example URL: https://country.register.gov.uk/record/VA

Example request: `curl --request GET --url https://country.register.gov.uk/record/VA --header 'accept: application/json'`

Example response:

```
{
  "entry-number": "204",
  "entry-timestamp": "2016-04-05T13:23:05Z",
  "item-hash": "sha-256:466d194d5100532edd115e3f0035967b09bc7b7f5fc444166df6f4a5f7cb9127",
  "name": "Vatican City",
  "country": "VA",
  "citizen-names": "Vatican citizen",
  "official-name": "Vatican City State"
}
```

### View records that share attributes  

Path: GET /records/{field-name}/{field-value}

Find all records that share a field-value for a particular field. For example, all schools marked as Quaker schools from the school register.

*Note: Results from this API call are paginated. This call will return the first 100 records from the first page of the register. Use `page-size` to define the number of records you want and `page-index` to define the pages you want. The maximum `page-size` is 5000.*

Example URL: https://local-authority-eng.register.gov.uk/records/local-authority-type/CTY

Example request: `curl --request GET --url https://local-authority-eng.register.gov.uk/records/local-authority-type/CTY --header 'accept: application/json'`

Example response:

```
{
  "NTH": {
    "entry-number": "269",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:3dd0676f10ab535ed46df5ee7f779afc83f60ca9787598f8fd108ad17a4110e1",
    "name": "Northamptonshire",
    "official-name": "Northamptonshire County Council",
    "local-authority-eng": "NTH",
    "local-authority-type": "CTY"
  },
  "LND": {
    "entry-number": "38",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:0bd11d488aadc456d4814853613a28dd26a1867702816376f4b5040968de3ad7",
    "name": "City of London",
    "start-date": "1905-06-28",
    "official-name": "City of London Corporation",
    "local-authority-eng": "LND",
    "local-authority-type": "CTY"
  },
  "WAR": {
    "entry-number": "334",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:9c4fbebee1030717a580d67c8424c6fa8164c8ec6ede2636faeb997bed826e22",
    "name": "Warwickshire",
    "official-name": "Warwickshire County Council",
    "local-authority-eng": "WAR",
    "local-authority-type": "CTY"
   }
}

...

```

### View all entries

Path: GET /entries

Get all entries from the register. For example, all updates there have ever been to the country register.

*Note: Results from this API call are paginated. This call will return the first 100 entries from the first page of the register. Use `page-size` to define the number of entries you want and `page-index` to define the pages you want. The maximum `page-size` is 5000.*

Example URL: https://local-authority-eng.register.gov.uk/entries?start=1&limit=10

Example request: `curl --request GET --url 'https://local-authority-eng.register.gov.uk/entries?start=1&limit=10' --header 'accept: application/json'`

Example response:

```
[
  {
    "entry-number": "1",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:6c4c815895ea675857ee4ec3fb40571ce54faf5ebcdd5d73a2aae347d4003c31"
  },
  {
    "entry-number": "2",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:37dd060a3efa6d5bf16f876e08fa867210f424e2e4a7989d0322218f6772332d"
  },
  {
    "entry-number": "3",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:01cda95d102807943d68f71bbe7b9b290dec2ebdb15967ca66820f825ece5831"
  },
  {
    "entry-number": "4",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:bdc17a29807f47a94cf612abf92fcadd2d83176f9ea419b4eeda23af2cf25ef9"
  },
  {
    "entry-number": "5",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:37ca110698ea569fc229e5042830384890ab1095737f1630c9de30692cfcf973"
  },
  {
    "entry-number": "6",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:792c58bf07b54a3a072c8c8a7e9b0681490e3cc76ee6e95da20434520b66d9c7"
  },
  {
    "entry-number": "7",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:99d5b1631c6241b31d4c22a867802035763649efa50cc8e4c5c25a71e484d412"
  },
  {
    "entry-number": "8",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:2cfa1b4bd729bde785a1fdb004c6be6a04eda3ed0ac1198401ef144b218545e0"
  },
  {
    "entry-number": "9",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:0cd1103a9b0e4dcd774f6c52a4d541e8a029e78ae609b46eb1d0546df9587a6a"
  },
  {
    "entry-number": "10",
    "entry-timestamp": "2016-10-21T16:11:20Z",
    "item-hash": "sha-256:00a2c66ab69086fd9ed8d43a46e04d1577340468bd43e8fb46dcf4d6ae59c439"
  }
]
```

### View a specific entry

Path: GET /entry/{entry-number}

Find a specific entry from a register. For example, an update to the record for the USSR in the country register.

Example URL: https://country.register.gov.uk/entry/204

Example request: `curl --request GET --url https://country.register.gov.uk/entry/204 --header 'accept: application/json'`

Example response:

```
{
  "entry-number": "204",
  "entry-timestamp": "2016-04-05T13:23:05Z",
  "item-hash": "sha-256:466d194d5100532edd115e3f0035967b09bc7b7f5fc444166df6f4a5f7cb9127"
}
```

### <a name="items"></a>View a specific item

Path: GET /item/{item-hash}

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

### <a name="downloadreg"></a>Download the full register

Path: GET /download-register

Download the full contents of the register in a ZIP file.
*Note: This will download every entry and item as an individual JSON file. If you only want to download records, use `GET /records`.*

Example URL: https://local-authority-eng.register.gov.uk/download-register

Example request: `curl -o country.zip --request GET --url https://local-authority-eng.register.gov.uk/download-register`

## Download updates from a register

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
