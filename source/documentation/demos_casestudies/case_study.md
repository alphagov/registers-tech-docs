### Case study

**E-petitions**

The [UK Government and Parliament petitions service](https://petition.parliament.uk/) uses the country register to populate a drop-down menu.

To sign a petition, users are asked to select their location. The menu options come from the country register. The petitions service team have added additional areas that are not recognised as official countries by the FCO, for example Taiwan and the Occupied Palestinian Territories. Because the menu includes more than just countries, the service team have labelled the field ‘Location’ rather than ‘Country’.

The initial values in the database are set by a migration script, which has a hardcoded snapshot of the country register at a point in time, along with some other hardcoded locations such as American Samoa.

Every night, the e-petitions team run a job to read the country register and update every matching location in the database if it has changed. There are other locations in the table which are not in the country register and are left alone by the job.
