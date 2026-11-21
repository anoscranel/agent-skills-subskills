---
name: natural-experiments
domain: critical-thinking/natural-experiments
trigger: "Using an external source of variation to identify an effect."
anti_trigger: "Not for covariate matching, and not for randomized designs."
scope: "IV, difference-in-differences, regression discontinuity."
status: seedling
---

# Natural experiments

## Standard

When measured covariates are not enough, an external source of variation can identify the effect. An instrumental variable moves the treatment but affects the outcome only through the treatment: it needs relevance (it actually shifts treatment), the exclusion restriction (no direct path to the outcome), and independence (it is not confounded with the outcome). The estimate is then a local effect for the units whose treatment the instrument moves, not a universal average, and the exclusion restriction is an assumption that must be argued, since it cannot be tested from the data.

Difference-in-differences compares the change over time in a treated group with the change in a comparison group; its identifying assumption is parallel trends, that absent treatment the groups would have moved together. That assumption is not proven by similar pre-trends, only made more plausible. Regression discontinuity exploits a cutoff that assigns treatment by a running variable; its assumption is that units just either side of the cutoff are otherwise comparable, so the jump at the cutoff is the effect. The design is checked by continuity of covariates at the cutoff and by the absence of manipulation of the running variable around it.

Primary sources: <https://doi.org/10.1080/01621459.1996.10476902> and <https://doi.org/10.1162/003355304772839588>.

## Decision rules

- Argue each design's identifying assumption before trusting the estimate.
- IV needs relevance, exclusion, and independence; report the local nature.
- DiD assumes parallel trends, which pre-trends support but cannot prove.
- RDD assumes comparability at the cutoff and no running-variable manipulation.
- Run the design's falsification checks, not just the estimate.

## Procedure

1. Name the external variation and why it is plausibly exogenous.
2. State the identifying assumption in words.
3. Check relevance and the design's diagnostic plots.
4. Run placebo or falsification tests where available.
5. Record the population the estimate applies to.

## Anti-patterns

- Claiming the exclusion restriction is testable from the data.
- Reading an IV estimate as a universal average effect.
- Treating parallel pre-trends as proof of parallel trends.
- Ignoring bunching of the running variable at the cutoff.

## Done checklist

- [ ] Identifying assumption stated in words.
- [ ] Relevance and diagnostics checked.
- [ ] Falsification or placebo tests run.
- [ ] Local-versus-average nature recorded.
- [ ] Manipulation checks done for RDD.

Each design also has a strength or bandwidth choice to make explicit: a weak instrument inflates bias toward the confounded estimate, and a wide discontinuity bandwidth trades comparability for precision.

## Sources

- Instrumental variables: <https://doi.org/10.1080/01621459.1996.10476902>
- Difference-in-differences reliability: <https://doi.org/10.1162/003355304772839588>
- Regression discontinuity: <https://doi.org/10.1016/j.jeconom.2007.05.001>
- DiD method: <https://en.wikipedia.org/wiki/Difference_in_differences>
