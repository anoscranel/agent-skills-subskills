---
name: ac-causal-inference
description: 'Estimating causal effects rather than associations: the causal question and estimand, the causal DAG and confounding, identification strategies, propensity-score matching and adjustment, natural experiments (instrumental variables, difference-in-differences, regression discontinuity), sensitivity analysis for unmeasured confounding, and the written causal-inference record. It draws the line between correlation and cause; it never claims causation from association alone and never hides the identifying assumptions. Use when asking "does X cause Y", "causal inference", "confounding", "causal DAG", "instrumental variables", "difference in differences", "regression discontinuity", "propensity score", "estimate a causal effect from observational data". Not for randomized controlled experiments (ac-online-experiments), not for pooling existing study results (ac-meta-analysis-and-synthesis), not for choosing under uncertainty (ac-decision-analysis), not for offline model evaluation (ac-model-evaluation).'
license: MIT
metadata:
  domain: critical-thinking
status: seedling
---

# Causal inference

## Overview

Most questions that matter are causal: does this policy reduce harm, does this treatment help, did this change cause the improvement. Most data is associational: two things move together. The craft of causal inference is the discipline of stating exactly what causal claim is being made, what assumptions would make it identifiable from the data in hand, and how fragile the conclusion is to those assumptions being wrong.

Association is not causation, and no amount of data fixes that on its own. A correlation can reflect a common cause, reverse causation, or selection. The estimate becomes a causal effect only when a set of identifying assumptions holds, and those assumptions are argued, not tested by the same data. The honest deliverable is an estimate plus the assumptions it rests on plus how sensitive it is to their violation.

Neighbours: ac-online-experiments designs randomized experiments where causation is identified by randomization itself; ac-meta-analysis-and-synthesis pools existing study results; ac-decision-analysis chooses under uncertainty once effects are estimated; ac-model-evaluation tests model behaviour offline. This skill owns the observational case, where no randomization did the work.

Primary sources: <https://ftp.cs.ucla.edu/pub/stat_ser/r350.pdf> and <https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/>.

## When to use

- When the question is whether X causes Y, not merely whether they co-occur.
- When estimating an effect from observational data with no randomization.
- When choosing between matching, instrumental variables, difference-in-differences, or discontinuity designs.
- When stress-testing how much unmeasured confounding would overturn a result.

## When NOT to use

- For randomized controlled experiments (use ac-online-experiments).
- For pooling existing study estimates (use ac-meta-analysis-and-synthesis).
- For choosing among options under uncertainty (use ac-decision-analysis).
- For evaluating model behaviour offline (use ac-model-evaluation).

## Subskill Index

| Leaf | Domain segment | Scope (one line) |
|---|---|---|
| `subskills/the-causal-question.md` | `critical-thinking/the-causal-question` | Stating the estimand before the estimator. |
| `subskills/dag-and-confounding.md` | `critical-thinking/dag-and-confounding` | The causal graph and what confounding is. |
| `subskills/identification-strategies.md` | `critical-thinking/identification-strategies` | How an effect becomes computable from data. |
| `subskills/matching-and-adjustment.md` | `critical-thinking/matching-and-adjustment` | Propensity scores, balance, and adjustment. |
| `subskills/natural-experiments.md` | `critical-thinking/natural-experiments` | IV, difference-in-differences, regression discontinuity. |
| `subskills/sensitivity-and-robustness.md` | `critical-thinking/sensitivity-and-robustness` | Bounding what unmeasured confounding can do. |
| `subskills/causal-inference-record.md` | `critical-thinking/causal-inference-record` | The estimand, assumptions, and honest limits. |

## Status and honest limits

A causal estimate is only as good as its identifying assumptions, and those assumptions are never fully testable from the same data that produced the estimate. Unmeasured confounding, selection into treatment, and measurement error cannot be ruled out by more observations; they can only be bounded and argued. The DAG is a statement of the analyst's assumptions about the world, not a discovery from the data, and two reasonable analysts can draw different graphs and get different answers. Matching and weighting balance measured covariates, never unmeasured ones. Nothing here turns observational data into a randomized experiment; the skill's job is to make the leap from association to causation explicit, argued, and stress-tested, and to say plainly when the data cannot support the causal claim at all.
