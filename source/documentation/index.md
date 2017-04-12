# Technical user documentation for registers

Registers are digital lists of accurate and up-to-date data about a particular topic from an authoritative source. For example, the [country register](https://country.register.gov.uk/) is a list of British English-language names and descriptive terms for countries. The [UK Government and Parliament petitions service](https://petition.parliament.uk/) uses the country register to populate a drop-down menu so a user can select their location.

Registers only provide raw data. You cannot use the APIs to search a register or match data. Depending on your requirements, you may have to build indexes on top of a register to fulfill specific requests.

## API changes - April 2017
As of 11 April 2017, it is now possible to have more than one item per entry. However, if you are using either the ``/record`` or ``/records`` resource on a register you should still only ever see one item per entry. This change has been made so that we can support multi-valued indexes in the future. The ``/record`` and ``/entry`` resources have also been changed to have a more consistent structure with /records and /entries respectively.

See the [API reference](https://registers-docs.cloudapps.digital/#api-reference) for more details and example responses or [contact the registers team](https://registers.cloudapps.digital/support.html) with any questions

## Using registers in a service

This is the API reference and general technical guide for registers built by Government Digital Service (GDS). This guide is for developers, technical architects, and other members of service teams interested in using registers in a service.

Register APIs provide a direct and standard way to access data so you can be confident the data in your service is accurate, up-to-date and authoritative.

You can use the data from registers to build menus and other widgets for forms. For example, you could use the country register to populate a menu for a user to select their location.

[Contact the GDS registers team](https://registers.cloudapps.digital/support.html) if you have any problems or questions that are not covered in this guide.
