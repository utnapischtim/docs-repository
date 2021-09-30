# Custom Fields

The following part describes how a data model could be extended by custom
fields. Custom fields could then used to implement another metadata standard
beside the rdm records metadata model

## Configuration of a Custom Field

```python
CUSTOM_FIELD_LIST.append({
  "metadata": {
    "title": TITLE_METADATA,
    "validate": TITLESchema,
  },
  "ui": {
    "title": TITLE_UI,
    "component": PATH_TO_REACT_COMPONENT,
  },
  "landingpage": {
    "title": TITLE_LANDINGPAGE,
    "template": PATH_TO_JINJA_TEMPLATE,
    "type": "sidebar|main|detail",
  },
  "permission": "rwq:rwq:rwq"
  "type": "vocabulary|number|str|custom",
  "vocabulary": {
    "table": TABLE_NAME,
    "url": URL,
    "file": FILE_PATH,
  },
  "history": BOOLEAN,
  "search": {
    "facet": BOOLEAN,
    "mapping": MAPPING,
    "template": PATH_TO_TEMPLATE
  },
})
```

```python
BOOLEAN: true|false
permission: r...read, w...write, q...queryable
permission: OWNER:GROUP:ALL

class TITLESchema(CustomFieldBaseSchema):
    ...
```

## Defintions
custom field config (cfg) is the configuration mentioned above

## Permission
the permission of custom fields should be set separatelly with the "permission"
key of the cfg. The default value is the permisson of the whole rest of the
data model. but it should be possible to set it directly for the custom field.
This has the benefit that it is also possible to create fields for notes which
should not be visible outside. The "permission" key is a explicit way to
indicate if this value should be visualized or not. If a missing "landingpage"
key is used for not rendering then this removes the possibility to have a
default landingpage rendering mechanism.

## Landing Page
the landing page is handled by the "landingpage" key. The template of it
gives the possibilty to create special html for it, but it is also possible to
visualize it only with a "key -> value" pair indicated by the "title" key. The
"type" key indicates where the custom field should be rendered. For now it is
possible with "sidebar" "main" and "detail". This should be extended!

## Metadata
the "metadata" key indicates how the custom field should be named in the stored
json of the record. The "validation" key gives the possibility to validate the
custom field with the given schema class.

## Type
the "type" key indicates which type the custom field has. This type is used to
distinguish which default template is used for rendering th custom field on the
upload page.

## Vocabulary
the "vocabulary" key has three possibility to provide a vocabulary. It could be
by a table, by a url and by a file. The table has to be created separatelly but
it has to be there when the field is used then. The url should be a endpoint to
a rest interface to collect the vocabulary in a special (to define)
format/standard. The file should contain the same information as the url would
provide.

## History
this key is a boolean key and it indicates if the custom field should have a
creation/modify history.

## Search
the "search" key defines the mapping if the key is searchable defined by the
"permission" key. Further it also defines a template to render the field if it
should be rendered in the result item. Further a "facet" boolean key is there to
indicate if it should be possible to create a facet of it.
