---
name: annotation-record
domain: software-engineering/annotation-record
trigger: "Writing the record that makes a labeled set trustworthy."
anti_trigger: "Not for the labeling itself, and not for a model card."
scope: "The written record that makes a labeled set trustworthy."
status: seedling
---

# Annotation record

## Standard

A labeled dataset without a record is a claim without evidence. The annotation record is what lets a downstream user — a fine-tuning run, an evaluation, a retrieval ground truth — decide whether the labels can be trusted for their purpose. Greene's shared-rubric argument is exactly this: without an explicit, comparable account of how a dataset was produced, buyers cannot distinguish quality from price, and the market races to the bottom. The record is the artifact that makes quality visible and comparable.

The record must carry the instrument and its evidence: the codebook version every label was produced under, the annotator roster with qualification scores, the agreement coefficients with their sample and expected agreement, the adjudication log with rulings, the quality-control catches and actions, the sampling plan, and the known limitations. The Data Cascades study is the cautionary anchor — upstream data work that is undocumented becomes a downstream cascade nobody can trace. The record's duty is to name what was NOT covered and where the labels are weak, because a record that only reports strengths cannot support a trust decision. A dataset whose record cannot say how it was made and where it fails is not ready to be built on.

Primary sources: <https://doi.org/10.1145/3411764.3445518> and <https://arxiv.org/abs/2112.03867>.

## Decision rules

- Record the codebook version attached to every label batch.
- Carry the annotator roster with qualification and quality scores.
- Report agreement coefficients with sample and expected agreement.
- Include the adjudication log, quality-control catches, and sampling plan.
- Name the known limitations and the surfaces not covered.
- Version the record with the dataset; a label change updates the record.

## Procedure

1. Capture the codebook version and taxonomy for the release.
2. Assemble the annotator roster with qualification and quality scores.
3. Attach agreement results, adjudication log, and QC catch/action log.
4. Record the sampling plan and the label budget actually spent.
5. Write the limitations section: what is weak, what was not covered.
6. Version and ship the record beside the dataset; link them permanently.

## Anti-patterns

- Shipping a dataset with no record of how it was labeled.
- Reporting only strengths and omitting known weaknesses.
- A record that does not name the codebook version.
- Letting the record drift out of sync with the labels.
- Treating the record as paperwork instead of the trust evidence.

## Done checklist

- [ ] Codebook version recorded per batch.
- [ ] Annotator roster with scores included.
- [ ] Agreement, adjudication, and QC logs attached.
- [ ] Sampling plan and budget recorded.
- [ ] Limitations and uncovered surfaces named.
- [ ] Record versioned and linked to the dataset.

## Sources

- Data Cascades in High-Stakes AI: <https://doi.org/10.1145/3411764.3445518>
- Towards a Shared Rubric for Dataset Annotation (Greene): <https://arxiv.org/abs/2112.03867>
- Inter-Coder Agreement for Computational Linguistics (Artstein & Poesio): <https://doi.org/10.1162/coli.07-034-R2>