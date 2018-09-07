### Choose a response format 

Choose a response format by adding the appropriate suffix to the request URL:

| Format | Suffix | Media type |
|--------|--------|------------|
| JSON | .json | application/json |
| YAML | .yaml | text/ yaml |
| CSV | .csv | text/csv |
| TSV | .tsv | text/tsv |
| Turtle | .ttl | text/ttl |

For example: 

```
curl https://country.register.gov.uk/records/GB.json 
```

You can also specify a format by making a request with the `Accept` header. For example:

```
curl https://country.register.gov.uk/records/GB --header 'Accept: application/json' 
