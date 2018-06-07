## Linked registers

Registers can be linked by CURIEs and foreign keys. 

### CURIEs 

Any value in a field with a datatype of `curie` must be a CURIE. In registers, all CURIEs are of the form `{prefix}:{key}`, where `{prefix}` is mapped to a base URL `https://{register}.register.gov.uk/records/` for a given `{register}`. 

For example, [the `organisation` field in the `statistical-geography` register](https://field.register.gov.uk/records/organisation.json) has the datatype `curie`. In the [‘E09’ record of this register](https://statistical-geography.register.gov.uk/records/E09.json), the value of the `organisation` field is `government-organisation:D4`, so this resolves to the [‘D4’ record in the `government-organisation` register](https://government-organisation.register.gov.uk/records/D4). In this example, the `{key}` is ‘D4’ and the `{prefix}` is `government-organisation`, which maps to the base URL `https://government-organisation.register.gov.uk/records/D4`. 

You can see the datatype of any given `{field}` at `https://field.register.gov.uk/records/{field}`. 

### Foreign keys

Some fields are foreign keys which link to other registers. You can check this for a given `{field}` using the field register (`https://field.register.gov.uk/records/{field}`). 

For example, the [`local-authority-type` field is a foreign key](https://field.register.gov.uk/records/local-authority-type.json). In the `local-authority-eng` register, the `local-authority-type` field for each record links to a corresponding record in the `local-authority-type` register. In [the ‘SHE’ record of the `local-authority-eng` register](https://local-authority-eng.register.gov.uk/records/SHE.json), ‘NMD’ populates the `local-authority-type` field, so this resolves to [the ‘NMD’ record in the `local-authority-type` register](https://local-authority-type.register.gov.uk/records/NMD.json).  

