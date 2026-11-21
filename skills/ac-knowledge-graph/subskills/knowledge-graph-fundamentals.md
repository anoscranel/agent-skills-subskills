---
name: knowledge-graph-fundamentals
domain: software-engineering/knowledge-graph-fundamentals
trigger: "Deciding whether a knowledge graph is the right model."
anti_trigger: "Not for analytical star schemas, and not for the ontology's class design."
scope: "Entities, relationships, and when a graph beats a table."
status: seedling
---

# Knowledge graph fundamentals

## Standard

A knowledge graph models a domain as a set of entities and the typed relationships between them. An entity is anything with an identity: a person, a product, a place, a concept. A relationship connects two entities with a named type: worksFor, locatedIn, partOf. The result is a graph you can traverse and reason over, rather than a set of tables you must join by hand for every new question.

The decision to build one is a judgment about the questions, not the data volume. A knowledge graph earns its cost when the questions are open-ended and centre on connections, when the data arrives from many heterogeneous sources that must be integrated, and when the domain's meaning must be shared across teams or systems. It is the wrong choice when the domain is stable and the queries are fixed and well-served by a relational schema, when the data is a single clean source, or when the team lacks the modeling effort a graph demands. The graph is a tool for meaning and integration, not a general improvement on tables.

Primary sources: <https://en.wikipedia.org/wiki/Knowledge_graph> and <https://www.w3.org/TR/rdf11-concepts/>.

## Decision rules

- Choose a knowledge graph for connection-centric, open-ended questions over heterogeneous sources.
- Prefer a relational schema for a stable domain with a fixed, known query set.
- Identify the questions the graph must answer before modeling anything.
- Treat integration cost and ontology maintenance as real, budgeted costs.
- Do not build a graph to look modern; build it when a table cannot answer the question.
- Validate the graph against the questions it was built for, not against its size.

## Procedure

1. Write down the questions the system must answer, in the users' language.
2. Check whether a relational schema answers them adequately.
3. Identify the entities and the relationships the questions traverse.
4. Estimate the integration effort across the data sources.
5. Decide graph versus table against the questions and the budget.
6. Record the decision and the questions that justify it.

## Anti-patterns

- Building a knowledge graph because it is fashionable.
- Modeling before writing down the questions to be answered.
- Underestimating ontology design and maintenance effort.
- Treating graph size as a measure of success.
- Assuming a graph is always more flexible than a table.

## Done checklist

- [ ] Questions written before modeling.
- [ ] Relational alternative assessed honestly.
- [ ] Entities and relationships identified from the questions.
- [ ] Integration effort estimated.
- [ ] Graph-versus-table decision recorded with reasons.
- [ ] Validation plan tied to the original questions.

## Sources

- Knowledge graph: <https://en.wikipedia.org/wiki/Knowledge_graph>
- RDF 1.1 concepts: <https://www.w3.org/TR/rdf11-concepts/>
- Semantic web: <https://en.wikipedia.org/wiki/Semantic_web>
