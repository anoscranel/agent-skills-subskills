---
name: health-scores-and-monitoring
domain: software-engineering/health-scores-and-monitoring
trigger: "Scoring customer health and catching churn risk early."
anti_trigger: "Not for product analytics instrumentation, and not for support queues."
scope: "Health scores and early-warning signals."
status: seedling
---

# Health scores and monitoring

## Standard

A customer health score condenses the signals that predict whether a customer will renew into a single trackable indicator. It exists to surface risk early enough to act, not to produce a reassuring dashboard. Build it from signals that genuinely predict renewal: product usage depth and trend, adoption of the features that correlate with retention, support sentiment, engagement of the champion and the economic buyer, and commercial signals like payment behaviour.

The score is a model, not reality. A green score can hide a disengaged champion or a stakeholder who just left; a red score can punish a healthy customer with a seasonal usage dip. Weight the signals by their observed correlation with renewal, review the score's predictive accuracy against actual churn, and always let a human read the account behind the number. The point is the early-warning conversation, not the colour.

Primary sources: <https://en.wikipedia.org/wiki/Customer_success> and <https://en.wikipedia.org/wiki/Customer_relationship_management>.

Combine quantitative signals with qualitative ones. Usage data tells you what customers do; the CSM's account knowledge tells you why. A score built only on telemetry misses the reorg, the budget freeze, the champion who went quiet. Let the human update the score with context the data cannot see, and record that override so the model learns which signals it is missing.

## Decision rules

- Build the score from signals with observed correlation to renewal.
- Include usage depth and trend, not just logins.
- Include relationship signals: champion and economic-buyer engagement.
- Weight signals by predictive power, validated against actual churn.
- Treat the score as a trigger for a human conversation, not a verdict.
- Review and recalibrate the score against real outcomes.

## Procedure

1. List candidate signals and test their correlation with renewal.
2. Select the signals that genuinely predict retention.
3. Weight and combine them into a health score.
4. Set thresholds that trigger proactive outreach.
5. Validate the score against actual churn and retention.
6. Recalibrate on a cadence and record the changes.

## Anti-patterns

- A score built from whatever data is easiest to collect.
- Trusting the colour over the account behind it.
- No validation of the score against real churn.
- A score that never changes despite customer turnover.
- Treating a green score as proof the customer is safe.

## Done checklist

- [ ] Signals selected by observed correlation to renewal.
- [ ] Usage depth and trend included.
- [ ] Relationship and commercial signals included.
- [ ] Score validated against actual churn.
- [ ] Thresholds trigger proactive outreach.
- [ ] Recalibration cadence set.

## Sources

- Customer success: <https://en.wikipedia.org/wiki/Customer_success>
- Customer relationship management: <https://en.wikipedia.org/wiki/Customer_relationship_management>
- Churn rate: <https://en.wikipedia.org/wiki/Churn_rate>
