---
name: matching-and-adjustment
domain: critical-thinking/matching-and-adjustment
trigger: "Balancing treated and untreated groups on measured covariates."
anti_trigger: "Not for identification logic, and not for unmeasured confounding."
scope: "Propensity scores, balance, and adjustment."
status: seedling
---

# Matching and adjustment

## Standard

When the measured covariates are sufficient for exchangeability, the treated and untreated groups are made comparable by balancing those covariates. The propensity score, the probability of treatment given the covariates, summarizes the covariates into one number; matching, weighting, or stratifying on it reproduces a comparison in which the measured covariates are balanced across groups. The point is design, not modelling: the groups are balanced first, and only then is the outcome compared. The outcome model is the second step, not a substitute for balance.

Balance is checked, not assumed. The diagnostic is the standardized mean difference of each covariate across the balanced groups, not a significance test of the covariate-treatment association, which confounds balance with sample size. Overlap, or common support, is the requirement that treated and untreated units occupy the same covariate region; units outside it cannot be matched and are dropped or the estimand is narrowed to the region of overlap. The crucial discipline is that balance is assessed without looking at the outcome, because peeking at outcomes while adjusting turns design into fishing.

Primary sources: <https://en.wikipedia.org/wiki/Propensity_score_matching> and <https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/>.

## Decision rules

- Balance measured covariates before comparing outcomes.
- Diagnose balance by standardized mean differences, not p-values.
- Require overlap; drop or narrow to the common support.
- Assess balance without looking at the outcome.
- Balance measured covariates only; unmeasured ones are not addressed.

## Procedure

1. Estimate the propensity score from the measured covariates.
2. Match, weight, or stratify on the score.
3. Check standardized mean differences for every covariate.
4. Restrict to the region of common support.
5. Compare outcomes only after balance is achieved.

## Anti-patterns

- Using a significance test to declare the groups balanced.
- Extrapolating to strata with no overlap.
- Adjusting the model until the outcome looks right.
- Assuming matching removes unmeasured confounding.

## Done checklist

- [ ] Propensity score estimated.
- [ ] Groups balanced by match, weight, or strata.
- [ ] Standardized mean differences checked.
- [ ] Common support enforced.
- [ ] Outcomes compared only after balance.

Matching also clarifies the estimand: restricting to common support changes the population the effect describes, and the record must say whether the result is the effect on the treated, on the matched subset, or on the whole population. Where overlap is poor, the honest answer is a narrower question, not a wider extrapolation.

## Sources

- Propensity score methods: <https://en.wikipedia.org/wiki/Propensity_score_matching>
- Balance and adjustment: <https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/>
- Confounding control: <https://en.wikipedia.org/wiki/Confounding>
