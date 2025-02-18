
# I-Adopt JSON schema - original (Schema)

`ogc.oms.obs-props.iadopt-schema` *v1.0*

Defines a JSON schema for observable properties - based on the I-ADOPT model

[*Status*](http://www.opengis.net/def/status): Under development

## Examples

### Example 1
#### json
```json
{
  "@context": "https://w3id.org/iadopt/Variable.context.jsonld",
  "@id": "http://vocab.nerc.ac.uk/collection/P01/current/IC000344/",
  "@type": "https://w3id.org/iadopt/ont/Variable",
  "label": "concentration of endosulfane sulfate in wet flesh of ostrea edulis",

  "property": {
    "@type": [ "https://w3id.org/iadopt/ont/Property" ],
    "@id": "http://vocab.nerc.ac.uk/collection/S06/current/S0600045/",
    "label": "concentration"
  },

  "ooi": {
    "@type": [ "https://w3id.org/iadopt/ont/Entity" ],
    "@id": "http://vocab.nerc.ac.uk/collection/S27/current/CS003625/",
    "label": "endosulfane sulfate"
  },

  "matrix": {
    "@type": [ "https://w3id.org/iadopt/ont/Entity" ],
    "@id": "http://vocab.nerc.ac.uk/collection/S12/current/S1214/",
    "label": "flesh"
  },

  "context": {
    "@type": [ "https://w3id.org/iadopt/ont/Entity" ],
    "@id": "http://marinespecies.org/aphia.php?p=taxdetails&id=140658",
    "label": "ostrea edulis"
  },

  "constraint": {
    "@type": [ "https://w3id.org/iadopt/ont/Constraint", "http://purl.obolibrary.org/obo/PATO_0001823" ],
    "label": "wet",
    "constrains": [ "http://vocab.nerc.ac.uk/collection/S12/current/S1214/" ]
  }

}

```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Original IADOPT schema
allOf:
- $ref: https://raw.githubusercontent.com/SirkoS/iadopt-schema/refs/heads/main/json/Variable.schema.json

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/observable-properties/build/annotated/oms/obs-props/iadopt-schema/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/observable-properties/build/annotated/oms/obs-props/iadopt-schema/schema.yaml)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/observable-properties](https://github.com/ogcincubator/observable-properties)
* Path: `_sources/iadopt-schema`

