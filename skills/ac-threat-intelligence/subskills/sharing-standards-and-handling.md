---
name: sharing-standards-and-handling
domain: security-hardening/sharing-and-handling
trigger: "Sharing intelligence in standard formats under handling rules."
anti_trigger: "Not for collection, and not for internal-only analysis."
scope: "STIX, TAXII and handling labels."
status: seedling
---

# Sharing standards and handling

## Standard

Intelligence is worth more when it can move between organisations and tools without loss. Two OASIS standards do the moving. STIX (Structured Threat Information eXpression) is the data model: a common way to represent indicators, observables, campaigns, threat actors, TTPs and their relationships so a product is machine-readable. TAXII (Trusted Automated eXchange of Intelligence Information) is the transport: the protocol for publishing and subscribing to STIX collections between producers and consumers. Sharing at scale needs both — a format the recipient can parse and a channel that delivers it.

Handling is the other half. The Traffic Light Protocol (TLP) labels how far a piece of intelligence may spread: TLP:RED for the named recipients only, AMBER for the organisation, GREEN for the community, CLEAR for unrestricted. The label is set by the sharer and honoured by the recipient; breaking it burns the source. Legal, contractual and source-sensitivity constraints are recorded with the item, and the most restrictive applicable handling wins when products are combined.

Primary sources: <https://oasis-open.github.io/cti-documentation/> and <https://www.first.org/tlp/>.

## Decision rules

- Represent shareable intelligence in STIX so recipients can consume it.
- Use TAXII to publish and subscribe, not ad-hoc email threads.
- Label every shared item with its TLP; honour received labels strictly.
- Record legal and source constraints; the most restrictive handling wins on merge.
- Share at the highest fidelity the handling label permits.

## Procedure

1. Model the intelligence as STIX objects with their relationships.
2. Publish through a TAXII collection; subscribe to upstream feeds.
3. Assign a TLP label to each item at creation.
4. Record legal and source-handling constraints with the item.
5. Enforce received labels on storage, use and onward sharing.
6. Review handling before any wider dissemination.

## Anti-patterns

- Sharing intelligence as unstructured prose over email.
- Re-distributing TLP:AMBER material outside the organisation.
- Stripping handling labels when re-packaging a feed.
- STIX without the relationships that make it useful.
- Ignoring source constraints because the data is convenient.

## Done checklist

- [ ] Intelligence modelled in STIX with relationships.
- [ ] TAXII publish/subscribe configured.
- [ ] TLP labels assigned and honoured.
- [ ] Legal and source constraints recorded and enforced.
- [ ] Handling reviewed before wider sharing.

Sharing communities multiply the value further: sector information-sharing and analysis centres let peers pool sightings of the same campaign, so one member's detection becomes everyone's early warning. Joining such a community carries obligations as well as benefits — contribute what your handling rules allow, and respect the labels on what you receive.

## Sources

- STIX and TAXII documentation: <https://oasis-open.github.io/cti-documentation/>
- Traffic Light Protocol: <https://www.first.org/tlp/>
- Threat intelligence sharing: <https://en.wikipedia.org/wiki/Cyber_threat_intelligence>
