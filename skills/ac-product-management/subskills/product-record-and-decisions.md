---
name: product-record-and-decisions
domain: software-engineering/product-record-and-decisions
trigger: "Writing the product decision record, assumptions log, or discovery synthesis."
anti_trigger: "Not for the spec document, and not for the experiment readout."
scope: "The written product decision record and assumptions log."
status: seedling
---

# Product record and decisions

## Standard

The product record makes the reasoning behind a direction auditable and revisable. It captures the opportunity framed, the evidence gathered, the assumptions the decision rests on, and the call that was made with its reasons — so that a later team can tell what was decided, on what evidence, and what would change it. Without it, product decisions become folklore that cannot be questioned because no one remembers why.

The opportunity solution tree is the organising artifact: the desired outcome at the top, the opportunities beneath it, the candidate solutions under each opportunity, and the experiments that test them. It keeps the link from outcome to evidence to solution visible in one place. Alongside it sits the assumptions log — the beliefs the plan depends on, ranked by fragility, each with the test that would confirm or break it — and the decision record itself, which states what was decided, why, and what would trigger a revisit.

Primary sources: <https://www.producttalk.org/> and <https://www.svpg.com/>.

## Decision rules

- Record the desired outcome and the opportunities and solutions beneath it in one tree.
- Keep an assumptions log, ranked by fragility, each with its test.
- State each decision with the evidence behind it and what would change it.
- Separate what was learned from what was decided, and both from what was built.
- Revisit the record when evidence changes, and amend it openly.
- Record rejected options and the reasons, so they are not re-litigated blindly.

## Procedure

1. Place the desired outcome at the top of the opportunity solution tree.
2. Map opportunities, candidate solutions, and the experiments that test them.
3. Log the assumptions the plan depends on, ranked by fragility, with tests.
4. Write the decision: what, why, the evidence, and the revisit trigger.
5. Record rejected options and the reasons for rejection.
6. Review and amend the record as new evidence arrives.

## Anti-patterns

- Decisions that live only in someone's memory or a chat thread.
- An opportunity tree that lists features with no link to an outcome.
- Assumptions with no test attached, so they cannot be challenged.
- Recording only what was built, not what was learned or decided.
- Silently rewriting the record to match what later happened.

## Done checklist

- [ ] Opportunity solution tree maps outcome to evidence to solution.
- [ ] Assumptions logged, ranked by fragility, with tests.
- [ ] Decision stated with evidence and revisit trigger.
- [ ] Learning separated from decision and from build.
- [ ] Rejected options and reasons recorded.
- [ ] Record reviewed and amended on new evidence.

## Sources

- Product Talk, opportunity solution trees and continuous discovery: <https://www.producttalk.org/>
- Silicon Valley Product Group, product decisions and evidence: <https://www.svpg.com/>
- The Lean Startup, validated learning and the build-measure-learn loop: <https://theleanstartup.com/>
