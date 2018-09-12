### Choose a response format 

Choose a response format by adding the appropriate suffix to the request URL:

| Format | Suffix | Media type |
|--------|--------|------------|
| JSON | .json | application/json |
| CSV | .csv | text/csv |

For example: 

```
curl https://country.register.gov.uk/records/GB.json 
```

You can also specify a format by making a request with the `Accept` header. For example:

```
curl https://country.register.gov.uk/records/GB --header 'Accept: application/json' 
