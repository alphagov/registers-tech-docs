## <a name="availablereg"></a>Available open registers

There are many open registers currently in discovery and alpha. These include open registers of territories, local authorities, and schools.

The country register is in beta, but available to use in your service.

### Country register

The [country register](https://country.register.gov.uk/) is a list of British-English language country names. This register is maintained by the Foreign and Commonwealth Office (FCO) and is currently in beta.

The country register doesn’t include territories, for example, Taiwan, Gibraltar, and the Occupied Palestinian Territories. These are included in the territories register, which is in discovery.

The country register contains the following fields:  

* `country` (a 2 letter ISO 3166-2 code)  
* `name` (commonly used name of a country)  
* `official-name` (official name of a country)   
* `citizen-names` (name of the citizens of a country)  
* `start-date` (when the country was first recognised)  
* `end-date` (when the country was dissolved or changed its name)   

You may need to remove records with an end-date, such as East Germany, if your service or product only requires data about existing countries.

### Local authorities (England) register

The [register of local authorities in England](https://local-authority-eng.register.gov.uk/) is maintained by the Department for Communities and Local Government.

The register contains the following fields:     

* `local-authority-eng` (3 letter ISO code or equivalent)  
* `local-authority-type` (type of local government organisation)  
* `name`(commnonly used name of a local authority)  
* `official-name`(official name of local authority)  
* `start-date` (when the local authority was first established)  
* `end-date`(when the local authority was dissolved or changed its name)  

You may need to remove records with an end-date if your service or product only requires data about existing local authorities.
