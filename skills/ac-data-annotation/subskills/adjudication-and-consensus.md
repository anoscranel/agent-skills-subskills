---
name: adjudication-and-consensus
domain: software-engineering/adjudication-and-consensus
trigger: "Resolving the items annotators split on."
anti_trigger: "Not for computing agreement, and not for qualifying annotators."
scope: "Resolving the items annotators split on, without laundering noise."
status: seedling
---

# Adjudication and consensus

## Standard

Disagreement is data, not an inconvenience. When annotators split on an item, the split itself tells you something — about the item's ambiguity, the guidelines' gap, or an annotator's drift — and the resolution must preserve that information rather than erase it. Sheng and colleagues show that repeated noisy labels can be combined into a high-quality consensus, but the combination is only as good as the model of each labeler's error; blindly majority-voting a panel that shares a bias just produces a confident wrong answer.

The adjudication ladder is ordered by cost and by what it preserves. Cheap automatic consensus (majority or error-weighted vote) suits clear items where the split is random noise. Expert adjudication suits items where the split is systematic — a genuine boundary case that needs a ruling, which then feeds back into the guidelines. Discussion-to-consensus suits the cases where annotators hold different but defensible readings and the act of reconciling them improves the codebook. The discipline is to route each disagreement to the right rung, record the resolution and its reason, and never silently drop a hard item to make the agreement number look better.

Primary sources: <https://doi.org/10.1145/1401890.1401965> and <https://aclanthology.org/D08-1027/>.

## Decision rules

- Treat every disagreement as a signal; classify it before resolving it.
- Route random-noise splits to error-weighted consensus, not plain majority.
- Route systematic/boundary splits to expert adjudication that produces a ruling.
- Feed adjudication rulings back into the guidelines so the gap closes.
- Record the resolution, the method, and the reason for every adjudicated item.
- Never drop a hard item silently to inflate agreement.

## Procedure

1. Collect the disagreement set from the double-labeled sample.
2. Classify each split: random noise, boundary case, or annotator drift.
3. Apply error-weighted consensus to the random-noise items.
4. Send boundary cases to an expert adjudicator; capture the ruling.
5. Update the codebook with new rulings; re-version it.
6. Log every resolution with method and reason; recompute agreement after.

## Anti-patterns

- Plain majority vote over a panel that shares a bias.
- Dropping hard items to raise the agreement statistic.
- Adjudicating without recording the reason, so the gap reopens.
- Treating all disagreements as noise when some are guideline gaps.
- Letting adjudication rulings die in a spreadsheet instead of the codebook.

## Done checklist

- [ ] Disagreements classified before resolution.
- [ ] Error-weighted consensus for noise splits.
- [ ] Expert adjudication for boundary cases.
- [ ] Rulings fed back into the versioned codebook.
- [ ] Every resolution logged with method and reason.
- [ ] Agreement recomputed after adjudication.

## Sources

- Get Another Label? (Sheng et al.): <https://doi.org/10.1145/1401890.1401965>
- Cheap and Fast – But is it Good? (Snow et al.): <https://aclanthology.org/D08-1027/>
- Inter-Coder Agreement for Computational Linguistics (Artstein & Poesio): <https://doi.org/10.1162/coli.07-034-R2>