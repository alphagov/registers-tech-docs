## Linked registers

Registers can be linked by CURIEs and foreign keys. CURIEs are the preferred mechanism, and all new registers will only use CURIEs.

### CURIEs 

Any value in a field with a datatype of `curie` must be a CURIE. In registers, all CURIEs are of the form `{prefix}:{key}`, where `{prefix}` is mapped to a base URL `https://{register}.register.gov.uk/records/` for a given `{register}`. 

For example, [the `organisation` field in the `statistical-geography` register](https://field.register.gov.uk/records/organisation) has the datatype `curie`. In the [‘E09’ record of this register](https://statistical-geography.register.gov.uk/records/E09), the value of the `organisation` field is `government-organisation:D4`. The `{key}` is ‘D4’ and the `{prefix}` is `government-organisation`, which maps to the URL `https://government-organisation.register.gov.uk/records/`. The expanded URL is therefore `https://government-organisation.register.gov.uk/records/D4`.

You can see the datatype of any given field at `https://field.register.gov.uk/records/{field}`. 

### Foreign keys

Some fields are foreign keys which link to other registers. A field is a foreign key to another register if the `register` field in the record of the field register is populated (`https://field.register.gov.uk/records/{field}`). 

For example, the `local-authority-type` field is a foreign key, and has the URL `https://field.register.gov.uk/records/local-authority-type`. In the `local-authority-eng` register, the `local-authority-type` field for each record links to a corresponding record in the `local-authority-type` register. In this example, the ‘SHE’ record of the `local-authority-eng` register has the URL `https://local-authority-eng.register.gov.uk/records/SHE`. The `local-authority-type` field here is populated by `NMD`, so this resolves to the ‘NMD’ record in the `local-authority-type` register, which has the URL `https://local-authority-type.register.gov.uk/records/NMD`.  

