---
name: whether-privacy-preserving-ml
domain: software-engineering/whether-privacy-preserving-ml
trigger: "Deciding whether a model needs a formal privacy guarantee and which mechanism."
anti_trigger: "Not for data governance duties, and not for general pipeline design."
scope: "Deciding a formal guarantee is needed and which."
status: seedling
---

# Whether privacy-preserving ML

## Standard

The decision to apply a formal privacy mechanism starts from a named requirement, not from anxiety. The requirement is a sentence of the form: an adversary with this capability must not learn this fact about this individual. Everything downstream follows from how precise that sentence is. "We should be private" is not a requirement; "a user querying the model must not be able to tell whether a specific patient's record was in training" is.

Three questions select the mechanism. Where does the data live — centralised, or distributed across clients that cannot share it? Who is the adversary — an outside querier, the server itself, another client, or someone with the released model? And what utility can be sacrificed — how much accuracy, calibration, or fairness is the privacy guarantee allowed to cost? The answers distinguish differential privacy (bounding what one individual's inclusion reveals) from federation (keeping data decentralised) from cryptographic computation (hiding the update or input in transit). These compose but are not interchangeable.

Primary sources: <https://arxiv.org/abs/1912.04977> and <https://arxiv.org/abs/1607.00133>.

## Decision rules

- Write the requirement as adversary-capability plus protected-fact before choosing a mechanism.
- Anonymisation and aggregation are not guarantees; require a formal bound when the fact is sensitive.
- Choose by adversary: outside querier and released model point to differential privacy; an honest-but-curious server points to secure aggregation or cryptographic compute.
- Federation answers data locality, not leakage; never treat it as a privacy guarantee alone.
- State the acceptable utility cost up front, because every formal mechanism trades accuracy for the bound.
- When the threat model is undefined, stop and define it; a guarantee without an adversary is decoration.

## Procedure

1. Name the protected fact and the individual it concerns.
2. Enumerate adversaries and their capabilities (query access, model access, server, other clients).
3. Map each adversary to the mechanism that bounds it.
4. Estimate the utility budget the task can surrender.
5. Confirm the data-locality constraint (centralised versus federated).
6. Record the chosen guarantee and its adversary coverage in the privacy record.

## Anti-patterns

- "We aggregate the data, so it is anonymous."
- Choosing differential privacy when the adversary is the server holding raw data.
- Federating and declaring privacy without any bound on update leakage.
- Adopting a mechanism because it is fashionable, with no protected fact named.
- Ignoring the utility cost until after the model is trained and degraded.

## Done checklist

- [ ] Protected fact and individual named.
- [ ] Adversaries and capabilities enumerated.
- [ ] Mechanism mapped to each adversary.
- [ ] Utility budget stated before training.
- [ ] Data-locality constraint recorded.
- [ ] Guarantee and its coverage written into the record.

## Sources

- Advances and Open Problems in Federated Learning: <https://arxiv.org/abs/1912.04977>
- Deep Learning with Differential Privacy: <https://arxiv.org/abs/1607.00133>
- Differential privacy overview: <https://en.wikipedia.org/wiki/Differential_privacy>
