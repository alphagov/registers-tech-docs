### CURIEs 

Any value in a field with a datatype of `curie` must be a CURIE. In registers,
all CURIEs are of the form `{prefix}:{key}`, where `{prefix}` is mapped to a
base URL of the form `https://{register}.register.gov.uk/records` for a given
register (`{register}`). This means that when the `{key}` is blank, it
references the full set of records in that register.

For example, the `organisation` field
(`https://field.register.gov.uk/records/organisation`), which appears in the
`statistical-geography` register, has the datatype `curie`. In [the ‘E09’
record of this
register](https://statistical-geography.register.gov.uk/records/E09.json), the
value of the `organisation` field is `government-organisation:D4`. The
`{prefix}` is `government-organisation`, which maps to the URL
`https://government-organisation.register.gov.uk/records`, and the `{key}` is
‘D4’. The expanded URL is therefore
`https://government-organisation.register.gov.uk/records/D4`.
