---
name: attribution-and-campaign-tracking
domain: security-hardening/attribution-and-campaigns
trigger: "Clustering activity into campaigns and assessing attribution."
anti_trigger: "Not for indicator handling, and not for legal attribution decisions."
scope: "Actor and campaign tracking with confidence."
status: seedling
---

# Attribution and campaign tracking

## Standard

Campaign tracking clusters related intrusions into activity threads that share adversary, tooling, infrastructure or victimology, so the defender can reason about a persistent opponent rather than isolated events. Attribution is the harder claim: naming who is behind the campaign. It rests on converging lines of evidence — infrastructure reuse, tooling and code similarity, TTP overlap, targeting pattern, timing and language artefacts — each of which can be faked or shared. Because these signals are circumstantial, honest attribution is always an assessment with a confidence level, never a certainty.

The craft is to separate observation from inference and to carry alternatives. A strong product states what is observed, what is inferred, the confidence in each inference, the plausible alternative explanations, and the evidence that would change the assessment. Naming conventions help tracking (vendor families, numbered clusters), but a vendor's actor name is a hypothesis about clustering, not a fact about identity, and different vendors' names for similar activity are not automatically the same actor.

Primary sources: <https://en.wikipedia.org/wiki/Cyber_threat_intelligence> and <https://www.activeresponse.org/wp-content/uploads/2013/07/diamond.pdf>.

## Decision rules

- Cluster on converging independent evidence, not on one shared artefact.
- State attribution as an assessment with an explicit confidence level.
- Carry plausible alternative explanations and disconfirming evidence.
- Treat vendor actor names as clustering hypotheses, not identities.
- Re-assess attribution when new evidence arrives; record the change.

## Procedure

1. Cluster events into candidate campaigns by shared features.
2. List the independent lines of evidence for the cluster.
3. Assess attribution; state confidence and alternatives.
4. Record what would strengthen or overturn the assessment.
5. Track the campaign over time; update on new evidence.
6. Keep observed facts separate from inferred identity throughout.

## Anti-patterns

- Asserting an actor name as established fact.
- Clustering on a single shared IP or hash.
- Suppressing alternative explanations that weaken the narrative.
- Treating two vendors' names as the same actor without evidence.
- Never revisiting an attribution once published.

## Done checklist

- [ ] Campaigns clustered on converging evidence.
- [ ] Attribution stated with confidence and alternatives.
- [ ] Disconfirming evidence and overturn conditions recorded.
- [ ] Vendor names treated as hypotheses.
- [ ] Attribution re-assessed on new evidence.

Confidence language should be consistent across products so that consumers can compare assessments: a shared scale for low, moderate and high confidence, each tied to the quantity and independence of the supporting evidence. Without that consistency, one analyst's 'likely' and another's 'probable' quietly mean different things, and the consumer cannot tell how much weight to place on either.

## Sources

- Threat intelligence and attribution: <https://en.wikipedia.org/wiki/Cyber_threat_intelligence>
- Diamond Model for clustering: <https://www.activeresponse.org/wp-content/uploads/2013/07/diamond.pdf>
- Source and confidence rating: <https://en.wikipedia.org/wiki/Admiralty_code>
