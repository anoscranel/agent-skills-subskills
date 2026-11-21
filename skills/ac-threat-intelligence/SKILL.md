---
name: ac-threat-intelligence
description: 'Producing and using cyber threat intelligence: priority intelligence requirements and the intelligence cycle, collection and source evaluation, indicators of compromise and the Pyramid of Pain, analytic models (kill chain, Diamond Model, MITRE ATT&CK), attribution and campaign tracking with honest confidence, sharing standards (STIX, TAXII, TLP), and turning intelligence into detection with measured value. It builds the intelligence product; it never asserts attribution as fact and never treats an indicator feed as intelligence. Use when asking "threat intelligence", "CTI", "IOC", "Pyramid of Pain", "MITRE ATT&CK mapping", "kill chain", "threat actor attribution", "STIX TAXII", "intelligence requirements", "OSINT collection". Not for running the SOC, detection engineering or threat hunting (ac-security-operations), not for hardening systems (ac-security-engineer), not for which security standard applies (ac-security-standards).'
license: MIT
metadata:
  domain: security-hardening
status: seedling
---

# Threat intelligence

## Overview

Threat intelligence is analysed, contextualised information about threats that a decision-maker can act on. An indicator feed is not intelligence: a list of bad IPs becomes intelligence only when it answers a question someone actually asked, with the confidence and the caveats attached. The craft runs the intelligence cycle — direction, collection, processing, analysis, dissemination, feedback — and its discipline is separating what is observed from what is inferred, and what is inferred from what is assumed.

This skill owns the production and use of the intelligence product: defining requirements, collecting and evaluating sources, working indicators and frameworks, tracking actors with honest confidence, sharing under handling rules, and proving the intelligence changed a defensive outcome. Its neighbours: ac-security-operations runs the SOC, detection engineering and threat hunting that consume intelligence; ac-security-engineer hardens systems; ac-security-standards maps which standard applies.

Primary sources: <https://en.wikipedia.org/wiki/Cyber_threat_intelligence> and <https://attack.mitre.org/>.

## When to use

- Standing up a threat-intelligence function or priority intelligence requirements.
- Evaluating collection sources and indicator feeds.
- Applying kill chain, Diamond Model or ATT&CK to a threat.
- Tracking a threat actor or campaign with calibrated confidence.
- Sharing intelligence under STIX/TAXII and handling labels.

## When NOT to use

- For SOC operations, detection rules or threat hunting (use ac-security-operations).
- For hardening a system or reviewing code (use ac-security-engineer).
- For choosing a security standard or its edition (use ac-security-standards).

## Subskill Index

| Leaf | Domain segment | Scope (one line) |
|---|---|---|
| `subskills/intelligence-requirements-and-cycle.md` | `security-hardening/intelligence-requirements` | Requirements and the intelligence cycle. |
| `subskills/collection-and-source-evaluation.md` | `security-hardening/collection-and-sources` | Collection channels and source reliability. |
| `subskills/indicators-and-pyramid-of-pain.md` | `security-hardening/indicators-and-ttp` | IOCs, TTPs and the Pyramid of Pain. |
| `subskills/analysis-models-and-frameworks.md` | `security-hardening/analysis-frameworks` | Kill chain, Diamond Model, ATT&CK. |
| `subskills/attribution-and-campaign-tracking.md` | `security-hardening/attribution-and-campaigns` | Actor and campaign tracking with confidence. |
| `subskills/sharing-standards-and-handling.md` | `security-hardening/sharing-and-handling` | STIX, TAXII and handling labels. |
| `subskills/operationalising-and-measuring-intel.md` | `security-hardening/operationalising-intel` | Turning intel into defence and measuring value. |

## Status and honest limits

Attribution is an assessment, not a fact; the strongest honest product states confidence, alternatives and disconfirming evidence rather than a name. Indicators decay fast and feed-driven blocking generates false positives that hurt the business more than the adversary. Intelligence that never reaches a decision-maker, or that no one can act on, is overhead regardless of its quality — the measure of the function is decisions changed, not reports produced. Nothing here replaces the defensive controls that act on the intelligence.
