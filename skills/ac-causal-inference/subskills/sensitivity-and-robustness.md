---
name: sensitivity-and-robustness
domain: critical-thinking/sensitivity-and-robustness
trigger: "Testing how much unmeasured confounding would change the conclusion."
anti_trigger: "Not for the point estimate, and not for the DAG."
scope: "Bounding what unmeasured confounding can do."
status: seedling
---

# Sensitivity and robustness

## Standard

Unmeasured confounding cannot be ruled out by any amount of data or by balancing measured covariates. The honest response is to bound it rather than to ignore it. Sensitivity analysis asks how strong an unmeasured confounder would have to be, in its association with both treatment and outcome, to explain away the estimated effect. The E-value summarizes this as the minimum strength of association an unmeasured confounder would need to move the estimate to the null; Rosenbaum bounds do the same for matched designs. A conclusion that survives only a weak confounder is fragile, and that fragility belongs in the result, not in a footnote.

Placebo and falsification tests probe the assumption from other angles. A treatment that should have no effect, an outcome that should not be affected, or a period before the treatment began should each give a null result; a non-null placebo signals unmeasured confounding, selection, or a broken design. Robustness is reported as the direction of the likely bias as well as its size: if the remaining confounding plausibly pushes the estimate toward the null, the true effect is larger, and saying which way it pushes is part of the finding.

Primary sources: <https://en.wikipedia.org/wiki/Confounding> and <https://en.wikipedia.org/wiki/Causal_inference>.

## Decision rules

- Bound unmeasured confounding rather than assuming it away.
- Report the strength of confounder needed to explain the effect away.
- Run placebo tests that should return null.
- State the direction of the likely remaining bias.
- A result that survives only a weak confounder is reported as fragile.

## Procedure

1. Compute a sensitivity summary such as the E-value.
2. State how strong a confounder would overturn the result.
3. Run placebo treatments, outcomes, or periods.
4. Assess the plausible direction of remaining bias.
5. Report fragility and bias direction with the estimate.

## Anti-patterns

- Declaring unmeasured confounding absent because covariates balanced.
- Reporting a point estimate with no sensitivity analysis.
- Ignoring a non-null placebo result.
- Omitting the direction of the remaining bias.

## Done checklist

- [ ] Sensitivity summary computed.
- [ ] Overturn-strength stated.
- [ ] Placebo tests run and null confirmed.
- [ ] Bias direction assessed.
- [ ] Fragility reported with the estimate.

Sensitivity analysis is not a way to rescue a broken design; it is a way to show how much additional structure the conclusion can bear before it collapses.

## Sources

- Unmeasured confounding: <https://en.wikipedia.org/wiki/Confounding>
- Causal assumptions and sensitivity: <https://en.wikipedia.org/wiki/Causal_inference>
- Bias analysis: <https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/>
