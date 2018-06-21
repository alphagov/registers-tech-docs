## Linked registers

Registers can be linked by CURIEs and foreign keys. 

In registers, CURIEs are a datatype, and all new registers will only be linked by CURIEs. Foreign keys are fields, and not defined by a single datatype.

You can find the datatype of any given field (`{field}`) at `https://field.register.gov.uk/records/{field}`. 

### CURIEs 

Any value in a field with a datatype of `curie` must be a CURIE. In registers, all CURIEs are of the form `{prefix}:{key}`, where `{prefix}` is mapped to a base URL of the form `https://{register}.register.gov.uk/records/` for a given register (`{register}`). This means that when the `{key}` is blank, it references the full set of records in that register.

For example, the `organisation` field (`https://field.register.gov.uk/records/organisation`), which appears in the `statistical-geography` register, has the datatype `curie`. In [the ‘E09’ record of this register](https://statistical-geography.register.gov.uk/records/E09.json), the value of the `organisation` field is `government-organisation:D4`. The `{prefix}` is `government-organisation`, which maps to the URL `https://government-organisation.register.gov.uk/records/`, and the `{key}` is ‘D4’. The expanded URL is therefore `https://government-organisation.register.gov.uk/records/D4`.

### Foreign keys

Some fields in registers are foreign keys which link to other registers. A given field (`{field}`) is a foreign key to another register if the `register` field is populated at `https://field.register.gov.uk/records/{field}`.  

For example, the `local-authority-type` field is a foreign key, and has the URL `https://field.register.gov.uk/records/local-authority-type`. It’s used in the `local-authority-eng` register. This means that the `local-authority-type` field for each record in the `local-authority-eng` register links to a corresponding record in the `local-authority-type` register. 

In the same example, the ‘SHE’ record of the `local-authority-eng` register has the URL `https://local-authority-eng.register.gov.uk/records/SHE`. The `local-authority-type` field here is populated by `NMD`, so this resolves to the ‘NMD’ record in the `local-authority-type` register, which has the URL `https://local-authority-type.register.gov.uk/records/NMD`.  
 
