
# I-ADOPT SHACL - Crispae version (Model)

`ogc.oms.obs-props.iadopt-rules-c` *v0.1*

Uses the proposed version to validate examples

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 4

Goal: Define a Building Block for a semantic data model

This approach is appropriate where a given schema is one of many possible schemas for the same underlying semantic model, and allows defining the model and logical constraints independently, with re-usable validation rules and unit testing advantages.

### Steps
- uncomment line
- examine file "ontology.ttl"
- run build
- run viewer
- navigate to "Exercise 9"/Ontology and examine classes
- view validation results on "about tab"
- view validation results at [Validation Report](validation) or [build-local/...](/register/build-local/tests/bbr/template/exercise3/_report.json)
## Examples

### air temperature at 1.7 meter
#### ttl
```ttl
@prefix iadopt: <https://w3id.org/iadopt/ont/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix envthes: <http://vocabs.lter-europe.net/EnvThes/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dc: <http://purl.org/dc/terms/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

iadopt:Variable
  rdfs:label "Variable" ;
  a owl:Class .

iadopt:hasProperty
  rdfs:comment "A Variable has a Property that characterizes an Entity." ;
  rdfs:label "hasProperty" .

iadopt:hasMatrix
  rdfs:subPropertyOf iadopt:hasContextObject ;
  rdfs:comment "A Variable might have an Entity in which the ObjectOfInterest is contained." ;
  rdfs:label "hasMatrix" .

envthes:
  skos:prefLabel "EnvThes"@en ;
  a owl:Ontology, skos:ConceptScheme .

iadopt:hasObjectOfInterest
  rdfs:comment "A Variable has an Entity whose Property is observed." ;
  rdfs:label "hasObjectOfInterest" .

envthes:30377
  skos:inScheme envthes: ;
  skos:altLabel "temperature of air at 1.7 meter"@en ;
  dc:modified "2024-10-14"^^xsd:date ;
  dc:created "2024-10-14"^^xsd:date ;
  iadopt:hasProperty <http://qudt.org/vocab/quantitykind/Temperature> ;
  skos:definition "Temperature of the air in a height of 1.7 meter"@en ;
  iadopt:hasConstraint envthes:30375 ;
  iadopt:hasMatrix <https://vocabulary.actris.nilu.no/actris_vocab/troposphere> ;
  skos:broader envthes:30333 ;
  iadopt:hasObjectOfInterest envthes:23 ;
  a iadopt:Variable, skos:Concept ;
  skos:prefLabel "air temperature at 1.7 meter"@en .

iadopt:hasConstraint
  rdfs:comment "A Variable has a Constraint, that confines an Entity involved in the observation." ;
  rdfs:label "hasConstraint" .

envthes:30333
  skos:prefLabel "near-surface air temperature"@en ;
  a iadopt:Variable, skos:Concept ;
  skos:narrower envthes:30377 .

envthes:30375
  skos:prefLabel "1.7 meter above ground"@en ;
  a iadopt:Constraint, skos:Concept ;
  iadopt:constrains envthes:23 .

envthes:23
  skos:prefLabel "αέρας"@el, "oras"@lt, "vzduch"@sk, "vzduch"@cs, "ilma"@fi, "õhk"@et, "ar"@pt, "air"@fr, "air"@en, "luft"@sv, "luft"@no, "luft"@da, "powietrze"@pl, "هواء"@ar, "Luft"@de, "Въздух"@bg, "lucht"@nl, "aer"@ro, "aire"@es, "zrak"@sl, "zrak"@hr, "aria"@it, "levegő"@hu, "gaiss"@lv ;
  a skos:Concept .

```

## Sources

* [Link to source](https://i-adopt.github.io/ontology)
* [ALternative SHACL](https://github.com/Crispae/IADOPT-shacl/blob/main/shapes/iadopt-shapes.ttl)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/observable-properties](https://github.com/ogcincubator/observable-properties)
* Path: `_sources/iadopt-rules-c`

