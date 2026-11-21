---
name: product-metrics-and-north-star
domain: software-engineering/product-metrics-and-north-star
trigger: "Defining product success metrics, a north-star metric, or a measurement framework."
anti_trigger: "Not for event instrumentation, and not for statistical experiment analysis."
scope: "North-star metric, input metrics, and success criteria."
status: seedling
---

# Product metrics and north star

## Standard

A north-star metric is the single measure that best captures the value the product delivers to customers, and it aligns the team on what success means. It is chosen because moving it reflects real customer value, not because it is easy to move, and it is supported by a small set of input metrics the team can influence directly. The discipline is to measure value delivered, not activity produced.

The supporting framework keeps the metric honest. The HEART framework organises measures into happiness, engagement, adoption, retention, and task success, so a single number never stands alone. Input metrics decompose the north star into the levers the team controls. Vanity metrics — total registered users, raw page views — are rejected because they only go up and say nothing about value, and every metric is paired with the guardrail that stops it being gamed.

Primary sources: <https://amplitude.com/books/north-star> and <https://research.google/pubs/pub36299/>.

## Decision rules

- Choose a north-star metric that captures customer value delivered, not team activity.
- Decompose it into a small set of input metrics the team can directly influence.
- Use HEART to balance happiness, engagement, adoption, retention, and task success.
- Reject vanity metrics that only rise and reveal nothing about value.
- Pair each metric with a guardrail that prevents gaming it.
- Set success criteria before work begins, so results can be judged honestly.

## Procedure

1. State the value the product delivers to customers in one sentence.
2. Choose the north-star metric that best captures that value.
3. Decompose it into the input metrics the team can move.
4. Balance the set with HEART dimensions and guardrail metrics.
5. Define success criteria and targets before the work starts.
6. Review the metrics on a cadence and replace any that are being gamed.

## Anti-patterns

- A north-star metric that measures output rather than customer value.
- Optimising a metric while the guardrails quietly degrade.
- Reporting vanity metrics because they always look good.
- Too many top-level metrics, so nothing is actually prioritised.
- Setting success criteria after seeing the results.

## Done checklist

- [ ] North-star metric captures customer value.
- [ ] Input metrics identified and influenceable.
- [ ] HEART dimensions and guardrails balanced.
- [ ] Vanity metrics rejected.
- [ ] Success criteria set before work begins.
- [ ] Metric review cadence and replacement rule stated.

## Sources

- Amplitude, the North Star Playbook: <https://amplitude.com/books/north-star>
- Google Research, the HEART framework for user-centred metrics: <https://research.google/pubs/pub36299/>
- Kano model, satisfaction and measurement: <https://en.wikipedia.org/wiki/Kano_model>
