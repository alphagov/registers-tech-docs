### CURIEs 

Any value in a field with a datatype of `curie` must be a CURIE. 

For a given register, all CURIEs are of the form `{prefix}:{key}`, where `{prefix}` is mapped to a
base URL of the form `https://{register}.register.gov.uk/records/`. This means that when the `{key}` is blank, it
references the full set of records in that register.

For example, the [datatype of the `organisation` field is `curie`](`https://field.register.gov.uk/records/organisation`). In the [‘E09’ record of the `statistical-geography` register](https://statistical-geography.register.gov.uk/records/E09.json), the value of the `organisation` field is `government-organisation:D4`. This means that 'E09' in `statistical-geography` links to 'D4' in the `government-organisation` register. 

In the example, 
`{prefix}` is `government-organisation` and `{key}` is
‘D4’. The full expanded URL is therefore
`https://government-organisation.register.gov.uk/records/D4`.

