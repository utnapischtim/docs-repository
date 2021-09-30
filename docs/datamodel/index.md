# Data Model

This chapter describes how to choose which implementation approach should be
used to implement a new data model for the repository.

# What a Data Model should fulfil

![](images/data-model.png?raw=true)

The next part is to discuss the implementation details. All variants have to
fulfil the same things. The implementation effort is different.

1. permission handling of the records
    * owner
    * group
    * curator
2. landing page
3. search
    * over all records
    * specialized in one data model
4. results view and faceting
5. creation and modification of records
6. community feature
    * link a record with a community
    * give a community access to a record
    * give a community access to a type of record
7. secret links
8. versioning of records (new doi)
9. modification history (who did when what)
10. pid minting
    * one id over the whole repository
    * doi minting
11. linking of records
    * internal
        * publication with research data (maybe different data models)
        * journal -> volume -> issue -> article
        * book -> chapter -> subchapter -> subsubchapter
        * create collections
    * external
        * publication with related work
12. export
    * OAI-PMH (set over the whole data model, set over defined records e.g. by the
     community)
    * landing page exporter (formats (json, xml), metadata standards (marc21,
     datacite, dublin core etc), citations (bibtex))
13. notification trigger
    * newly added type
14. vocabularies
15. validation
    * syntax
    * semantic
16. statistics
17. custom fields

The next step is do ready about the [different
possibilities](various_possibilities.md) to implement the points above.


