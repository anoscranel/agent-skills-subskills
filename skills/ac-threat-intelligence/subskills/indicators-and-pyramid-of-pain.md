---
name: indicators-and-pyramid-of-pain
domain: security-hardening/indicators-and-ttp
trigger: "Working with IOCs and TTPs and their defensive value."
anti_trigger: "Not for detection-rule authoring, and not for attribution."
scope: "IOCs, TTPs and the Pyramid of Pain."
status: seedling
---

# Indicators and the Pyramid of Pain

## Standard

An indicator of compromise (IOC) is an observable artefact — a hash, IP, domain, filename, mutex, registry key — that may signal an intrusion. A tactic, technique or procedure (TTP) is a description of behaviour. The distinction matters because they sit at different levels of the Pyramid of Pain, David Bianco's model of how much it costs an adversary to change what you detect. Hash values and IPs are trivial to change; domains are easy; host and network artefacts are annoying; tools are harder; TTPs are most painful to abandon. Intelligence weighted toward the top of the pyramid forces the adversary to re-tool; intelligence weighted toward the bottom is re-issued by the adversary within hours.

The defensive implication is a portfolio. Low-level indicators are cheap to match and useful for immediate blocking, but they decay fast and generate false positives. Behavioural detections against TTPs cost more to build and survive longer. An intelligence product that only ever ships hashes and IPs keeps the defender permanently one step behind.

Primary sources: <https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html> and <https://en.wikipedia.org/wiki/Indicator_of_compromise>.

## Decision rules

- Classify every indicator by its pyramid level before relying on it.
- Prefer detections against TTPs and tooling for durable coverage.
- Track indicator shelf-life; retire indicators that have decayed.
- Assess false-positive cost before blocking on low-level indicators.
- Use low-level IOCs for triage and pivoting, not as the whole defence.

## Procedure

1. Extract indicators and behaviours from the intelligence.
2. Place each on the pyramid; note the expected adversary cost to change it.
3. Build durable detection from the higher levels where feasible.
4. Use low-level indicators for scoping and hunting with an expiry date.
5. Measure false positives and decay; retire stale indicators.
6. Re-balance the portfolio toward behavioural coverage over time.

## Anti-patterns

- Equating a large IOC feed with strong defence.
- Blocking on IPs with no false-positive or decay analysis.
- No expiry on low-level indicators.
- Ignoring TTPs because they are harder to operationalise.
- Treating an indicator match as proof of compromise.

## Done checklist

- [ ] Indicators classified by pyramid level.
- [ ] Durable behavioural detection built from higher levels.
- [ ] Low-level indicators carry expiry and FP assessment.
- [ ] Decay and false positives measured; stale items retired.
- [ ] Portfolio re-balanced toward behaviour.

It also pays to match the indicator to the response time available. Very low-level indicators suit automated, short-lived blocking close to the event, while higher-level behavioural detections suit the standing defensive posture that must still work next quarter. Confusing the two horizons leads either to brittle automation or to slow manual work on artefacts that have already changed.

## Sources

- The Pyramid of Pain: <https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html>
- Indicators of compromise: <https://en.wikipedia.org/wiki/Indicator_of_compromise>
- ATT&CK behaviours: <https://attack.mitre.org/>
