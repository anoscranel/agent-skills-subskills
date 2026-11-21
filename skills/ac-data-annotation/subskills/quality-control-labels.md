---
name: quality-control-labels
domain: software-engineering/quality-control-labels
trigger: "Catching label errors and drift before they poison the set."
anti_trigger: "Not for the agreement statistic, and not for model evaluation."
scope: "Golden labels, attention checks, and audits that catch drift."
status: seedling
---

# Quality-control labels

## Standard

Quality control is the continuous measurement that keeps a labeling process honest after the qualification gate. The core device is the golden item: an item whose correct label is already known, slipped into the production stream so that an annotator's accuracy can be measured on real work, not just on a qualification batch. Snow and colleagues' non-expert annotation result depends on exactly this kind of oversight — cheap labelers are usable because their output is checked, not because it is assumed good. The Data Cascades study shows what happens when this checking is skipped: small upstream data errors compound silently into downstream failures that are expensive to trace back.

Golden items must be designed, not convenient. A golden set drawn only from easy, clear cases measures nothing about the hard boundary cases where errors actually live, so it must span the taxonomy and include the known-hard items. Attention checks catch the disengaged or automated labeler; golden items catch the miscalibrated one. Both feed a per-annotator quality score that drives action — retrain, reweight, or remove — and the audit trail records what was caught and what was done. The honest limit: golden items only catch the errors they were designed to catch, so a golden set that mirrors the annotators' shared blind spot will pass a biased panel.

Primary sources: <https://aclanthology.org/D08-1027/> and <https://doi.org/10.1145/3411764.3445518>.

## Decision rules

- Embed golden items in the production stream, not only in qualification.
- Build the golden set to span the taxonomy and include known-hard cases.
- Use attention checks for disengagement and golden items for miscalibration.
- Maintain a per-annotator quality score that triggers a defined action.
- Audit a sample of accepted labels independently, not just the golden hits.
- Record what was caught and what action followed; do not silently discard.

## Procedure

1. Curate a golden set spanning labels and difficulty, with verified answers.
2. Insert golden items and attention checks at a stated rate into the stream.
3. Score each annotator against golden items continuously.
4. Apply the pre-declared action when a score falls below its bar.
5. Independently audit a sample of accepted (non-golden) labels.
6. Log catches, actions, and audit findings; refresh the golden set over time.

## Anti-patterns

- A golden set of only easy items that measures nothing about hard cases.
- Assuming qualified annotators need no ongoing checking.
- Catching errors but taking no action, so the noise stays in the set.
- Auditing only golden hits and never the accepted labels.
- A golden set that shares the panel's blind spot, passing bias.

## Done checklist

- [ ] Golden items embedded in production at a stated rate.
- [ ] Golden set spans taxonomy and hard cases.
- [ ] Attention checks and golden items both used.
- [ ] Per-annotator quality score with a defined action.
- [ ] Independent audit of accepted labels.
- [ ] Catches and actions logged; golden set refreshed.

## Sources

- Cheap and Fast – But is it Good? (Snow et al.): <https://aclanthology.org/D08-1027/>
- Data Cascades in High-Stakes AI: <https://doi.org/10.1145/3411764.3445518>
- Get Another Label? (Sheng et al.): <https://doi.org/10.1145/1401890.1401965>