Get all entries from a register.

Parameters: 

* `start` (Optional): Collection page number. Defaults to 1.
* `limit` (Optional): Collection page size. Defaults to 100. Maximum is 5000. 

```http
GET /entries/?start=1&limit=10 HTTP/1.1
Host: local-authority-eng.register.gov.uk
Accept: application/json
Authorization: YOUR-API-KEY-HERE
```

```http
HTTP/1.1 200
Content-Type: application/json
Link: <?start=11&limit=10>; rel="next"


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
