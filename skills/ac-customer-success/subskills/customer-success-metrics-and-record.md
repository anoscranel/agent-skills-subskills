---
name: customer-success-metrics-and-record
domain: software-engineering/customer-success-metrics-and-record
trigger: "Measuring customer success and writing the record."
anti_trigger: "Not for product metrics, and not for the success plan itself."
scope: "NRR, GRR, logo retention, and the written CS record."
status: seedling
---

# Customer success metrics and record

## Standard

The metrics tell you whether the motion works. Gross revenue retention (GRR) is the revenue kept from the base excluding expansion; it exposes churn and contraction. Net revenue retention (NRR) adds expansion, so it can exceed 100% and can hide logo churn behind a few large expansions. Logo retention counts customers kept, independent of their size. Report all three: NRR alone can flatter a business that is quietly losing many small customers while growing a few big ones.

The record makes the motion reviewable: per-account outcome and health, the playbooks and their measured effect, the cohort retention curves, and the honest account of what is working and what is not. A record that reports only the flattering aggregate is a defect. Pair every retention figure with its segment and cohort, and state what the metrics cannot tell you — the small sample, the seasonality, the definition that changed.

Primary sources: <https://en.wikipedia.org/wiki/Churn_rate> and <https://en.wikipedia.org/wiki/Customer_retention>.

Distinguish leading from lagging indicators. NRR and GRR are lagging: they tell you what already happened. Leading indicators — adoption trend, health-score movement, champion engagement — tell you what is about to happen and give you time to act. A useful record carries both, so the team can see the coming quarter, not only the last one.

## Decision rules

- Report GRR, NRR, and logo retention together, not NRR alone.
- GRR exposes churn and contraction without expansion masking it.
- NRR above 100% must be decomposed into expansion, contraction, churn.
- Pair every retention figure with its segment and cohort.
- Record per-account outcome, health, and playbook effect.
- State what the metrics cannot tell you: samples, seasonality, definition changes.

## Procedure

1. Define GRR, NRR, and logo retention precisely.
2. Compute each by segment and cohort.
3. Decompose NRR into expansion, contraction, and churn.
4. Record per-account outcome, health, and playbook effect.
5. Build cohort retention curves and review them.
6. Publish the record with its limitations named.

## Anti-patterns

- Reporting NRR alone to flatter the base.
- No decomposition of NRR into its components.
- Aggregates without segment or cohort.
- A record with only successes and no churned analysis.
- Metrics whose definitions quietly change between periods.

## Done checklist

- [ ] GRR, NRR, logo retention defined and reported together.
- [ ] NRR decomposed into expansion, contraction, churn.
- [ ] Figures broken out by segment and cohort.
- [ ] Per-account outcome and playbook effect recorded.
- [ ] Cohort retention curves reviewed.
- [ ] Limitations named in the record.

## Sources

- Churn rate: <https://en.wikipedia.org/wiki/Churn_rate>
- Customer retention: <https://en.wikipedia.org/wiki/Customer_retention>
- Customer lifetime value: <https://en.wikipedia.org/wiki/Customer_lifetime_value>
