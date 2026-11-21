---
name: identification-strategies
domain: critical-thinking/identification-strategies
trigger: "Deciding how an effect can be computed from the data."
anti_trigger: "Not for the estimator's mechanics, and not for the record."
scope: "How an effect becomes computable from data."
status: seedling
---

# Identification strategies

## Standard

Identification is the logical step that turns an association into a causal effect: under a stated set of assumptions, the observed data determine the causal quantity. Randomization identifies the effect by making treatment independent of potential outcomes by construction. Without randomization, the effect is identified only by assumption: conditional exchangeability (treated and untreated are comparable given the measured covariates), positivity (every covariate stratum has a chance of each treatment), and consistency (the observed outcome under the actual treatment equals the potential outcome). These are assumptions about the world, argued from subject knowledge, not properties the data can confirm.

The identification strategies are the ways the assumption set can be satisfied. Backdoor adjustment identifies the effect when the measured covariates block every backdoor path. The front-door criterion identifies it through a mediator when the treatment-outcome confounding cannot be adjusted directly but the mediator can. Instrumental variables identify it through a variable that moves treatment but not the outcome directly. Do-calculus is the general machinery that decides, for a given graph, whether the effect is identifiable at all and by what formula. The discipline is that identification is argued before estimation, and an effect that is not identified cannot be rescued by a better estimator.

Primary sources: <https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/> and <https://doi.org/10.1017/CBO9780511803161>.

## Decision rules

- Argue identification before choosing any estimator.
- State exchangeability, positivity, and consistency explicitly.
- Use backdoor adjustment only when measured covariates block all backdoors.
- An unidentified effect cannot be rescued by a better estimator.
- Record which identifying assumption each conclusion depends on.

## Procedure

1. State the identifying assumptions the design relies on.
2. Check exchangeability is plausible from subject knowledge.
3. Check positivity: every stratum has both treated and untreated.
4. Choose the strategy the graph licenses: backdoor, front-door, IV.
5. Record the assumptions each conclusion rests on.

## Anti-patterns

- Estimating first and asserting identification afterwards.
- Assuming exchangeability because the covariate list is long.
- Ignoring positivity and extrapolating to unsupported strata.
- Treating a significant estimate as evidence the effect is identified.

## Done checklist

- [ ] Identifying assumptions stated.
- [ ] Exchangeability argued from knowledge.
- [ ] Positivity checked.
- [ ] Strategy licensed by the graph.
- [ ] Assumption-dependence recorded per conclusion.

The choice among strategies is driven by the graph and by which assumptions are most defensible, not by which estimator is most familiar or most convenient to run.

## Sources

- Identification and the causal estimand: <https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/>
- Do-calculus and identification: <https://doi.org/10.1017/CBO9780511803161>
- Causal inference overview: <https://en.wikipedia.org/wiki/Causal_inference>
