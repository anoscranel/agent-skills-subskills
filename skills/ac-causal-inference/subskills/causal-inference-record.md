---
name: causal-inference-record
domain: critical-thinking/causal-inference-record
trigger: "Writing the record that makes a causal claim auditable."
anti_trigger: "Not for running the analysis, and not for the estimand."
scope: "The estimand, assumptions, and honest limits."
status: seedling
---

# Causal inference record

## Standard

The causal-inference record is what lets a reader judge the claim without rerunning the analysis. It opens with the estimand: the effect, intervention, outcome, and population. It then records the identifying strategy and the assumptions it rests on, stated in words, because the estimate means nothing without them. The DAG or the equivalent assumption statement is included, with the adjustment set or the identification argument that follows from it.

The record carries the diagnostics and the limits together. Balance or overlap statistics for a matching design, the first-stage strength for an instrument, the parallel-trends evidence for a difference-in-differences, and the cutoff continuity for a discontinuity design are reported alongside the estimate. The sensitivity analysis states how much unmeasured confounding would overturn the result, and the placebo results are shown. Finally the record names what remains unverifiable: the assumption the data cannot test, the population the estimate does not cover, and the direction of the likely remaining bias. A record that presents only the estimate and its standard error is an association with a causal label, not a causal analysis.

Primary sources: <https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/> and <https://ftp.cs.ucla.edu/pub/stat_ser/r350.pdf>.

## Decision rules

- Open with the estimand, then the identifying assumptions in words.
- Include the DAG or the assumption statement and the adjustment argument.
- Report the design's diagnostics next to the estimate.
- Carry the sensitivity and placebo results with the effect.
- Name what stays unverifiable and the likely bias direction.

## Procedure

1. Record the estimand and the identifying assumptions.
2. Attach the graph and the adjustment or identification argument.
3. Add balance, first-stage, trends, or continuity diagnostics.
4. Report the sensitivity summary and placebo results.
5. Write the unverifiable assumptions and the bias direction.

## Anti-patterns

- An estimate and a standard error presented as the whole analysis.
- Assumptions left implicit or asserted as obvious.
- Diagnostics omitted because they were inconvenient.
- No statement of what the data cannot verify.

## Done checklist

- [ ] Estimand and assumptions recorded.
- [ ] Graph and identification argument included.
- [ ] Diagnostics reported with the estimate.
- [ ] Sensitivity and placebo results shown.
- [ ] Unverifiable assumptions and bias direction named.

The record is versioned with the data and the code that produced the estimate, so that a later reader can reproduce both the number and the assumptions that generated it.

## Sources

- Reporting the causal analysis: <https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/>
- Assumptions and diagrams: <https://ftp.cs.ucla.edu/pub/stat_ser/r350.pdf>
- Causal inference craft: <https://en.wikipedia.org/wiki/Causal_inference>
