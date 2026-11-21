---
name: estimation-and-budgeting
domain: software-engineering/estimation-and-budgeting
trigger: "Estimating project effort and building the budget."
anti_trigger: "Not for sprint-level task estimates, and not for cost accounting."
scope: "Estimation techniques, budget, and contingency."
status: seedling
---

# Estimation and budgeting

## Standard

Estimates are ranges with a stated basis, not single heroic numbers. Analogous estimation scales from a similar past project; parametric estimation multiplies a measured rate by a quantity; bottom-up estimation sums the work packages; three-point estimation combines optimistic, most-likely and pessimistic figures into an expected value with a spread. The technique is chosen for how much is known, and the estimate always carries its assumptions and its confidence.

The budget aggregates the estimated costs and adds contingency for the risks that were identified. Contingency is sized from the risk register, not from a flat percentage applied by habit, and it is held and controlled separately from the base estimate. Padding every line instead hides the uncertainty rather than managing it, and a budget with no stated contingency is a budget that has already spent its slack without admitting it.

Primary sources: <https://en.wikipedia.org/wiki/Cost_estimation> and <https://en.wikipedia.org/wiki/Project_management>.

## Decision rules

- State every estimate as a range with its basis and assumptions, not a single number.
- Choose the technique for the knowledge available: analogous, parametric, bottom-up, three-point.
- Build the budget bottom-up from the work packages where possible.
- Size contingency from the risk register, held separately from the base estimate.
- Record the estimate's confidence and revisit it as the project learns.
- Never pad individual lines to hide uncertainty; expose it as contingency instead.

## Procedure

1. Choose the estimation technique for the information available.
2. Estimate effort or cost per work package with its assumptions.
3. Apply three-point figures where uncertainty is high.
4. Aggregate into the base budget.
5. Size and hold contingency from the risk register.
6. Record confidence and schedule re-estimation points.

## Anti-patterns

- A single-point estimate presented as a commitment.
- Bottom-up detail invented where the work is not understood.
- Contingency set as a flat percentage with no link to risk.
- Padding every line and then also adding contingency.
- Estimates never revisited as the project learns more.

## Done checklist

- [ ] Technique chosen and stated.
- [ ] Estimates carry ranges and assumptions.
- [ ] Base budget aggregated from packages.
- [ ] Contingency sized from risks, held separately.
- [ ] Confidence recorded.
- [ ] Re-estimation points scheduled.

Re-estimation is where honesty pays. As the project delivers, actuals replace assumptions, and the estimate at completion is revised from measured performance rather than defended from the original optimism. A manager who re-estimates from evidence early can still act on the variance; one who defends the first number until the end can only report it. The estimate is a living forecast, and treating it as a fixed promise converts a planning tool into a source of pressure.

## Sources

- Cost estimation: <https://en.wikipedia.org/wiki/Cost_estimation>
- Project management: <https://en.wikipedia.org/wiki/Project_management>
- Three-point estimation: <https://en.wikipedia.org/wiki/Three-point_estimation>
