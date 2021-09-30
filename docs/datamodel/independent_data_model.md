# Independend Data Model

The independend data model assumes that the datamodels used in the repository
could be used independently. This means that it is possible to install which
data model it is asked for without installing another one. Independently does
not mean that common code should not be used from all data models.



Each data model creates there own tables to store data model specific
informations. Each data model creates there own indices to search over those
records.

## Permissions
The permission has to be independend from the data model. This has the
implication that all data models have to implement the same root fields to
provide the permission management. This is done by providing components who will
handle the access management by the invenio framework.

## Landing Page
The best way to implement the landing page would be to have one path to the
landing page e.g. /record/4938-3833. The schema within the json will then be
used to distinguish which data model should be used to render the record.

## Search
One search page, one search slot to search over all data models. There has to be
a facet to filter for a special data model. So on the backend there has to be
the possibilty to search over all different indices. Each data model has to
provide the data model specific facets.

## Results View and Faceting

## Creation and Modification of Records

## Community Feature

## Secret Links

## Version of Records

## Modification History

## Pid Minting

## Linking of Records

## Export

## Notification Trigger

## Vocabularies

## Validation

## Statistics

