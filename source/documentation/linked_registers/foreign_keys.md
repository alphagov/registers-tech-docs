### Foreign keys

Some fields in registers are foreign keys which link to other registers. 

To find this out, you can look at `https://field.register.gov.uk/records/{field}`. A field is a foreign key to another register if the `register` field is populated at this address. 

The `local-authority-type` field is a foreign key: `https://field.register.gov.uk/records/local-authority-type`. It’s used in
the `local-authority-eng` register. This means that the `local-authority-type`
field for each record in the `local-authority-eng` register links to a
corresponding record in the `local-authority-type` register. 

For example, the ‘SHE’ record of the `local-authority-eng` register
has the URL `https://local-authority-eng.register.gov.uk/records/SHE`. The
`local-authority-type` field here is populated by `NMD`, so this resolves to
[the ‘NMD’ record in the `local-authority-type` register](https://local-authority-type.register.gov.uk/records/NMD). 
 
