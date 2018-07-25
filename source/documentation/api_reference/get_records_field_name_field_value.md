Get all records that share a `field-value` for a particular `field-name`.

Parameters: 

* `field-name` (Required): Field name. 
* `field-value` (Required): Field value. 
* `page-index` (Optional): Collection page number. Defaults to 1.
* `page-size` (Optional): Collection page size. Defaults to 100. Maximum is 5000. 

```http
GET /records/local-authority-type/CTY/?page-index=1&page-size=3 HTTP/1.1 
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
