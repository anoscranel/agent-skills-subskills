---
name: modeling-and-ontologies
domain: software-engineering/modeling-and-ontologies
trigger: "Designing the ontology or shared vocabulary for a domain."
anti_trigger: "Not for the SPARQL queries, and not for entity resolution across sources."
scope: "Classes, properties, and ontology design."
status: seedling
---

# Modeling and ontologies

## Standard

An ontology is the shared vocabulary of a knowledge graph: the classes things belong to, the properties that relate them, and the constraints that govern those relationships. A class is a category such as Person or Product; a property is a relationship type such as worksFor or hasPrice; a constraint states rules such as a Person worksFor at most one Organisation at a time. The ontology is what lets independent parties interpret the same data the same way.

Good ontology design starts from competency questions: the questions the ontology must answer, written before any class is named. The design then covers the domain's scope without trying to model everything. Classes are chosen to be useful distinctions, properties to be reusable across classes, and constraints to be only as strong as the domain genuinely requires. Over-constraining is as harmful as under-modeling: a rule that is too strong excludes valid data, and an ontology that tries to capture every nuance becomes unmaintainable. Reusing an established vocabulary where one fits is almost always better than inventing a new one.

Primary sources: <https://en.wikipedia.org/wiki/Ontology_(information_science)> and <https://www.w3.org/TR/owl2-overview/>.

## Decision rules

- Write competency questions before naming any class or property.
- Model the scope the questions require, not the whole domain.
- Choose classes for useful distinctions and properties for reuse.
- Constrain only as strongly as the domain genuinely requires.
- Reuse an established vocabulary where it fits before inventing new terms.
- Keep the ontology as small as the questions allow; every term has a maintenance cost.

## Procedure

1. Write the competency questions the ontology must answer.
2. Survey existing vocabularies for reusable terms.
3. Enumerate the classes and the properties between them.
4. Define each class and property with a clear, written definition.
5. Add only the constraints the questions actually depend on.
6. Test the ontology by answering the competency questions against sample data.

## Anti-patterns

- Modeling the whole domain instead of the required scope.
- Inventing new terms where an established vocabulary fits.
- Constraints so strong they exclude legitimate data.
- Classes named without written definitions.
- An ontology that cannot answer its own competency questions.

## Done checklist

- [ ] Competency questions written first.
- [ ] Existing vocabularies surveyed for reuse.
- [ ] Classes and properties enumerated with definitions.
- [ ] Constraints limited to what the questions require.
- [ ] Ontology kept minimal for the scope.
- [ ] Competency questions answered against sample data.

## Sources

- Ontology (information science): <https://en.wikipedia.org/wiki/Ontology_(information_science)>
- OWL 2 overview: <https://www.w3.org/TR/owl2-overview/>
- schema.org getting started: <https://schema.org/docs/gs.html>
