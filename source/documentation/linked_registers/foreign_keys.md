### Foreign keys

Some fields in registers are foreign keys which link to other registers. A
given field (`{field}`) is a foreign key to another register if the `register`
field is populated at `https://field.register.gov.uk/records/{field}`.  

For example, the `local-authority-type` field is a foreign key, and has the
URL `https://field.register.gov.uk/records/local-authority-type`. It’s used in
the `local-authority-eng` register. This means that the `local-authority-type`
field for each record in the `local-authority-eng` register links to a
corresponding record in the `local-authority-type` register. 

In the same example, the ‘SHE’ record of the `local-authority-eng` register
has the URL `https://local-authority-eng.register.gov.uk/records/SHE`. The
`local-authority-type` field here is populated by `NMD`, so this resolves to
the ‘NMD’ record in the `local-authority-type` register, which has the URL
`https://local-authority-type.register.gov.uk/records/NMD`.  
 
