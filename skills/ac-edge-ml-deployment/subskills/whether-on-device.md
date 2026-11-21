---
name: whether-on-device
domain: software-engineering/whether-on-device
trigger: "Deciding whether a feature runs on-device or in the cloud."
anti_trigger: "Not for shrinking the model, and not for server-side serving."
scope: "The on-device-versus-cloud decision, in numbers."
status: seedling
---

# Whether on-device

## Standard

On-device inference is chosen for four reasons, and each must be true of the feature, not aspirational. Privacy: data never leaves the device, which matters for sensitive inputs and some regulations. Latency: no network round trip, so the result is available even on a dead connection and without queueing. Offline: the feature works with no connectivity at all. Cost: inference moves from a metered server to hardware the user already owns, which changes the economics at scale. If none of these binds, the cloud is usually simpler, and a larger model is available there.

The counterweight is capability. A device has a fixed compute, memory and power budget, and the model that fits may be a smaller or more heavily compressed one with worse quality. The decision is therefore made in numbers: the quality the feature needs, the latency budget, the device tier that must be supported, and the cost per inference at the expected volume. A hybrid is often the real answer — on-device for the common case, cloud for the hard case — and choosing that split is part of this decision, not an afterthought.

Primary sources: <https://arxiv.org/abs/2106.08962> and <https://www.tensorflow.org/lite/guide>.

## Decision rules

- Name which of privacy, latency, offline or cost actually binds; if none binds, default to cloud.
- State the quality floor, latency budget and minimum device tier before choosing.
- Compare the on-device model quality against the cloud model, not against an ideal.
- Cost the decision at expected volume: server cost per inference versus development and support cost of on-device.
- Consider the hybrid split explicitly: on-device common case, cloud hard case.
- Decide by the weakest device that must be supported, not the flagship.

## Procedure

1. Write the feature's quality floor, latency budget and offline requirement.
2. List the device tiers in the installed base that must be supported.
3. Check whether a model meeting the quality floor fits the weakest tier.
4. Estimate per-inference cloud cost at volume versus on-device engineering cost.
5. Choose on-device, cloud, or a stated hybrid split, with the binding reason recorded.
6. Record the decision and the numbers that drove it.

## Anti-patterns

- Choosing on-device for the marketing claim of privacy when the data is not sensitive.
- Assuming the on-device model matches cloud quality without measuring.
- Benchmarking only on a flagship and shipping to low-tier devices.
- Ignoring the engineering and maintenance cost of supporting many device variants.
- Treating on-device versus cloud as binary when a hybrid is cheaper and better.

## Done checklist

- [ ] Binding reason named.
- [ ] Quality floor, latency budget and device tiers stated.
- [ ] On-device quality compared against cloud.
- [ ] Volume cost estimated both ways.
- [ ] Hybrid split considered and decided.
- [ ] Decision and numbers recorded.

## Sources

- Efficient deep learning survey (Menghani): <https://arxiv.org/abs/2106.08962>
- TensorFlow Lite guide: <https://www.tensorflow.org/lite/guide>
- ONNX Runtime documentation: <https://onnxruntime.ai/docs/>
