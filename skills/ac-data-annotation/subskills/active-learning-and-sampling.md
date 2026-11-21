---
name: active-learning-and-sampling
domain: software-engineering/active-learning-and-sampling
trigger: "Choosing which items to label when the budget is fixed."
anti_trigger: "Not for training the model, and not for measuring agreement."
scope: "Choosing which items to label when the budget is fixed."
status: seedling
---

# Active learning and sampling

## Standard

A label budget is almost always smaller than the pool of items, so the sampling decision — which items get labeled — is a first-class part of the annotation craft, not an afterthought. Settles' survey frames active learning as the discipline of spending labels where they buy the most: the learner queries the items it is most uncertain about, or that best cover the input space, instead of labeling a uniform random slice. For a labeling project the same logic applies even without a model in the loop — stratify to cover the taxonomy, oversample the rare and the hard, and do not spend the budget redundantly on items that are all the same easy case.

The trap is that uncertainty sampling alone concentrates labels on the decision boundary and can starve the representative coverage a dataset also needs; a set that is all boundary cases is not a faithful sample of the population. The working posture combines strategies: a coverage/stratified base so every label and region is represented, plus an uncertainty or diversity overlay that targets the informative items. The sampling plan is written down before labeling, because a plan chosen after seeing the data is a plan fitted to the data. And the honest limit: active learning reduces the labels needed for a given quality, it does not remove the need for quality control on the labels it does select.

Primary sources: <https://burrsettles.com/pub/settles.activelearning.pdf> and <https://aclanthology.org/D08-1027/>.

## Decision rules

- Write the sampling plan before labeling, not after seeing the data.
- Guarantee stratified coverage of every label and input region as a base.
- Overlay uncertainty or diversity sampling to target informative items.
- Oversample rare and hard cases; do not spend budget on redundant easy items.
- State the label budget and the stopping rule up front.
- Keep quality control on selected items; sampling does not replace it.

## Procedure

1. Fix the label budget and the coverage requirements per label.
2. Draw a stratified base sample covering the taxonomy and input space.
3. Add an uncertainty/diversity overlay for the remaining budget.
4. Record the sampling plan and its rationale before labeling starts.
5. Label the selected items under the normal quality-control regime.
6. Evaluate coverage and informativeness; adjust the next round's plan.

## Anti-patterns

- Labeling a uniform random slice when the budget is tight.
- Pure uncertainty sampling that starves representative coverage.
- Choosing the sample after inspecting the data, then calling it principled.
- Spending the budget on redundant easy cases.
- Assuming active-selected labels need no quality control.

## Done checklist

- [ ] Sampling plan written before labeling.
- [ ] Stratified coverage base guaranteed.
- [ ] Uncertainty/diversity overlay applied.
- [ ] Rare and hard cases oversampled.
- [ ] Budget and stopping rule stated.
- [ ] Quality control retained on selected items.

## Sources

- Active Learning Literature Survey (Settles): <https://burrsettles.com/pub/settles.activelearning.pdf>
- Cheap and Fast – But is it Good? (Snow et al.): <https://aclanthology.org/D08-1027/>
- Get Another Label? (Sheng et al.): <https://doi.org/10.1145/1401890.1401965>