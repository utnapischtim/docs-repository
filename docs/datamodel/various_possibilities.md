# Overview of different possibilities

There are four main possiblities to implement a new data model:

1. [customize fields](#custom-fields)
2. [master format](#master-format)
3. [independent data model](#independent-data-model)
4. [dependent data model](#dependent-data-model)

## custom fields

using the custom field mechanism implemented in the core. This provides the
possibility to create over a configuration file a new field. This configuration
provides the possibility to store a value in this field into the database
according to the record. Further it provides the possibility to create the field
in the upload process. Further it adds facets to the result page. (the custom
field configuration has also to provide if the custom field is shown to the
landing page, how it is displayed and where on the landing page)

this approach has the advantage that every new field (every new metadata entry)
would be stored into the rdm-records record json. All features of
invenio-rdm-records would be there.

The disadvantage of this approach would be to multiple custom fields if there is
intendet to implement a whole metadata standard like Marc21 or LOM.

go further to the [implementation details](custom_fields.md)

## master format

The master format version stores the record created in a special metadata
standard into a separated table. It maps the fields to invenio-rdm-records data
model and creates separated custom fields where necessary (e.g. missing storable
information in the invenio-rdm-records data model).

Advantage: after the master format record (e.g. marc21) is mapped to the
rdm-records standard all features came out of the box

disadavantage: mapping metadata into invenio-rdm-records could be hard. The
solution would then be to implement custom fields which could lead to the same
problems discussed in custom fields.

go further to the [implementation details](master_format.md)

## independent data model

the independent data model is totaly independend but provides the same
functionality as invenio-rdm-records but with a different metadata standard.

advantage: independent of invenio-rdm-records, totally customizable
disadvantage: maintainance hell. keeping up with invenio-rdm-records features
etc

go further to the [implementation details](independent_data_model.md)

## dependent data model

as of master format with independent data model. the trick is to use the
features (like versioning, drafts etc) from invenio-rdm-records but not creating
a mapping to invenio-rdm-records.

advantage: independency against invenio-rdm-records metadata standard, easier to
implement metadata standard own features, using invenio-rdm-records features
(versioning, secret links, community and so on)
disadvantage: dependend on invenio-rdm-records, not independend data model

go further to the [implementation details](dependent_data_model.md)
