---
name: linked-data-and-integration
domain: software-engineering/linked-data-and-integration
trigger: "Integrating sources and resolving records about the same entity."
anti_trigger: "Not for the ontology design, and not for a single clean source."
scope: "Linked data, schema.org, and entity resolution."
status: seedling
---

# Linked data and integration

## Standard

Linked data is the practice of publishing and connecting structured data on the web so that different datasets can refer to the same things. Its principles are to name things with URIs, make those URIs resolvable to useful information, and include links to other datasets' URIs so more can be discovered. schema.org provides a widely used shared vocabulary for common entities such as people, organisations, products and events, so that independent publishers can describe them consistently, and it is the usual starting point before inventing new terms.

The hard problem in integration is entity resolution: deciding which records in different sources refer to the same real-world entity. Two records may describe the same person with different spellings, missing fields, or conflicting details, and the graph only integrates correctly when they are linked as one. Resolution combines exact identifiers where they exist, such as a shared ISBN, with matching on attributes where they do not, and it produces an explicit link, commonly an owl:sameAs assertion, rather than silently merging the records. That link must be justified, because a false sameAs merges two distinct entities and corrupts every query that follows.

Primary sources: <https://en.wikipedia.org/wiki/Linked_data> and <https://schema.org/docs/gs.html>.

## Decision rules

- Name entities with resolvable URIs and link to other datasets' URIs.
- Reuse schema.org terms for common entities before minting new ones.
- Resolve entities on exact identifiers first, then on attribute matching.
- Assert identity links explicitly; never merge records silently.
- Justify every sameAs link; a false link corrupts downstream queries.
- Record the evidence and confidence for each resolution decision.

## Procedure

1. Assign resolvable URIs to your entities and publish their descriptions.
2. Map your terms to schema.org or another shared vocabulary where possible.
3. Identify candidate matching records across the sources.
4. Match on exact identifiers first, then on weighted attribute evidence.
5. Assert sameAs or a weaker link for confirmed matches, with justification.
6. Review a sample of links for false merges and record the confidence.

## Anti-patterns

- Minting new terms where schema.org already fits.
- Merging records on a name match alone.
- Asserting sameAs for things that are merely similar.
- Silent merges with no recorded justification.
- Assuming integration is complete without checking for false links.

## Done checklist

- [ ] Entities given resolvable URIs.
- [ ] Terms mapped to a shared vocabulary.
- [ ] Candidate matches identified across sources.
- [ ] Exact-identifier matches done before attribute matching.
- [ ] Identity links asserted with justification.
- [ ] Links sampled for false merges and confidence recorded.

## Sources

- Linked data: <https://en.wikipedia.org/wiki/Linked_data>
- schema.org getting started: <https://schema.org/docs/gs.html>
- Web Ontology Language (sameAs): <https://en.wikipedia.org/wiki/Web_Ontology_Language>
