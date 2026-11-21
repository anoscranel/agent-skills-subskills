---
name: annotation-guidelines
domain: software-engineering/annotation-guidelines
trigger: "Writing the codebook and label taxonomy before anyone labels."
anti_trigger: "Not for training-pair curation, and not for scoring a finished model."
scope: "The codebook and label taxonomy that make a label mean one thing."
status: seedling
---

# Annotation guidelines

## Standard

The guidelines are the measuring instrument. Every label in the set is an application of them, so a vague guideline does not produce a few bad labels — it produces a systematically noisy dataset whose noise no downstream model can undo. The codebook must make each label mean one thing: a definition, the decision rule for assigning it, positive and negative examples, and the boundary cases where two labels compete. Greene's shared-rubric work frames guidelines as the contract that lets a buyer compare annotation providers at all; without an explicit rubric, competition collapses to price and quality becomes invisible.

The taxonomy is part of the instrument, not an afterthought. Decide up front whether labels are mutually exclusive or multi-label, how granular they are, whether they form a hierarchy, and what the "other/unclear" bucket is for. A taxonomy that forces every item into a bad fit yields consistent garbage — high agreement on a wrong reading. The guidelines must also state what annotators do when the item is ambiguous, out of scope, or unlabelable, because that decision is where most silent disagreement is born.

Primary sources: <https://arxiv.org/abs/2112.03867> and <https://doi.org/10.1162/coli.07-034-R2>.

## Decision rules

- Write the codebook before the first label, not alongside it.
- Give every label a definition, a decision rule, and worked positive/negative examples.
- Name the boundary cases explicitly and rule on them in advance.
- Fix the taxonomy shape first: exclusive vs multi-label, granularity, hierarchy, "other" bucket.
- State the ambiguous/out-of-scope/unlabelable procedure; do not leave it to each annotator.
- Version the guidelines; every label records the version it was produced under.

## Procedure

1. Draft the task definition and the label set with the domain owner.
2. Write a definition, decision rule, and examples for each label.
3. Enumerate boundary cases and rule on each; record the rulings.
4. Pilot the codebook on a small sample with two or more annotators.
5. Read the pilot disagreements; revise the guidelines, not the annotators.
6. Freeze and version the codebook; re-pilot after any material change.

## Anti-patterns

- Writing guidelines after labeling has started, then retrofitting them to the labels.
- Definitions without examples, or examples without a decision rule.
- A taxonomy with no "other" bucket, forcing bad fits.
- Letting each annotator resolve ambiguity privately.
- Treating a guideline revision as cosmetic and not re-versioning.

## Done checklist

- [ ] Codebook written before the first label.
- [ ] Each label has definition, rule, and examples.
- [ ] Boundary cases ruled on in advance.
- [ ] Taxonomy shape fixed and documented.
- [ ] Ambiguity procedure stated.
- [ ] Guidelines versioned; pilot disagreements fed back into them.

## Sources

- Towards a Shared Rubric for Dataset Annotation (Greene): <https://arxiv.org/abs/2112.03867>
- Inter-Coder Agreement for Computational Linguistics (Artstein & Poesio): <https://doi.org/10.1162/coli.07-034-R2>
- Data Cascades in High-Stakes AI: <https://doi.org/10.1145/3411764.3445518>