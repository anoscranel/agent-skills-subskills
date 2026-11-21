---
name: the-causal-question
domain: critical-thinking/the-causal-question
trigger: "Turning a vague 'does X affect Y' into a computable causal question."
anti_trigger: "Not for the estimation method, and not for the graph."
scope: "Stating the estimand before the estimator."
status: seedling
---

# The causal question

## Standard

Before any estimator is chosen, the causal question is written as an estimand: the effect, of a specified intervention, on a specified outcome, in a specified population. The potential-outcomes frame makes this precise: each unit has an outcome under treatment and under control, and the causal effect is the contrast between them. Since only one is ever observed, the estimand is an average over a population, never a per-unit fact recoverable from data. The average treatment effect, the effect on the treated, and the effect on a subpopulation are different quantities, and the method that estimates one need not estimate another.

The discipline is that the intervention must be well-defined. "Does exercise help" is not an estimand until the intervention (how much, versus what), the outcome (which measure, when), and the population (whom) are fixed. Vague interventions produce effects that cannot be replicated or contradicted. The question is also distinguished from the associational question it replaces: "treated units differ from untreated" is a description, not a causal claim, and writing the estimand is what forces the difference to be faced.

Primary sources: <https://en.wikipedia.org/wiki/Rubin_causal_model> and <https://en.wikipedia.org/wiki/Causal_inference>.

## Decision rules

- Write the estimand before any method: effect, intervention, outcome, population.
- The intervention must be well-defined enough to replicate or contradict.
- State which effect is wanted: overall average, effect on the treated, or a subgroup.
- Distinguish the causal question from the associational one it replaces.
- Refuse questions whose intervention cannot be stated concretely.

## Procedure

1. Write the intervention precisely, including the comparison condition.
2. Name the outcome and the time at which it is measured.
3. Define the target population the effect averages over.
4. Choose the effect type: ATE, ATT, or a named subgroup effect.
5. Record the associational quantity the data actually shows, separately.

## Anti-patterns

- Estimating before the intervention and population are fixed.
- Treating the treated-versus-untreated difference as the effect.
- An intervention so vague the effect cannot be contradicted.
- Reporting one effect type while the question asked another.

## Done checklist

- [ ] Estimand written: effect, intervention, outcome, population.
- [ ] Intervention concrete enough to replicate.
- [ ] Effect type chosen and named.
- [ ] Causal question separated from the associational one.
- [ ] Vague questions refused or made concrete.

A clearly written estimand is the cheapest error-catcher in the whole analysis, because it exposes a mismatch between the question and the method before any computing is done.

## Sources

- Potential outcomes and the estimand: <https://en.wikipedia.org/wiki/Rubin_causal_model>
- Causal versus associational claims: <https://en.wikipedia.org/wiki/Causal_inference>
- Counterfactual estimation: <https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/>
