---
name: knowledge-graph-record
domain: software-engineering/knowledge-graph-record
trigger: "Recording provenance, versioning and quality for a knowledge graph."
anti_trigger: "Not for the ontology design, and not for the SPARQL queries."
scope: "Provenance, versioning, quality, and the written record."
status: seedling
---

# Knowledge graph record

## Standard

A knowledge graph is only as trustworthy as its record. The record answers where each fact came from, how the graph has changed, and how good the data is. Provenance attaches a source to a statement or a set of statements, so a claim can be traced back to the dataset, document or feed it came from. Versioning tracks the ontology and the data over time, so a change in meaning or content is visible and, where necessary, reversible. Quality assessment checks the graph against the questions it was built to answer and against basic measures of completeness, consistency and accuracy.

Provenance is the piece most often neglected, and it is the one that matters most when two sources disagree. Because RDF triples are context-free, a statement's origin is not carried in the triple itself; it must be recorded, for example by grouping statements into named graphs per source or by annotating the statement. Without it, a false or outdated fact has no trail back to its cause. The record also captures the ontology's definitions, the vocabularies reused, the resolution links and their confidence, and the known gaps. A graph that cannot say what it does not cover will be trusted for more than it is worth.

Primary sources: <https://www.w3.org/TR/rdf11-concepts/> and <https://en.wikipedia.org/wiki/Knowledge_graph>.

## Decision rules

- Record the source of every statement or statement group.
- Use named graphs or statement annotation to carry provenance.
- Version both the ontology and the data, with changes visible.
- Assess quality against the original questions, not against graph size.
- Check completeness, consistency and accuracy with explicit measures.
- Record known gaps and the graph's coverage limits.

## Procedure

1. Group statements by source into named graphs or annotate them.
2. Record the ontology's definitions and the vocabularies reused.
3. Version the ontology and the data with a change history.
4. Measure completeness and consistency against the intended coverage.
5. Validate the graph against the original competency questions.
6. Write the coverage limits and known gaps into the record.

## Anti-patterns

- Loading data with no record of where it came from.
- Versioning the data but not the ontology, or vice versa.
- Judging quality by the number of triples.
- Skipping the completeness and consistency checks.
- Omitting the coverage limits from the record.

## Done checklist

- [ ] Provenance recorded per statement or group.
- [ ] Ontology definitions and reused vocabularies documented.
- [ ] Ontology and data versioned with history.
- [ ] Completeness and consistency measured.
- [ ] Graph validated against the original questions.
- [ ] Coverage limits and gaps recorded.

## Sources

- RDF 1.1 concepts (named graphs): <https://www.w3.org/TR/rdf11-concepts/>
- Knowledge graph: <https://en.wikipedia.org/wiki/Knowledge_graph>
- Semantic web: <https://en.wikipedia.org/wiki/Semantic_web>
