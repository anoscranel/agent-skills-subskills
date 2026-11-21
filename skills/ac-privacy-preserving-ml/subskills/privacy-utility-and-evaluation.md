---
name: privacy-utility-and-evaluation
domain: software-engineering/privacy-utility-and-evaluation
trigger: "Measuring what a privacy guarantee costs and whether it actually holds."
anti_trigger: "Not for choosing the mechanism, and not for general model evaluation."
scope: "Measuring what the guarantee costs and whether it holds."
status: seedling
---

# Privacy, utility, and evaluation

## Standard

A privacy guarantee is only meaningful alongside two measurements: what it cost, and whether it withstands attack. The cost is a utility delta — the drop in accuracy, calibration, or per-group fairness between the private model and a non-private baseline trained on the same data with the same budget. Reporting epsilon without the utility delta hides the price; reporting the delta without epsilon hides the guarantee. Both numbers belong in the same sentence.

The second measurement is adversarial. A membership-inference attack trains a shadow model to predict whether a specific record was in the training set, and the attack's advantage over chance is the empirical leakage; a well-implemented (epsilon, delta) mechanism should cap that advantage near the theoretical bound. Model-inversion and attribute-inference attacks probe whether inputs or sensitive attributes can be reconstructed from outputs. The evaluation posture is to run these attacks against the trained model and check that the measured leakage is consistent with the claimed budget, because a miswired clip or a forgotten noise term shows up as an attack that succeeds far beyond what epsilon predicts.

Primary sources: <https://arxiv.org/abs/1607.00133> and <https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf>.

## Decision rules

- Report the privacy budget and the utility delta together, never one alone.
- Compare against a non-private baseline on identical data, budget, and metric.
- Run membership-inference and inversion attacks and compare measured leakage to the bound.
- Break the utility delta down per group; DP noise often costs minority groups more.
- Treat the budget as a hard cap, not a target to approach for extra accuracy.
- A measured attack far above the theoretical bound indicates a bug, not a stronger adversary.

## Procedure

1. Train the non-private baseline on the same data and budget.
2. Measure the utility delta overall and per group.
3. Run a membership-inference attack with shadow models.
4. Run an inversion or attribute-inference attack where relevant.
5. Compare measured attack advantage to the theoretical (epsilon, delta) bound.
6. Record the budget, the utility delta, and the attack results together.

## Anti-patterns

- Quoting epsilon with no utility measurement.
- Quoting accuracy with no privacy budget.
- Comparing the private model to a baseline trained with more data or steps.
- Reporting only pooled accuracy while a minority group degrades sharply.
- Declaring privacy because no attack was tried.

## Done checklist

- [ ] Non-private baseline on identical data and budget.
- [ ] Utility delta measured overall and per group.
- [ ] Membership-inference attack run and advantage measured.
- [ ] Inversion or attribute attack run where relevant.
- [ ] Measured leakage compared to the theoretical bound.
- [ ] Budget, delta, and attack results recorded together.

## Sources

- Deep Learning with Differential Privacy (Abadi et al.): <https://arxiv.org/abs/1607.00133>
- The Algorithmic Foundations of Differential Privacy: <https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf>
- Differential privacy overview: <https://en.wikipedia.org/wiki/Differential_privacy>
