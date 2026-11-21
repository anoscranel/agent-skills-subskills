---
name: privacy-ml-record
domain: software-engineering/privacy-ml-record
trigger: "Writing the record of a privacy-preserving training or deployment."
anti_trigger: "Not for the mechanisms themselves, and not for legal compliance sign-off."
scope: "The written record: threat model, budget, cost, residuals."
status: seedling
---

# Privacy-ML record

## Standard

The privacy record is what separates a guarantee from a claim. It documents the threat model (the protected fact, the individuals concerned, and each adversary with its capabilities), the guarantee chosen and its exact parameters, the mechanism that delivers it, the accountant's output, the measured utility cost, and the residual risks the guarantee does not address. A deployment that cannot produce this record does not have a verifiable guarantee; it has an intention.

The record is a living artifact tied to the model version. Every retraining spends fresh privacy, so the record carries a cumulative ledger: each release's epsilon and delta, composed against everything released before it. It also names the unit of privacy (record, user, or group), because "user-level DP" and "record-level DP" are different promises with different costs. And it states plainly what is not covered — population-level facts the model legitimately learned, side channels outside the mechanism, a malicious or compromised client, and the possibility that the implementation diverged from the design. Naming the limits is not weakness; it is the difference between an honest guarantee and marketing.

Primary sources: <https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf> and <https://arxiv.org/abs/1912.04977>.

## Decision rules

- Record the threat model first: protected fact, individuals, adversaries, capabilities.
- State the guarantee with exact parameters and the privacy unit.
- Attach the accountant output and the mechanism settings, not just the epsilon.
- Keep a cumulative composed budget across every release.
- Record the measured utility cost and the attack-evaluation results.
- Name the residual risks and what the guarantee does not cover.

## Procedure

1. Write the threat model and the privacy unit.
2. Record the guarantee and its parameters with the mechanism settings.
3. Attach the accountant output and the clipping, noise, and sampling configuration.
4. Log the composed epsilon and delta against all prior releases.
5. Attach the utility-delta and attack-evaluation results.
6. List residual risks and the guarantee's exclusions; version the record with the model.

## Anti-patterns

- An epsilon quoted with no accountant, settings, or privacy unit.
- A fresh budget per release with no composition against earlier ones.
- A record that lists protections but no residual risks.
- Treating the record as a one-time form rather than a per-version ledger.
- A guarantee asserted in prose that the implementation never realised.

## Done checklist

- [ ] Threat model and privacy unit recorded.
- [ ] Guarantee, parameters, and mechanism settings attached.
- [ ] Accountant output and full configuration present.
- [ ] Cumulative composed budget across releases.
- [ ] Utility cost and attack results attached.
- [ ] Residual risks and exclusions named; record versioned with the model.

## Sources

- The Algorithmic Foundations of Differential Privacy: <https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf>
- Advances and Open Problems in Federated Learning: <https://arxiv.org/abs/1912.04977>
- Differential privacy overview: <https://en.wikipedia.org/wiki/Differential_privacy>
