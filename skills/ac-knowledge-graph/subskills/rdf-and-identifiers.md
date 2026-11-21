---
name: rdf-and-identifiers
domain: software-engineering/rdf-and-identifiers
trigger: "Representing data as RDF triples with stable identifiers."
anti_trigger: "Not for OWL reasoning, and not for the ontology's class design."
scope: "Triples, URIs, blank nodes, and RDF serialisations."
status: seedling
---

# RDF and identifiers

## Standard

The Resource Description Framework represents knowledge as triples: a subject, a predicate, and an object. The subject is the entity being described, the predicate is the property, and the object is either another entity or a literal value. Every fact in a knowledge graph is one such statement, and a set of triples forms a directed, labelled graph. This simple, uniform structure is what lets data from any source be merged without a shared schema up front.

Identifiers are the load-bearing decision. Entities and predicates are named by URIs, which are globally unique and can be dereferenced to find more information. A URI is a name, not merely a string: reusing someone else's URI for your entity asserts that you mean the same thing, which is the basis of linked data. Blank nodes are the exception — unnamed entities used when no meaningful identifier exists, such as an address that only makes sense as part of a person. They cannot be referenced from outside the graph, so they are used sparingly. RDF has several equivalent serialisations, including Turtle, RDF/XML, JSON-LD and N-Triples; the triples are the same regardless of the syntax, and JSON-LD has become the common choice for web integration.

Primary sources: <https://www.w3.org/TR/rdf11-concepts/> and <https://en.wikipedia.org/wiki/Resource_Description_Framework>.

## Decision rules

- Model every fact as a subject-predicate-object triple.
- Give entities and predicates stable, dereferenceable URIs.
- Reuse an existing URI only when you genuinely mean the same entity.
- Use blank nodes only for entities with no meaningful independent identity.
- Choose the serialisation for the consumer; the triples are identical across formats.
- Keep predicates consistent; the same relationship always uses the same URI.

## Procedure

1. Identify the entities and assign each a stable URI.
2. Choose or mint URIs for the predicates from the ontology.
3. Write the facts as triples, using literals for plain values.
4. Use blank nodes only where an entity has no independent identity.
5. Select the serialisation that fits the integration target.
6. Validate that URIs resolve and predicates are used consistently.

## Anti-patterns

- Using plain strings as entity identifiers instead of URIs.
- Reusing another source's URI for a different entity.
- Blank nodes for entities that deserve a stable identifier.
- The same relationship written with several different predicates.
- Assuming the serialisation changes the meaning of the triples.

## Done checklist

- [ ] Entities assigned stable URIs.
- [ ] Predicates taken from the ontology consistently.
- [ ] Facts written as triples with literals for plain values.
- [ ] Blank nodes used sparingly and only where justified.
- [ ] Serialisation chosen for the consumer.
- [ ] URIs and predicate usage validated.

## Sources

- RDF 1.1 concepts: <https://www.w3.org/TR/rdf11-concepts/>
- Resource Description Framework: <https://en.wikipedia.org/wiki/Resource_Description_Framework>
- Linked data: <https://en.wikipedia.org/wiki/Linked_data>
