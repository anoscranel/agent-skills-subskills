---
name: prioritization-frameworks
domain: software-engineering/prioritization-frameworks
trigger: "Ranking opportunities, features, or a backlog with an explicit framework."
anti_trigger: "Not for product discovery, and not for task-level estimation."
scope: "Ranking opportunities with explicit, evidence-weighted frameworks."
status: seedling
---

# Prioritisation frameworks

## Standard

Prioritisation is the disciplined act of saying no. A framework makes the trade-off explicit and comparable across candidates, so the decision rests on stated criteria rather than on whoever argues loudest. The point of a scoring model is not a false-precision number but a structured conversation about reach, impact, confidence, and effort that exposes what the ranking actually depends on.

The main frameworks serve different questions. RICE scores reach × impact × confidence ÷ effort, and its confidence term is the honest one — it forces the team to discount ideas resting on weak evidence. Weighted Shortest Job First ranks cost of delay ÷ job size, favouring the highest value per unit of time. The Kano model classifies features by how satisfaction responds to them — basic expectations, performance factors, delighters — which scoring models alone cannot capture. Value-versus-effort mapping is the quick visual sort.

Primary sources: <https://www.intercom.com/blog/rice-simple-prioritization-for-product-managers> and <https://en.wikipedia.org/wiki/Kano_model>.

## Decision rules

- Choose the framework for the question: RICE for reach and confidence, WSJF for cost of delay, Kano for satisfaction shape.
- Score confidence explicitly and discount ideas that rest on weak evidence.
- Estimate effort in comparable units; a ranking is only as good as its denominator.
- Use Kano to separate basic expectations from delighters before scoring impact.
- Treat the output as a structured input to a decision, not as the decision itself.
- Say no explicitly and record what was rejected and why.

## Procedure

1. List the candidate opportunities in comparable terms.
2. Choose the framework that fits the decision.
3. Score each candidate on the framework's factors, with evidence for each estimate.
4. Discount or flag candidates whose impact rests on low-confidence evidence.
5. Discuss the sensitivities that would change the ranking.
6. Record the ranking, the rejected candidates, and the reasons.

## Anti-patterns

- Using a framework's number as a substitute for judgment.
- Scoring impact high on unproven ideas while leaving confidence implicit.
- Ranking without a comparable effort estimate, so cheap ideas look free.
- Ignoring basic expectations and only funding delighters.
- Keeping every candidate alive, so nothing is actually prioritised.

## Done checklist

- [ ] Framework chosen to fit the decision.
- [ ] Confidence scored and low-evidence ideas discounted.
- [ ] Effort estimated in comparable units.
- [ ] Kano shape considered before impact scoring.
- [ ] Sensitivities that would change the ranking discussed.
- [ ] Ranking and rejected candidates recorded with reasons.

## Sources

- Intercom, RICE prioritisation: <https://www.intercom.com/blog/rice-simple-prioritization-for-product-managers>
- Kano model of customer satisfaction: <https://en.wikipedia.org/wiki/Kano_model>
- Silicon Valley Product Group, prioritisation and product decisions: <https://www.svpg.com/>
