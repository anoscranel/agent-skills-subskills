---
name: owl-and-semantics
domain: software-engineering/owl-and-semantics
trigger: "Adding formal semantics and reasoning to an ontology."
anti_trigger: "Not for the RDF triples themselves, and not for SPARQL querying."
scope: "OWL, restrictions, reasoning, and the open-world assumption."
status: seedling
---

# OWL and semantics

## Standard

The Web Ontology Language, OWL, adds formal semantics to an ontology so that a reasoner can draw conclusions that are not explicitly stated. It lets you define classes precisely, state property characteristics such as transitive or inverse, and express restrictions such as every instance of a class having a property of a particular type. A reasoner then infers new facts: if worksFor is transitive in a chain, or if an instance satisfies a class definition, the reasoner concludes the implied membership or relationship.

Two semantic principles trip up everyone coming from databases. The open-world assumption means that the absence of a statement is not evidence that the statement is false; a missing worksFor triple does not mean the person has no employer, only that the graph does not say. And there is no unique-name assumption by default: two different URIs may denote the same real-world entity until you assert or infer otherwise. These are deliberate choices that support open, distributed data, but they mean a reasoner will not flag a missing fact as an error the way a closed database constraint would. Validation of completeness therefore needs explicit shapes or queries, not the reasoner alone.

Primary sources: <https://www.w3.org/TR/owl2-overview/> and <https://en.wikipedia.org/wiki/Web_Ontology_Language>.

## Decision rules

- Use OWL when you need inference beyond the explicitly stated triples.
- Define classes and property characteristics precisely enough for the intended reasoning.
- Remember the open-world assumption: absence of a fact is not its negation.
- Do not assume distinct URIs denote distinct entities without an explicit statement.
- Validate completeness with explicit shapes or queries, not with the reasoner.
- Keep the ontology's expressivity within what the reasoner can handle tractably.

## Procedure

1. Identify the inferences the application actually needs.
2. Define classes and property characteristics to support those inferences.
3. Add restrictions only where they capture genuine domain rules.
4. Run a reasoner and inspect the inferred facts for surprises.
5. Write explicit completeness checks where the open world hides missing data.
6. Record the semantics used and the inferences relied upon.

## Anti-patterns

- Treating a missing triple as proof that a fact is false.
- Assuming two URIs are different entities by default.
- Expecting the reasoner to enforce completeness like a database constraint.
- Over-expressive modeling that makes reasoning intractable.
- Adding restrictions the domain does not actually require.

## Done checklist

- [ ] Required inferences identified.
- [ ] Classes and property characteristics defined for them.
- [ ] Open-world and no-unique-name assumptions respected.
- [ ] Reasoner output inspected for surprising inferences.
- [ ] Completeness checked with explicit shapes or queries.
- [ ] Semantics and relied-upon inferences recorded.

## Sources

- OWL 2 overview: <https://www.w3.org/TR/owl2-overview/>
- Web Ontology Language: <https://en.wikipedia.org/wiki/Web_Ontology_Language>
- Semantic web: <https://en.wikipedia.org/wiki/Semantic_web>
