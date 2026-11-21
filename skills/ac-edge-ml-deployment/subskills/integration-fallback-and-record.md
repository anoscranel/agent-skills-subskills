---
name: integration-fallback-and-record
domain: software-engineering/integration-fallback-and-record
trigger: "Wiring cloud fallback, model updates, and the deployment record."
anti_trigger: "Not for the on-device decision itself, and not for app release mechanics."
scope: "Cloud fallback, model updates, and the record."
status: seedling
---

# Integration, fallback and record

## Standard

No single on-device configuration covers the installed base, so the deployment is a routing problem. Some devices lack the accelerator or the op support, some are too slow, and some inputs are too hard for the small on-device model. A deliberate fallback decides per request whether to run on-device or call the cloud, based on capability detection, measured speed, or a confidence signal from the on-device model. The fallback is a feature, not a failure: it is what lets the on-device path serve the common case without stranding the rest.

Model updates are the other recurring concern. An on-device model is a shipped artifact with its own version, and updating it means delivering a new file to installed clients, keeping the format and runtime compatible, and being able to roll back. The record ties it together: the model and converter versions, the target formats and backends, the measured latency, memory and battery per device tier, the fallback rule, and the limitations — which devices fall back, and where quality is known to be worse. A deployment without that record cannot be maintained, because the next update cannot tell what will break.

Primary sources: <https://onnxruntime.ai/docs/> and <https://www.tensorflow.org/lite/guide>.

## Decision rules

- Define the fallback trigger explicitly: capability, measured speed, or model confidence.
- Detect device capability at runtime rather than hardcoding a device list.
- Version the on-device model and deliver updates with rollback capability.
- Keep format and runtime compatibility across model updates.
- Record model and converter versions, backends, measurements, fallback rule and limitations.
- Name which devices fall back and where quality is known to be worse.

## Procedure

1. Implement runtime capability detection for backend and op support.
2. Wire the fallback rule: on-device when capable and fast enough, cloud otherwise.
3. Package the model as a versioned artifact with an update channel.
4. Test update and rollback across the supported device tiers.
5. Record versions, measurements, the fallback rule and limitations.
6. Re-run the measurement set after each model or runtime update.

## Anti-patterns

- Hardcoding a device allowlist that ages into wrong routing decisions.
- No fallback, so unsupported devices get a broken or absent feature.
- Shipping a model update with no rollback.
- Updating the model without re-measuring on real devices.
- A record that omits which devices fall back and where quality is worse.

## Done checklist

- [ ] Fallback trigger defined and implemented.
- [ ] Capability detected at runtime.
- [ ] Model versioned with update and rollback.
- [ ] Compatibility maintained across updates.
- [ ] Record includes versions, measurements, fallback and limitations.
- [ ] Measurements re-run after each update.

## Sources

- ONNX Runtime documentation: <https://onnxruntime.ai/docs/>
- TensorFlow Lite guide: <https://www.tensorflow.org/lite/guide>
- ONNX Runtime Web and fallback patterns: <https://onnxruntime.ai/docs/tutorials/web/>
