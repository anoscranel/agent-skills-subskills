---
name: ac-privacy-preserving-ml
description: 'Training and deploying ML under a formal privacy guarantee: differential privacy and its epsilon-delta budget, DP-SGD with per-example gradient clipping and calibrated noise, federated learning across decentralised clients, secure aggregation and cryptographic computation, and the privacy-versus-utility accounting that proves the guarantee costs what you can afford. It covers when a guarantee is warranted, the mechanisms, and the written record; it never claims privacy from architecture alone and never treats a model as anonymised because it was aggregated. Use when asking "differential privacy", "DP-SGD", "epsilon delta budget", "federated learning", "FedAvg", "secure aggregation", "homomorphic encryption for ML", "privacy-preserving machine learning", "membership inference defence". Not for data governance and GDPR duties (ac-privacy-engineering), not for ML pipelines and drift (ac-ml-systems-practice), not for adapting weights (ac-model-fine-tuning), not for application hardening (ac-security-engineer).'
license: MIT
metadata:
  domain: software-engineering
status: seedling
---

# Privacy-preserving ML

## Overview

Some models must learn from data that cannot be exposed: medical records, typing behaviour, financial histories. The instinct is to aggregate or anonymise and call it private, and that instinct fails — gradients memorise, aggregates leak individuals, and a released model can be interrogated into revealing its training examples. Formal privacy guarantees exist precisely because intuition about leakage is unreliable.

This skill owns the craft of training and deploying models under a stated, measurable privacy guarantee. Its neighbours carve the rest: ac-privacy-engineering owns data governance and legal duties; ac-ml-systems-practice owns the pipeline; ac-model-fine-tuning owns adapting weights; ac-security-engineer owns application hardening. The unit here is the guarantee: a differential-privacy budget, a federation protocol, a cryptographic wrapper, each with a known cost in utility and a known residual risk.

Primary sources: <https://arxiv.org/abs/1607.00133> and <https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf>.

## When to use

- When a model trains on data that must not be reconstructable from the model or its updates.
- When a privacy budget (epsilon, delta) must be chosen, spent, and accounted.
- When training is federated across clients whose data cannot be centralised.
- When a formal guarantee, not an assertion of safety, is the deliverable.

## When NOT to use

- For data retention, subject rights, and GDPR duties (use ac-privacy-engineering).
- For general ML pipeline hygiene and drift (use ac-ml-systems-practice).
- For adapting model weights (use ac-model-fine-tuning).
- For application security controls (use ac-security-engineer).

## Subskill Index

| Leaf | Domain segment | Scope (one line) |
|---|---|---|
| `subskills/whether-privacy-preserving-ml.md` | `software-engineering/whether-privacy-preserving-ml` | Deciding a formal guarantee is needed and which. |
| `subskills/differential-privacy-foundations.md` | `software-engineering/differential-privacy-foundations` | The epsilon-delta guarantee and its composition. |
| `subskills/dp-sgd-and-training.md` | `software-engineering/dp-sgd-and-training` | Per-example clipping, calibrated noise, the accountant. |
| `subskills/federated-learning.md` | `software-engineering/federated-learning` | FedAvg, client sampling, non-IID drift, rounds. |
| `subskills/secure-aggregation-and-compute.md` | `software-engineering/secure-aggregation-and-compute` | Secure aggregation, homomorphic encryption, MPC. |
| `subskills/privacy-utility-and-evaluation.md` | `software-engineering/privacy-utility-and-evaluation` | Measuring what the guarantee costs and whether it holds. |
| `subskills/privacy-ml-record.md` | `software-engineering/privacy-ml-record` | The written record: threat model, budget, cost, residuals. |

## Status and honest limits

A formal guarantee bounds a defined leakage, not every leakage. Differential privacy bounds what one individual's inclusion reveals; it does not stop a model from learning population-level facts, does not anonymise the training data retroactively, and does not protect against a compromised client or a poisoned update. Federation reduces centralisation but does not by itself guarantee privacy — updates still leak. A privacy budget spent without an accountant is an assertion, not a guarantee. Nothing here certifies a deployment as safe; the record must name what the guarantee does not cover.
