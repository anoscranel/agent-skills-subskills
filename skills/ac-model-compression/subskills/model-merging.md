---
name: model-merging
domain: software-engineering/model-merging
trigger: "Combining several fine-tuned models into one without retraining."
anti_trigger: "Not for ensembling at inference, and not for training a new model from data."
scope: "Combining fine-tuned weights: soups, task arithmetic, DARE."
status: seedling
---

# Model merging

## Standard

Merging combines the weights of several models into a single model, with no further training and no increase in inference cost. It works only under a hard constraint: the models must share an architecture and, for weight averaging, a common pretrained initialization — averaging weights from unrelated initializations lands in a meaningless region of weight space. Model soups average the weights of several fine-tunes of the same base and often improve accuracy and robustness over any single fine-tune, for free at inference time. This is different from ensembling, which runs every model and combines outputs at a per-request cost.

The richer operations treat a fine-tune as a displacement from its base. A task vector is the difference between a fine-tuned model and its pretrained base; task arithmetic adds or negates these vectors to add or remove behaviours. SLERP interpolates between two models along a sphere rather than a straight line, which can preserve more of each parent's behaviour. DARE drops most of each delta (often ninety percent or more) and rescales the rest before merging, which reduces interference between parents. Merging is cheap to try and cheap to get wrong: parents that pull in incompatible directions produce a merged model worse than either, so the merge is always an experiment measured against the parents, never an assumption of improvement.

Primary sources: <https://arxiv.org/abs/2203.05482> and <https://arxiv.org/abs/2212.04089>.

## Decision rules

- Merge only models sharing architecture and, for averaging, a common base.
- Use soups to combine same-base fine-tunes for robustness at no inference cost.
- Use task arithmetic to add or negate specific behaviours via task vectors.
- Use DARE-style delta dropping when parents interfere.
- Evaluate the merge against every parent on each parent's task, not only the blend.
- Treat every merge as a measured experiment; discard merges that lose to a parent.

## Procedure

1. Confirm shared architecture and common base across all parents.
2. Choose the operation: averaging, task arithmetic, interpolation, or DARE.
3. Compute the merge with a tool such as mergekit.
4. Evaluate on each parent's task and on the combined objective.
5. Compare against the best single parent; keep only wins.
6. Record parents, operation, coefficients, and per-task results.

## Anti-patterns

- Averaging weights from different pretrained bases or architectures.
- Calling a merge an ensemble and paying per-request cost for it.
- Evaluating only the blended objective and missing a parent's regression.
- Merging many models at once and being unable to attribute interference.
- Assuming a merge improves things without measuring against the parents.

## Done checklist

- [ ] Shared architecture and base confirmed.
- [ ] Merge operation chosen.
- [ ] Merge computed (e.g. mergekit).
- [ ] Evaluated on each parent's task and the blend.
- [ ] Compared against the best parent; losers discarded.
- [ ] Parents, coefficients, and results recorded.

## Sources

- Model soups: <https://arxiv.org/abs/2203.05482>
- Editing Models with Task Arithmetic: <https://arxiv.org/abs/2212.04089>
- DARE, absorbing abilities from homologous models: <https://arxiv.org/abs/2311.03099>
- mergekit, a toolkit for merging models: <https://github.com/arcee-ai/mergekit>
