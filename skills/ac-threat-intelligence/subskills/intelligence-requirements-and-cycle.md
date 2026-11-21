---
name: intelligence-requirements-and-cycle
domain: security-hardening/intelligence-requirements
trigger: "Setting intelligence priorities and running the cycle."
anti_trigger: "Not for indicator handling, and not for SOC operations."
scope: "Priority intelligence requirements and the intelligence cycle."
status: seedling
---

# Intelligence requirements and cycle

## Standard

Intelligence work starts from a decision, not from data. A priority intelligence requirement (PIR) is a question a named decision-maker needs answered to make a specific decision: which actors target our sector, what would an intrusion on this asset look like, which of our exposures is being exploited now. The PIR states the decision it informs and the consumer; without that, collection drifts to whatever is easiest to fetch.

The intelligence cycle is the loop that turns the requirement into a product: direction (set the PIRs), collection (gather against them), processing (normalise and de-duplicate), analysis (produce the assessment), dissemination (deliver to the consumer in a usable form), and feedback (did it answer the question and change the decision). The feedback step is the one most often skipped, and its absence is why intelligence functions produce reports nobody reads.

Primary sources: <https://en.wikipedia.org/wiki/Cyber_threat_intelligence> and <https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html>.

## Decision rules

- Every PIR names the decision it informs and the decision-maker.
- Collection is driven by the PIRs, not by what is cheap to collect.
- Dissemination format is chosen for the consumer's workflow, not the analyst's.
- The cycle is closed: feedback on whether the product changed the decision is captured.
- Fewer answered PIRs beat many unanswered ones.

## Procedure

1. Elicit PIRs from decision-makers; record the decision behind each.
2. Rank by consequence of the decision and feasibility of answering.
3. Map each PIR to the collection channels that could answer it.
4. Process and analyse; produce the assessment with confidence stated.
5. Disseminate in the consumer's format and channel.
6. Capture feedback; retire or re-scope PIRs that no longer inform decisions.

## Anti-patterns

- Collecting everything and calling it intelligence.
- A PIR with no decision or consumer attached.
- Reports produced on a schedule regardless of whether anyone acts.
- No feedback loop, so stale requirements persist forever.
- Measuring output in report count.

## Done checklist

- [ ] PIRs elicited, each with a decision and consumer.
- [ ] PIRs ranked and mapped to collection channels.
- [ ] Cycle run through dissemination in the consumer's format.
- [ ] Feedback captured on decision impact.
- [ ] Stale PIRs retired.

The cycle is also iterative at the level of the individual requirement: a first-pass assessment usually exposes what is not yet known, sharpening the question into a more answerable form. Treat that refinement as normal work, not as failure, and re-issue the sharpened requirement back into collection rather than forcing a weak answer to the original vague question.

## Sources

- Threat intelligence overview: <https://en.wikipedia.org/wiki/Cyber_threat_intelligence>
- The kill chain as an analysis frame: <https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html>
- ATT&CK knowledge base: <https://attack.mitre.org/>
