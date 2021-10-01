# Dependend Data Model

The dependent data model assumes that the invenio-rdm-records data model is the
root for all data models ever implemented for InvenioRDM. It serves as a
"library" to create other data models by providing the components to create
access management, versioning etc. This implies that the invenio-rdm-records
data model has to be installed otherwise it is not possible to have a
repository.

The main difference to the independent data model is that the
invenio-rdm-records data model is installed out of the box.

## Permissions

## Landing Page

## Search
The search is the crucial part of dependent and independend data models. They
have both the same problem. Also the master format has more or less the same
problem. The master format tries to solve that problem with the custom fields.
But the custom fields could also be used for the dependend and independend data
model.

custom fields could be designed in a way to be extend one of the data models or
the whole repository so for every data model, but the representation would be
different in the different data models. The custom fields could also be used to
serve as a middle layer for the search. For the search itself it seams not
necessary, but for the result view and the faceting it may be helpful.

The search has to be designed in a way, that the search is searching over
multiple indices. This will return objects in different standards.

Here we could use different ways to solve that problem. We can implement
serializers to map the dependend data model to rdm-records before it is indixed,
it could also be stored in one, but with differend endpoints. This is not really
a good option because it reproduces the mapping problem, which could be solved
by the master format which we are not talking here.

the other way would be to not use a serializer but to store it in a way that is
normal for that current data model metadata standard. That should then not be a
problem to render the records. The record itself also has a attribute to list
the schema which is used for so the renderer should find the template/component
to render this json record object.

the real problem are the faceting

## Results View and Faceting

the results view is described in the search above. but the faceting i will
describe here.

I think the faceting is the real hard part of the whole concept and it is the
same problem as in all other ways to implement it.

There should be a special form of custom fields for it. (or it could be a custom
field, but only the faceting is implemented, custom fields should have the
possibility to decide which part should be visible on all parts of the
repository and which not) This facet field should then be possible to
search/collect the information needed to work in all indices. If a index is not
providing the special things it is not listed on the facet.

Some special metadata keys would then be only served by one of the data models.
This would lead to that using that facet would filter out all other records from
other data models. Which would be what is intended.

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


