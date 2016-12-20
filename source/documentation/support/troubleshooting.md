Please find information below about common problems when using open registers. If your issue is not included or you are struggling to use open registers in your product or service, please contact the GDS open registers team at <a href="mailto:registerteam@digital.cabinet-office.gov.uk">registerteam@digital.cabinet-office.gov.uk</a>.

### Error codes

| Error code | Description           |
|------------|-----------------------|
| 200        | Ok                    |
| 404        | Data not found        |
| 500        | Internal server error |

### Common issues

**Open registers still in beta**

A register must pass certain criteria to move from discovery through to live. To move from beta to live, duplicate lists of the same information must be removed. For example, the country register will remain in beta until duplicate lists of countries are removed.  

Despite the beta label, open registers in beta are reliable to use in products and services.

**If you can't find a specific record**

If you can't find a specific record, check you have the correct field value. You must use the exact field value to get a match from the register. For example, in the country register the field value must be in capital letters.

Incorrect request: https://country.register.gov.uk/record/gb

Correct request: https://country.register.gov.uk/record/GB

**End-date field**

The `end-date` field is used to note when an entry ceases to be valid. For example, in the country register, the end-date field contains the date when a country was dissolved or changed its name. For example, the `end-date` field value for East Germany is `1990-10-02`.

You may need to remove records with an end-date if your product or service only requires data on existing countries.

**Missing countries in country register**

The country register only contains countries recognised by the Foreign and Commonwealth Office. As such, the country register does not contain territories such as Gibraltar and the Occupied Palestinian Territories. These are included in the territories register, which is in discovery.

**Adding additional data**

If you want to combine register data with data from other sources, it can be useful to keep the data from each source in separate files and combine them at a later stage. For example, you could keep separate files for data about countries and data about territories.
