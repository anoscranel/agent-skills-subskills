---
name: sparql-and-query
domain: software-engineering/sparql-and-query
trigger: "Querying a knowledge graph with SPARQL."
anti_trigger: "Not for the ontology design, and not for relational SQL tuning."
scope: "Querying a graph with SPARQL."
status: seedling
---

# SPARQL and query

## Standard

SPARQL is the query language for RDF graphs. Its core is the graph pattern: a set of triple patterns with variables that are matched against the graph's triples. A query asks for the bindings of those variables that make the pattern true. The most common form is SELECT, which returns a table of bindings; CONSTRUCT returns a new graph built from the matches; ASK returns a yes-or-no answer; DESCRIBE returns the triples that describe a resource. Matching is by graph structure, so a query traverses relationships directly rather than by joining tables.

Practical querying rests on a few constructs. OPTIONAL retrieves a pattern only where it exists, so an optional property does not eliminate an otherwise matching row. FILTER restricts results by a condition on the bindings. Property paths traverse a chain of relationships, including an arbitrary-length path, without naming every intermediate step. Aggregation with GROUP BY and HAVING summarises across matches. And because SPARQL operates on an open-world graph, a query returns only what the graph states or infers, not everything that might be true; a query that returns nothing may mean the data is missing rather than that the answer is no. Federated queries reach across endpoints with SERVICE, at the cost of depending on remote availability.

Primary sources: <https://www.w3.org/TR/sparql11-query/> and <https://en.wikipedia.org/wiki/SPARQL>.

## Decision rules

- Choose the query form for the result needed: SELECT, CONSTRUCT, ASK or DESCRIBE.
- Use OPTIONAL for properties that may be absent, so they do not drop matching rows.
- Use property paths for chains of relationships instead of long explicit joins.
- Filter with FILTER and aggregate with GROUP BY and HAVING where summarising.
- Treat an empty result as possibly missing data, not necessarily a negative answer.
- Federate with SERVICE only when the remote dependency is acceptable.

## Procedure

1. Write the question as a graph pattern with variables.
2. Choose the query form that produces the required result.
3. Mark optional patterns OPTIONAL and add the necessary FILTER conditions.
4. Use property paths for relationship chains and aggregation for summaries.
5. Run the query and check the results against known examples.
6. Record whether an empty result means absence of data or a negative answer.

## Anti-patterns

- Forgetting OPTIONAL and silently losing rows with missing properties.
- Writing long explicit joins where a property path would do.
- Reading an empty result as a definitive no.
- Aggregating without a correct GROUP BY.
- Federating across endpoints without accounting for their availability.

## Done checklist

- [ ] Question written as a graph pattern.
- [ ] Correct query form chosen.
- [ ] OPTIONAL and FILTER applied correctly.
- [ ] Property paths and aggregation used where appropriate.
- [ ] Results checked against known examples.
- [ ] Empty-result interpretation recorded.

## Sources

- SPARQL 1.1 query language: <https://www.w3.org/TR/sparql11-query/>
- SPARQL: <https://en.wikipedia.org/wiki/SPARQL>
- RDF 1.1 concepts: <https://www.w3.org/TR/rdf11-concepts/>
