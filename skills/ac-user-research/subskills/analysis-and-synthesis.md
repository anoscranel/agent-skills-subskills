---
name: analysis-and-synthesis
domain: software-engineering/analysis-and-synthesis
trigger: "Turning observations into findings and recommendations."
anti_trigger: "Not for collecting the data, and not for statistical hypothesis testing."
scope: "Affinity mapping, severity ratings, findings to recommendations."
status: seedling
---

# Analysis and synthesis

## Standard

Raw observations are not findings. Synthesis turns scattered notes into patterns: an affinity diagram groups individual observations into themes by similarity, so the recurring problems emerge from the bottom up rather than from the facilitator's expectations. Each observation is one note, grouped with like notes, and the clusters are named by what they reveal, not by the feature they concern.

Findings then carry a severity rating so the team fixes what matters. Severity weighs how often a problem occurred, how badly it blocked the task, and how persistent it is across users, on an explicit scale the team agrees on before rating. A finding states the problem, the evidence behind it, and its severity; a recommendation follows from the finding and names the change to make, not the feature to add. The deliverable is a prioritised set of problems with evidence and proposed fixes, traceable back to specific observed sessions.

Primary sources: <https://www.nngroup.com/articles/affinity-diagram/> and <https://en.wikipedia.org/wiki/Usability_testing>.

## Decision rules

- Synthesise bottom-up with an affinity diagram, not top-down from expectations.
- Rate severity on an explicit scale: frequency, task impact, persistence.
- Every finding carries its evidence and severity.
- Recommendations follow from findings and name the change, not a feature.
- Trace each finding back to specific observed sessions.
- Report what worked as well as what failed.

## Procedure

1. Write each observation as one note from a specific session.
2. Group notes by similarity into an affinity diagram.
3. Name each cluster by the problem it reveals.
4. Rate each problem's severity on the agreed scale.
5. Draft a recommendation per finding, naming the change.
6. Prioritise findings by severity with their evidence links.

## Anti-patterns

- Clustering observations by feature instead of by problem.
- Severity assigned by whoever argues loudest.
- Findings with no session evidence behind them.
- Recommendations that are feature requests, not fixes.
- Reporting only failures and hiding what worked.

## Done checklist

- [ ] Observations noted per session.
- [ ] Affinity clusters built and named.
- [ ] Severity rated on an explicit scale.
- [ ] Findings carry evidence and severity.
- [ ] Recommendations name the change.
- [ ] Successes reported alongside failures.

Severity is not the only prioritisation input, and the rating is not the decision. A severe problem on a rarely-used flow may rank below a moderate one on the path every user takes, so severity is read alongside how central the affected task is to the product's purpose and how costly the fix is. The rating makes the trade-off explicit and reviewable rather than settling it, and a finding the team chooses not to fix is recorded with the reason, so a later regression can be recognised as a known, accepted problem rather than a new discovery.

## Sources

- Affinity diagram method: <https://www.nngroup.com/articles/affinity-diagram/>
- Usability testing practice: <https://en.wikipedia.org/wiki/Usability_testing>
- Usability and evaluation: <https://en.wikipedia.org/wiki/Usability>
