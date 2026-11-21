---
name: runtimes-and-delegates
domain: software-engineering/runtimes-and-delegates
trigger: "Choosing the runtime and hardware backend that executes the model."
anti_trigger: "Not for writing kernels, and not for format conversion."
scope: "CPU, GPU, NPU backends and execution providers."
status: seedling
---

# Runtimes and delegates

## Standard

The runtime executes the graph; the delegate or execution provider decides which hardware runs each op. On Android, NNAPI routes supported ops to a neural accelerator, GPU or DSP, with CPU as the fallback. On Apple devices, CoreML schedules across CPU, GPU and the Neural Engine. TensorFlow Lite offers delegates for GPU and accelerators, and ONNX Runtime offers execution providers per platform. The choice is per model and per device, not global: a backend that accelerates one op may not support another, and unsupported ops fall back to CPU mid-graph.

The performance reality is that a delegate existing is not a delegate helping. Accelerator wins are largest for the ops they are designed for, and the transfer cost of moving tensors between CPU and an accelerator can erase the gain when ops alternate between backends. The honest approach is to measure end-to-end latency per candidate backend on the target device, including any fallback segments, and to prefer the configuration that is fastest for the whole graph, not the one with the most impressive name.

Primary sources: <https://developer.android.com/ndk/guides/neuralnetworks> and <https://www.tensorflow.org/lite/performance/delegates>.

## Decision rules

- Select the backend per model and per device, from measurement, not from the accelerator's reputation.
- Check which ops the delegate supports; unsupported ops fall back, often to CPU.
- Count backend-switch transfer cost when ops alternate between CPU and accelerator.
- Measure end-to-end latency for the whole graph per candidate, including fallback segments.
- Keep a CPU fallback path for devices lacking the accelerator or the op support.
- Record the chosen backend per device tier and the measured basis for the choice.

## Procedure

1. Enumerate candidate runtimes and delegates for the target device.
2. Check op coverage for each candidate against the model.
3. Measure whole-graph latency per candidate on the real device.
4. Inspect where ops actually ran and where fallbacks occurred.
5. Choose the fastest whole-graph configuration with a CPU fallback.
6. Record the selection and the measurements per device tier.

## Anti-patterns

- Assuming the neural accelerator is always faster than the GPU or CPU.
- Ignoring CPU fallback segments that dominate the latency.
- Quoting a single-op benchmark as end-to-end performance.
- No fallback path on devices without the accelerator.
- Selecting a delegate once and never re-measuring after a model or OS change.

## Done checklist

- [ ] Candidates enumerated per device.
- [ ] Op coverage checked.
- [ ] Whole-graph latency measured per candidate.
- [ ] Fallback segments inspected.
- [ ] CPU fallback path present.
- [ ] Selection and measurements recorded per tier.

## Sources

- Android Neural Networks API: <https://developer.android.com/ndk/guides/neuralnetworks>
- TensorFlow Lite delegates: <https://www.tensorflow.org/lite/performance/delegates>
- Apple CoreML framework: <https://developer.apple.com/documentation/coreml>
