---
name: analysis-models-and-frameworks
domain: security-hardening/analysis-frameworks
trigger: "Structuring threat analysis with kill chain, Diamond Model or ATT&CK."
anti_trigger: "Not for collection, and not for detection coverage metrics."
scope: "Kill chain, Diamond Model, MITRE ATT&CK."
status: seedling
---

# Analysis models and frameworks

## Standard

Frameworks give raw observations a structure that supports reasoning and communication. Three do different jobs. The intrusion kill chain describes an attack as an ordered sequence — reconnaissance, weaponisation, delivery, exploitation, installation, command and control, actions on objectives — so a defender can identify where in the chain an intrusion sits and where it can be broken. The Diamond Model frames an intrusion event as a relationship among four features: adversary, capability, infrastructure and victim, letting the analyst pivot from one known feature to the others and to cluster events into activity threads. MITRE ATT&CK is a knowledge base of adversary tactics and techniques observed in the wild, giving a shared vocabulary to classify behaviour.

The discipline is to use the framework that answers the question, and to record the mapping, not to perform the mapping as an end in itself. A kill-chain placement that drives a defensive decision, a Diamond pivot that links two incidents into one campaign, an ATT&CK technique tag that lets detection be compared across tools — each earns its place. A beautifully labelled event that changed nothing is decoration.

Primary sources: <https://www.activeresponse.org/wp-content/uploads/2013/07/diamond.pdf> and <https://attack.mitre.org/>.

## Decision rules

- Use the kill chain to locate and break the attack phase.
- Use the Diamond Model to pivot across adversary, capability, infrastructure, victim.
- Use ATT&CK to classify behaviour in a shared technique vocabulary.
- Record the mapping and the decision it informs; do not map for its own sake.
- Keep framework labels consistent so events can be clustered and compared.

## Procedure

1. State the analytic question before choosing a framework.
2. Place the event in the kill chain to find the break point.
3. Build the Diamond event; pivot to related features and threads.
4. Tag behaviours with ATT&CK techniques.
5. Record the mapping and the defensive decision it supports.
6. Reuse consistent labels to cluster events into campaigns.

## Anti-patterns

- Applying every framework to every event regardless of value.
- Treating an ATT&CK tag as analysis rather than classification.
- Kill-chain labels with no decision attached.
- Inconsistent labelling that defeats clustering.
- Confusing a framework's vocabulary with evidence.

## Done checklist

- [ ] Analytic question stated; framework chosen to fit.
- [ ] Kill-chain phase and break point identified.
- [ ] Diamond event built and pivots explored.
- [ ] Behaviours tagged with ATT&CK techniques.
- [ ] Mapping recorded with the decision it informs.

## Sources

- The Diamond Model: <https://www.activeresponse.org/wp-content/uploads/2013/07/diamond.pdf>
- MITRE ATT&CK: <https://attack.mitre.org/>
- The intrusion kill chain: <https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html>
