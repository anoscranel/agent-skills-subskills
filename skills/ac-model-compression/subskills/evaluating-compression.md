---
name: evaluating-compression
domain: software-engineering/evaluating-compression
trigger: "Checking that a compressed model still meets the quality bar."
anti_trigger: "Not for offline model selection, and not for the compression operation itself."
scope: "Proving the compressed model still meets the bar."
status: seedling
---

# Evaluating compression

## Standard

Compression is not finished when the artifact is smaller; it is finished when the smaller artifact is proven to still do the job. The evaluation has two axes and both are required. Quality: does the compressed model hold the task metric within the stated budget? Fit: does it actually meet the constraint on the target hardware — the memory, the latency, the cost? A model can pass one and fail the other, and reporting only the smaller file size is the classic way compression gets shipped broken.

Quality is measured against the uncompressed baseline on the task's own metric, not on a generic proxy alone. For language models, perplexity gives a quick signal, but downstream task benchmarks and the application's real inputs decide acceptance; a model that holds perplexity while failing the task is a failure. Sensitivity is uneven across the model: some layers and some weight groups tolerate far more compression than others, so a per-layer or per-group sensitivity check finds where the budget was overspent. The regression gate compares the candidate to the baseline under the quality budget stated before compressing, on data the compression calibration never touched.

Primary sources: <https://arxiv.org/abs/2210.17323> and <https://arxiv.org/abs/2306.00978>.

## Decision rules

- Evaluate quality AND fit; both are required for acceptance.
- Measure quality against the uncompressed baseline on the task's own metric.
- Use perplexity as a signal, downstream task performance as the decision.
- Keep the eval set disjoint from the quantization calibration set.
- Run a per-layer sensitivity check when the budget is overspent.
- Gate on the pre-stated quality budget, measured on the target hardware.

## Procedure

1. Re-state the quality budget and the constraint from the decision step.
2. Evaluate the baseline and the candidate on the task metric, same data.
3. Measure memory, latency, and cost on the target device for both.
4. If quality fails, localize with a per-layer sensitivity check.
5. Accept only if quality is within budget AND fit meets the constraint.
6. Record both axes of results and the accept/reject decision.

## Anti-patterns

- Reporting file size as proof that compression worked.
- Judging by perplexity alone when the task has its own metric.
- Evaluating on the calibration set, overstating quality.
- Accepting on quality while the model still misses the latency or memory target.
- No baseline comparison, so degradation has no reference.

## Done checklist

- [ ] Quality and fit both evaluated.
- [ ] Quality compared to the baseline on the task metric.
- [ ] Latency, memory, and cost measured on target.
- [ ] Eval set disjoint from calibration.
- [ ] Sensitivity localized if quality failed.
- [ ] Accept/reject decided against the pre-stated budget.

## Sources

- GPTQ, with per-layer error compensation and evaluations: <https://arxiv.org/abs/2210.17323>
- AWQ, with activation-aware saliency and benchmarks: <https://arxiv.org/abs/2306.00978>
- Model soups, evaluating merged models against parents: <https://arxiv.org/abs/2203.05482>
