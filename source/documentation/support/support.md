## Troubleshooting 

### Error codes

| Error code | Description           |
|------------|-----------------------|
| 200        | Ok                    |
| 404        | Data not found        |
| 500        | Internal server error |

### Finding a specific record

If you cannot find a specific record, check you have the correct field value. You must use the exact field value to get a match from the register. For example, in the `local-authority-eng` register, you must capitalise the field value: 

Incorrect request: https://local-authority-eng.register.gov.uk/record/bir

Correct request: https://local-authority-eng.register.gov.uk/record/BIR

### Adding additional data 

If you want to combine register data with data from other sources, you may find it useful to keep the data from each source in separate files and combine them at a later stage. For example, you could keep separate files for data about countries and for data about territories.

### HTTPS

GOV.UK Registers follows government [HTTPS security guidelines](https://www.gov.uk/service-manual/technology/using-https). This means you must make sure your service (including APIs) is only accessible through secure connections. For web-based services this means HTTPS only, with an HTTP Strict Transport Security (HSTS).

### Technical specification

GDS maintains a [technical specification for registers](https://openregister.github.io/specification/).

## Contact us 

Please [contact the GDS Registers team](https://registers.cloudapps.digital/support.html) if you have difficulty using registers in your product or service.

