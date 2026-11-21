---
name: expected-value-and-decision-trees
domain: critical-thinking/expected-value-and-decision-trees
trigger: "Valuing the alternatives and handling sequential choices."
anti_trigger: "Not for eliciting probabilities, and not for sensitivity analysis."
scope: "Valuing paths, sequential choices, and risk attitude."
status: seedling
---

# Expected value and decision trees

## Standard

With options, objectives, and probabilities in hand, each path can be valued. The expected value of an option is the probability-weighted average of its outcomes; it is the right criterion for a decision repeated many times or one whose stakes the decider can absorb. A decision tree lays the choice out over time: decision nodes where the decider chooses, chance nodes where nature resolves, and terminal outcomes scored on the objectives. Folding the tree back from the leaves, taking the best option at each decision node and the expectation at each chance node, yields the value of the whole sequence, including choices that only arise after information arrives.

Expected value is not always the criterion. Where an outcome could ruin the decider, or the decision is one-shot with stakes that cannot be absorbed, risk attitude matters, and the objective becomes expected utility rather than expected money. Prospect theory documents that people weigh losses more heavily than equivalent gains and are risk-averse over gains but risk-seeking over losses, so a stated preference for "the safe option" is a judgment to elicit, not a number to assume. The rule is to match the criterion to the stakes: expected value for absorbable, repeated bets; explicit risk attitude where a tail outcome is unaffordable.

Primary sources: <https://en.wikipedia.org/wiki/Expected_utility_hypothesis> and <https://doi.org/10.2307/1914185>.

## Decision rules

- Use expected value for repeated or absorbable bets.
- Build a tree when choices arrive in sequence or after information.
- Fold back: best at decision nodes, expectation at chance nodes.
- Switch to expected utility when a tail outcome is unaffordable.
- Elicit risk attitude; do not assume risk-neutrality.
- Score terminal outcomes on the objectives, not only on money.

## Procedure

1. Lay out decision nodes and chance nodes in time order.
2. Attach probabilities to chance branches and scores to terminal outcomes.
3. Fold the tree back from the leaves.
4. Read off the value of the initial choice.
5. Test whether a tail outcome is unaffordable; if so, restate in utility.
6. Record the criterion used and why it fits the stakes.

## Anti-patterns

- Applying expected value to a one-shot ruin-risk decision.
- Assuming risk-neutrality the decider never stated.
- Scoring outcomes on money alone when other objectives bind.
- Ignoring decisions that only arise after information arrives.
- Reporting an expected value as a guaranteed outcome.

## Done checklist

- [ ] Options valued with a stated criterion.
- [ ] Tree built for sequential or information-dependent choices.
- [ ] Fold-back computed correctly.
- [ ] Risk attitude elicited where tails are unaffordable.
- [ ] Outcomes scored on all binding objectives.
- [ ] Criterion and its justification recorded.

## Sources

- Expected utility hypothesis: <https://en.wikipedia.org/wiki/Expected_utility_hypothesis>
- Kahneman & Tversky, Prospect Theory: <https://doi.org/10.2307/1914185>
- Decision trees: <https://en.wikipedia.org/wiki/Decision_tree>
