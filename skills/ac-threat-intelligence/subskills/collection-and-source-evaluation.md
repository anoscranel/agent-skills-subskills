---
name: collection-and-source-evaluation
domain: security-hardening/collection-and-sources
trigger: "Choosing collection channels and judging source reliability."
anti_trigger: "Not for analysis frameworks, and not for sharing formats."
scope: "Collection channels and source reliability."
status: seedling
---

# Collection and source evaluation

## Standard

Collection channels are chosen against the requirements: open-source intelligence (public reports, forums, paste sites, social media), commercial and community feeds, technical telemetry (DNS, passive DNS, netflow, honeypots), closed or dark-web sources, and internal incident data. Each channel answers some PIRs and not others, and each carries its own bias — a vendor feed reflects what that vendor's sensors see, which is not the whole threat.

Source evaluation is the discipline that keeps collection honest. The Admiralty or NATO code rates two dimensions separately: the reliability of the source (track record of being right) and the credibility of the information (is it corroborated, plausible, current). A reliable source can pass a single dubious report, and an unknown source can pass a true one; the two ratings must not be merged into one impression. Every collected item carries its rating so the analyst downstream knows how much weight to give it.

Primary sources: <https://en.wikipedia.org/wiki/Admiralty_code> and <https://en.wikipedia.org/wiki/Cyber_threat_intelligence>.

## Decision rules

- Channels are selected per PIR, with the channel's known bias recorded.
- Rate source reliability and information credibility separately, on a stated scale.
- Corroborate load-bearing items across independent channels before weighting them.
- Record collection legal and handling constraints at the point of collection.
- Prefer primary technical evidence over second-hand reporting where both exist.

## Procedure

1. List candidate channels against each PIR.
2. Record each channel's coverage, bias, and access constraints.
3. Rate each source's reliability from its track record.
4. Rate each item's credibility: corroboration, plausibility, recency.
5. Attach both ratings to the collected item.
6. Review channel value periodically; drop channels that answer nothing.

## Anti-patterns

- Treating a paid feed as authoritative by virtue of being paid.
- Merging source reliability and information credibility into one judgment.
- Acting on a single uncorroborated report for a consequential assessment.
- Dark-web collection without legal and handling review.
- Keeping channels that have never answered a requirement.

## Done checklist

- [ ] Channels mapped to PIRs with bias recorded.
- [ ] Source reliability rated per source.
- [ ] Information credibility rated per item.
- [ ] Load-bearing items corroborated independently.
- [ ] Channel value reviewed and pruned.

Volume is not the goal either. A small set of well-chosen channels that reliably answer the standing requirements beats a wide net that produces mostly noise, because every irrelevant item still costs an analyst's attention. Track the hit rate of each channel against the requirements it was meant to serve and let that evidence, not the fear of missing something, decide what stays.

## Sources

- Admiralty source-rating code: <https://en.wikipedia.org/wiki/Admiralty_code>
- Threat intelligence collection: <https://en.wikipedia.org/wiki/Cyber_threat_intelligence>
- Handling labels for collected material: <https://www.first.org/tlp/>
