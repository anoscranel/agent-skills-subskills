---
name: operationalising-and-measuring-intel
domain: security-hardening/operationalising-intel
trigger: "Turning intelligence into defence and measuring its value."
anti_trigger: "Not for producing intelligence, and not for SOC staffing."
scope: "Turning intel into defence and measuring value."
status: seedling
---

# Operationalising and measuring intelligence

## Standard

Intelligence earns its cost only when it changes a defensive outcome. Operationalising means routing the product to the control that can act: indicators to blocking and detection, TTPs to behavioural detections and hunt hypotheses, actor and campaign context to risk and patching prioritisation, strategic assessments to leadership decisions. Each PIR should map to the control or decision it informs, so the path from intelligence to effect is explicit rather than hoped for.

Measuring the function is what separates it from a reporting mill. The honest metrics are about effect, not volume: detections built or improved from intelligence, incidents detected earlier, hunts that found something, decisions that changed, false-positive rate of intelligence-driven blocking. A feedback loop carries these results back to the requirements, so collection and analysis re-aim at what actually changed outcomes. Intelligence that produces no measurable defensive effect is re-scoped or stopped, however elegant the analysis.

Primary sources: <https://attack.mitre.org/> and <https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html>.

## Decision rules

- Map each PIR to the control or decision it informs.
- Route product to the control that can act on it, not just to a mailing list.
- Measure effect: detections built, earlier detection, hunts landed, decisions changed.
- Track the false-positive cost of intelligence-driven blocking.
- Feed results back to requirements; stop intelligence with no measurable effect.

## Procedure

1. Map each PIR to its consuming control or decision.
2. Deliver indicators and TTPs to detection and hunting with context.
3. Deliver strategic assessments to the decisions they inform.
4. Measure detections, detection lead time, hunt yield and decision impact.
5. Measure false positives from intelligence-driven controls.
6. Feed the effect data back; re-aim or retire low-value requirements.

## Anti-patterns

- Intelligence delivered to a distribution list with no owning control.
- Measuring success in reports produced or indicators shipped.
- No feedback loop from outcomes to requirements.
- Blocking on intelligence without watching false positives.
- Continuing a requirement that has never changed a decision.

## Done checklist

- [ ] PIRs mapped to consuming controls or decisions.
- [ ] Product routed to the acting control with context.
- [ ] Effect measured: detections, lead time, hunt yield, decisions.
- [ ] False-positive cost tracked.
- [ ] Low-value requirements re-aimed or retired.

Attribution of effect needs care too: an incident detected earlier is not automatically the intelligence team's win, since detection rules, telemetry and the responder all contributed. Record the contribution honestly, crediting the intelligence where it supplied the decisive context and not where it merely existed in the background.

## Sources

- ATT&CK for detection and hunting: <https://attack.mitre.org/>
- Pyramid of Pain for durable detection: <https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html>
- Threat intelligence value: <https://en.wikipedia.org/wiki/Cyber_threat_intelligence>
