Get all records from a register.

Parameters: 

* `page-index` (Optional): Collection page number. Defaults to 1.
* `page-size` (Optional): Collection page size. Defaults to 100. Maximum is 5000. 

```http
GET /records/?page-index=1&page-size=3 HTTP/1.1
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

