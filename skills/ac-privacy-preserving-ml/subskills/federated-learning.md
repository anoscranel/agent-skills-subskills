---
name: federated-learning
domain: software-engineering/federated-learning
trigger: "Training across decentralised clients whose data cannot be centralised."
anti_trigger: "Not for DP accounting, and not for secure aggregation transport."
scope: "FedAvg, client sampling, non-IID drift, rounds."
status: seedling
---

# Federated learning

## Standard

Federated learning trains a shared model without centralising raw data. In the canonical FedAvg round, the server sends the current global weights to a sampled subset of clients, each client performs several local epochs on its own data, and the server averages the resulting updates weighted by each client's example count. Raw data never leaves the device; only model updates travel. The result is a locality guarantee, not a privacy guarantee, and the distinction is the single most important thing to hold onto.

Two properties define the setting and its difficulty. Clients are non-IID: each holds data drawn from a different distribution, so local updates pull in conflicting directions and the global model can drift or diverge. Clients are also unreliable: they drop out, arrive late, and hold wildly different example counts, so weighted averaging and straggler handling are first-order concerns. Cross-silo federation (a handful of stable institutions) tolerates more local epochs and larger fractions per round; cross-device federation (millions of flaky phones) demands small client fractions, few local epochs, and aggressive dropout tolerance.

Primary sources: <https://arxiv.org/abs/1602.05629> and <https://arxiv.org/abs/1912.04977>.

## Decision rules

- State plainly that federation is a locality property; pair it with DP or secure aggregation for privacy.
- Weight the server average by client example count, not by client count.
- Tune local epochs against non-IID drift: more local work speeds convergence on IID data and destabilises non-IID data.
- Sample a client fraction per round and tolerate dropout; do not require full participation.
- Choose cross-silo versus cross-device settings deliberately; they have opposite stability profiles.
- Measure global-model accuracy per client distribution, not just the pooled average.

## Procedure

1. Classify the deployment as cross-silo or cross-device.
2. Set the client fraction, local epochs, and local batch size.
3. Initialise global weights and run a FedAvg round with weighted averaging.
4. Handle stragglers and dropouts with timeouts and partial-round acceptance.
5. Evaluate accuracy per client distribution and watch for non-IID drift.
6. Record rounds, fraction, local epochs, and the per-distribution accuracy spread.

## Anti-patterns

- Calling a federated model private because raw data stayed on device.
- Averaging updates by client count when example counts differ by orders of magnitude.
- Many local epochs on highly non-IID clients, then blaming the optimizer for divergence.
- Requiring every sampled client to return before the round can close.
- Reporting only pooled accuracy while some client distributions collapse.

## Done checklist

- [ ] Cross-silo versus cross-device classified.
- [ ] Locality-versus-privacy distinction stated.
- [ ] Weighted averaging by example count.
- [ ] Local epochs tuned against non-IID drift.
- [ ] Dropout and straggler handling configured.
- [ ] Per-distribution accuracy recorded.

## Sources

- Communication-Efficient Learning of Deep Networks from Decentralized Data (FedAvg): <https://arxiv.org/abs/1602.05629>
- Advances and Open Problems in Federated Learning: <https://arxiv.org/abs/1912.04977>
- TensorFlow Federated: <https://www.tensorflow.org/federated>
- Federated learning overview: <https://en.wikipedia.org/wiki/Federated_learning>
