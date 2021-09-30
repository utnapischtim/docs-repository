# Master Format

the idea is to implement a new metadata standard in a way that features like
searchability are supported by the rdm-records datamodel. That should be
achieved by storing the master format in a separated table and map all fields
from it to the rdm-records datamodel. To implement that in a way that no
information is lost it would be necessary to create some custom fields for the
rdm-records data model.

The master format is used only to create/modify a record in that metadata
standard. The the landing page and the search results are rendered with the
metadata of the rdm-records version of that record. This has the benefit that
all features (e.g. permissions, secret links, community) of rdm-records would
work with the new metadata standard.

The master format could be implemented without custom fields but then it would
be that a lot of additional information which the new metadata standard would
provide is lost in the mapping from the new standard to the rdm-records
standard. If this would really be ok then it is worth to think if the new
standard really gives that much of additional information over the rdm-records
standard.

## Permissions
the permissions would be implemented like normal rdm-records. It has to be
passed through from the UI to create/modify the records of the master format to the
rdm-records version of it.

## Landing Page
The landing page could be rendered with the information of the rdm-records
version of the master format. The custom fields would help to display the more
information what the new metadata standard would bring.

## Search
The search would work like the search of a normal rdm-records record.

## Results View and Faceting
The same as normal rdm-records records

## Creation and Modification of Records
To create and modify a record it has to be implemented a new user interface. A
endpoint has to be provided to save the records. This endpoint would do also the
conversion(mapping) to a rdm-records record and would store that record
afterwards.

Depending on the new metadata standard react components from the rdm-records
could be reused or not.

## Community Feature
the linking with communities or in general all connections from and to a
community from the record would be implemented in a sense of a proxy react
component. It has to passed through to the rdm-records version of the record.

## Secret Links
same as the community feature by passing it through to the rdm-records instance
of the record

## Version of Records
pass it through

## Modification History
The modification history has to be implemented in the master format. This has to
be decided for every new metadata standard if it is necessary to know or not.

## Pid Minting
the pid has to be provided by the rdm-records version of the record.

## Linking of Records
the rdm-records has to provide all possible linking options. The problem is the
linking could not be implemented in the master format because the rdm-record
instance of a record is used to render the content. But if this record does not
know how to handle different linking scenarios it could not be simulated by the
master format.

## Export
it should be provided by the rdm-records module. otherwise it would be necessary
to create a special endpoint for that master format. but that should normally
not be done. if a new export is really necessary it would be better to implement
it for the rdm-records datamodel.

## Notification Trigger
if implemented then used from rdm-records

## Vocabularies
reuse of the already existing vocabularies but pass it to the UI of the master
format. Maybe implement new vocabularies for the new master format. This should
be discussed with the core team if it would bring benefits for the rdm-records
to so it should be implemented there!

## Validation
the validation has to be done on the master format so it has to be implemented
newly

## Statistics
should come out of the box
