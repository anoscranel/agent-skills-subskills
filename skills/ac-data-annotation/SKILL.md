---
name: ac-data-annotation
description: 'Producing high-quality labeled data for ML and LLM systems: annotation guidelines and label taxonomies, annotator selection and calibration, inter-annotator agreement and what low agreement means, adjudication and consensus, golden-label quality control, active-learning sampling for label budgets, and the written annotation record. It owns the craft of turning raw items into trustworthy labels; it never trains a model and never evaluates one. Use when asking "how do I label this dataset", "annotation guidelines", "inter-annotator agreement", "Cohen''s kappa", "Krippendorff''s alpha", "annotator calibration", "adjudicate disagreements", "golden labels", "active learning for labeling", "label quality audit". Not for curating instruction/preference training pairs (ac-model-fine-tuning), not for model evaluation or preference win-rates (ac-model-evaluation), not for literature screening in a systematic review (ac-systematic-review-conduct), not for pipeline data validation (ac-ml-systems-practice).'
license: MIT
metadata:
  domain: software-engineering
status: seedling
---

# Data annotation

## Overview

A label is a measurement, and a dataset of labels is only as good as the instrument that produced it. The instrument is not the model or the schema — it is the whole human process: the guidelines that define what each label means, the annotators who apply them, the agreement that shows they apply them consistently, the adjudication that resolves the cases they split on, and the quality controls that catch drift before it poisons the set. Most failed datasets fail here, quietly, long before any model is trained; the Data Cascades study documents how upstream data work compounds into downstream harm.

This skill owns that process end to end. Its neighbours carve the rest: ac-model-fine-tuning curates the instruction and preference pairs once labels exist; ac-model-evaluation judges models and reads preference win-rates; ac-systematic-review-conduct screens literature for a review; ac-ml-systems-practice validates pipelines. None of them owns the craft of producing the labels themselves. Annotation sits before all of them: raw items in, trustworthy labels out, with the evidence that they can be trusted.

Primary sources: <https://arxiv.org/abs/2112.03867> and <https://doi.org/10.1145/3411764.3445518>.

## When to use

- Before labeling a dataset for training, evaluation, or retrieval ground truth.
- When labels disagree and you must decide whether the task, the guidelines, or the annotators are at fault.
- When a label budget is fixed and you must choose which items to label.
- When you must prove a labeled set is trustworthy before anyone builds on it.

## When NOT to use

- For curating instruction/preference training pairs (use ac-model-fine-tuning).
- For evaluating models or reading preference win-rates (use ac-model-evaluation).
- For screening literature in a systematic review (use ac-systematic-review-conduct).
- For pipeline data validation and leakage checks (use ac-ml-systems-practice).

## Subskill Index

| Leaf | Domain segment | Scope (one line) |
|---|---|---|
| `subskills/annotation-guidelines.md` | `software-engineering/annotation-guidelines` | The codebook and label taxonomy that make a label mean one thing. |
| `subskills/annotator-calibration.md` | `software-engineering/annotator-calibration` | Selecting, training, and qualifying the people who apply the labels. |
| `subskills/inter-annotator-agreement.md` | `software-engineering/inter-annotator-agreement` | Measuring consistency and reading what low agreement actually means. |
| `subskills/adjudication-and-consensus.md` | `software-engineering/adjudication-and-consensus` | Resolving the items annotators split on, without laundering noise. |
| `subskills/quality-control-labels.md` | `software-engineering/quality-control-labels` | Golden labels, attention checks, and audits that catch drift. |
| `subskills/active-learning-and-sampling.md` | `software-engineering/active-learning-and-sampling` | Choosing which items to label when the budget is fixed. |
| `subskills/annotation-record.md` | `software-engineering/annotation-record` | The written record that makes a labeled set trustworthy. |

## Status and honest limits

Agreement is a necessary, not sufficient, condition for quality: annotators can agree perfectly on a wrong or biased reading, so high kappa never certifies correctness. Golden labels only catch the errors they were designed to catch, and a taxonomy that forces a bad fit produces consistent garbage. Nothing here guarantees a dataset is fit for a particular model; it makes the labeling process auditable and its weaknesses explicit, which is the most any annotation method can honestly claim.