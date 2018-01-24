## Support 

### Error codes

| Error code | Description           |
|------------|-----------------------|
| 200        | Ok                    |
| 404        | Data not found        |
| 500        | Internal server error |

### Common issues

**Registers still in beta**

Despite the beta label, registers in beta are reliable and ready for use in products and services.

**If you can't find a specific record**

If you can't find a specific record, check you have the correct field value. You must use the exact field value to get a match from the register. For example, in the `local-authority-eng` register, you must capitalise the field value: 

Incorrect request: https://local-authority-eng.register.gov.uk/record/bir

Correct request: https://local-authority-eng.register.gov.uk/record/BIR

**Adding additional data**

If you want to combine register data with data from other sources, you may find it useful to keep the data from each source in separate files and combine them at a later stage. For example, you could keep separate files for data about countries and for data about territories.

### Technical specification

GDS maintains a [technical specification for registers](https://openregister.github.io/specification/).

## Contact us 

If you experience difficulties using registers in your product or service, please [contact the GDS registers team](https://registers.cloudapps.digital/support.html).

