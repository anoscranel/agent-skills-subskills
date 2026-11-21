---
name: ac-knowledge-graph
description: 'Representing knowledge as a graph of entities and relationships so it can be integrated, queried and reasoned over: knowledge-graph fundamentals and when a graph beats a table, ontology and schema design, RDF triples and identifiers, OWL semantics and the open-world assumption, SPARQL querying, linked data and entity integration, and the knowledge-graph record. It covers the semantic-modeling craft; it never treats a graph as automatically better than a relational schema and never promises inference it has not tested. Use when asking "knowledge graph", "ontology design", "RDF triples", "SPARQL query", "linked data", "OWL", "semantic web", "entity resolution", "schema.org", "build a knowledge graph". Not for analytical star schemas and warehouses (ac-analytical-data-modeling), not for operational database schema and migrations (ac-database-changes), not for content addressing and hashing (ac-content-addressed-storage), not for recommendation ranking (ac-recommendation-systems).'
license: MIT
metadata:
  domain: software-engineering
status: seedling
---

# Knowledge graph

## Overview

A knowledge graph represents a domain as nodes and typed relationships rather than as rows and tables. Its strength is not storage but meaning: entities carry stable identifiers, relationships carry types, and an ontology states what those types mean, so data from different sources can be joined, queried and reasoned over without a bespoke mapping for every pair. Where a relational schema answers a fixed set of questions cheaply, a knowledge graph earns its cost when the questions are open-ended, the data is heterogeneous, and the connections between things matter as much as the things.

This skill covers the semantic-modeling craft, not the neighbouring ones: ac-analytical-data-modeling owns the analytical star schema, ac-database-changes owns the operational schema and its migrations, ac-content-addressed-storage owns content hashing and addressing, and ac-recommendation-systems owns ranking. The discipline throughout is that a graph is a deliberate choice with real costs — modeling effort, query complexity, and a learning curve — not an upgrade you apply to every dataset.

Primary sources: <https://www.w3.org/TR/rdf11-concepts/> and <https://en.wikipedia.org/wiki/Knowledge_graph>.

## When to use

- Integrating heterogeneous data about the same entities from several sources.
- Designing an ontology or a shared vocabulary for a domain.
- Querying across relationships with SPARQL.
- Deciding whether a knowledge graph is justified over a relational schema.
- Resolving and linking records that refer to the same real-world entity.

## When NOT to use

- For analytical fact-and-dimension modeling and warehouses (use ac-analytical-data-modeling).
- For operational database schema and zero-downtime migrations (use ac-database-changes).
- For content addressing and content hashing (use ac-content-addressed-storage).
- For recommendation ranking and candidate generation (use ac-recommendation-systems).

## Subskill Index

| Leaf | Domain segment | Scope (one line) |
|---|---|---|
| `subskills/knowledge-graph-fundamentals.md` | `software-engineering/knowledge-graph-fundamentals` | Entities, relationships, and when a graph beats a table. |
| `subskills/modeling-and-ontologies.md` | `software-engineering/modeling-and-ontologies` | Classes, properties, and ontology design. |
| `subskills/rdf-and-identifiers.md` | `software-engineering/rdf-and-identifiers` | Triples, URIs, blank nodes, and RDF serialisations. |
| `subskills/owl-and-semantics.md` | `software-engineering/owl-and-semantics` | OWL, restrictions, reasoning, and the open-world assumption. |
| `subskills/sparql-and-query.md` | `software-engineering/sparql-and-query` | Querying a graph with SPARQL. |
| `subskills/linked-data-and-integration.md` | `software-engineering/linked-data-and-integration` | Linked data, schema.org, and entity resolution. |
| `subskills/knowledge-graph-record.md` | `software-engineering/knowledge-graph-record` | Provenance, versioning, quality, and the written record. |

## Status and honest limits

A knowledge graph is not automatically the right model: for a stable, well-understood domain with a fixed query set, a relational schema is usually simpler and faster. Ontologies require real modeling effort and ongoing maintenance, and a poorly designed ontology is harder to change than a poorly designed table. Reasoning is only as sound as the ontology and data it runs over, and the open-world assumption means absence of a statement is not proof of its falsity — a trap for anyone used to closed-world databases. Nothing here promises inference quality; the graph must be validated against the questions it was built to answer.
