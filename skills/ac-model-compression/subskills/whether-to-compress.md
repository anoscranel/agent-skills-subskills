---
name: whether-to-compress
domain: software-engineering/whether-to-compress
trigger: "Deciding if and how to compress a model for a deployment constraint."
anti_trigger: "Not for serving infrastructure, and not for offline model selection."
scope: "The decision: constraint, quality budget, and the alternatives."
status: seedling
---

# Whether to compress

## Standard

Compression is warranted only against a named constraint. Before touching the model, state the constraint in numbers: the memory ceiling on the device, the storage budget, the latency target, or the cost per request that the current model misses. Then state the quality budget — how much measured degradation the task can absorb — because every compression scheme spends some of it. A model that already fits its constraint with margin does not need compressing; compressing it spends quality for no requirement.

The alternatives to compressing the current model deserve a fair hearing first. A smaller model trained from scratch, or a smaller member of the same family, often beats a heavily compressed large model on quality per byte. Using the serving layer better — a smaller batch, a faster kernel, a cheaper replica — can meet the constraint without touching the artifact. Compression is the answer when the alternatives fall short: the large model's quality is needed but its size is not affordable, and no smaller off-the-shelf model reaches the bar.

Primary sources: <https://arxiv.org/abs/2210.17323> and <https://arxiv.org/abs/2203.05482>.

## Decision rules

- Name the constraint in numbers (memory, storage, latency, cost) before compressing.
- State the quality budget: the maximum measured degradation the task accepts.
- Compare against a smaller model of the same family before compressing a large one.
- Consider serving-layer fixes (kernel, batch, replica) before altering the artifact.
- Choose the scheme by constraint: size and edge CPU → quantization; capability transfer → distillation; latency with hardware support → structured pruning; combining fine-tunes → merging.
- Do not compress a model that already meets its constraint with margin.

## Procedure

1. Measure the current model against the constraint on the target device.
2. Write the quality budget and the metric it is measured on.
3. Evaluate the smaller-family-model alternative on the same metric.
4. List serving-layer fixes that could meet the constraint untouched.
5. If compression is still warranted, pick the scheme that matches the constraint.
6. Record the constraint, budget, and the alternatives rejected, with reasons.

## Anti-patterns

- Compressing because it is fashionable, with no named constraint.
- Skipping the smaller-model comparison and assuming the large model is needed.
- No stated quality budget, so "acceptable" is decided after the fact.
- Choosing a scheme before knowing which constraint binds.
- Assuming compression is the only lever when serving changes would suffice.

## Done checklist

- [ ] Constraint quantified on the target device.
- [ ] Quality budget stated with its metric.
- [ ] Smaller-model alternative evaluated.
- [ ] Serving-layer fixes considered.
- [ ] Scheme chosen to match the binding constraint.
- [ ] Rejected alternatives recorded with reasons.

## Sources

- GPTQ, post-training quantization for large models: <https://arxiv.org/abs/2210.17323>
- Model soups, averaging fine-tuned weights: <https://arxiv.org/abs/2203.05482>
- Deep Compression, the combined-prune-quantize pipeline: <https://arxiv.org/abs/1510.00149>
