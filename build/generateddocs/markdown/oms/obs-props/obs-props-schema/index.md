
# ObservableProperties JSON schema (Schema)

`ogc.oms.obs-props.obs-props-schema` *v1.1*

Local copy for working

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
$defs:
  entity:
    '@type': object
    '@id': string
    required:
    - '@id'
  constraint:
    type: object
    properties:
      constrains:
        '@type': string
      '@type':
        description: Type definition has to include iadopt:Constraint.
        type:
        - string
        - array
        items:
          type: string
        contains:
          const: https://w3id.org/iadopt/ont/Constraint
        pattern: https://w3id.org/iadopt/ont/Constraint
    required:
    - constrains
type: object
properties:
  '@id':
    type: string
  '@type':
    description: Type definition has to include iadopt:Variable.
    type:
    - string
    - array
    items:
      type: string
    contains:
      const: https://w3id.org/iadopt/ont/Variable
    pattern: https://w3id.org/iadopt/ont/Variable
  property:
    $ref: '#/$defs/entity'
  ooi:
    $ref: '#/$defs/entity'
  objectofinterest:
    $ref: '#/$defs/entity'
  matrix:
    $ref: '#/$defs/entity'
  context:
    description: contextObject can either be a single entity or an array of entities
    anyOf:
    - type: array
      items:
        $ref: '#/$defs/entity'
    - $ref: '#/$defs/entity'
  contextobject:
    description: contextObject can either be a single entity or an array of entities
    anyOf:
    - type: array
      items:
        $ref: '#/$defs/entity'
    - $ref: '#/$defs/entity'
  constraint:
    description: constraint can either be a single Constraint or an array of Constraints
    anyOf:
    - type: array
      items:
        $ref: '#/$defs/constraint'
    - $ref: '#/$defs/constraint'
allOf:
- required:
  - '@id'
  - '@type'
  - property
- oneOf:
  - required:
    - context
  - required:
    - contextobject
  - properties:
      context:
        not: {}
      contextobject:
        not: {}
- oneOf:
  - required:
    - ooi
  - required:
    - objectofinterest

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/observable-properties/build/annotated/oms/obs-props/obs-props-schema/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/observable-properties/build/annotated/oms/obs-props/obs-props-schema/schema.yaml)

## Sources

* [Original](https://github.com/SirkoS/iadopt-schema/blob/main/json/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/observable-properties](https://github.com/ogcincubator/observable-properties)
* Path: `_sources/obs-props-schema`

