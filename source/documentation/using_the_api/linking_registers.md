## Linked registers

Registers can be linked by 

### How to resolve foreign keys

A field is a foreign key to another register if the `register` field in the record of the field register (`https://field.{domain}/records/{field}`) is populated. 

For example, the `local-authority-type` field is [a foreign key to the `local-authority-type` register](https://field.register.gov.uk/records/local-authority-type.json). `NMD` populates [the `SHE` record of this register](https://local-authority-eng.register.gov.uk/records/SHE.json), so this resolves to [the `NMD` record in the `local-authority-type` register](https://local-authority-type.register.gov.uk/records/NMD.json).  

### How to resolve CURIEs

Any value in a field with a datatype of `curie` is a CURIE. In registers, all CURIEs are of the form `https://{register}.{domain}/records/{key}`. 

For example, [the `organisation` field in the `statistical-geography` register](https://field.register.gov.uk/records/organisation.json) is a CURIE. In the [‘E09’ record of this register](https://statistical-geography.register.gov.uk/records/E09.json), the value of the `organisation` field is `government-organisation:D4`, so this resolves to the [‘D4’ record in the `government-organisation` register](https://government-organisation.register.gov.uk/records/D4.json). 






