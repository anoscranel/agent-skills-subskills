---
name: quantization
domain: software-engineering/quantization
trigger: "Lowering a model's weight precision to shrink size and cost."
anti_trigger: "Not for serving KV-cache, and not for training-aware weight updates in general."
scope: "Lowering weight precision: PTQ, QAT, GPTQ, AWQ, GGUF."
status: seedling
---

# Quantization

## Standard

Quantization stores weights in fewer bits: FP32 or FP16 down to INT8, INT4, or lower. Size falls roughly with bit-width, and on supported hardware inference gets faster and cheaper. The quality cost is small at INT8, noticeable at INT4, and often severe below it. Two families exist. Post-training quantization (PTQ) converts a trained model with no retraining, using a small calibration set to estimate activation ranges; it is cheap and fast. Quantization-aware training (QAT) simulates low precision during further training so the model adapts to it; it costs training time but preserves quality at aggressive bit-widths.

The modern LLM schemes differ in what they protect. GPTQ quantizes weights layer by layer using approximate second-order (Hessian) information to compensate for the error each rounding introduces, reaching INT4 and INT3 with small degradation. AWQ observes that a small fraction of weights are salient because activations amplify them, and protects those by per-channel scaling rather than rounding them naively. GGUF is the file format used by llama.cpp to ship quantized models for CPU and edge inference, with named levels trading size against quality. Granularity matters: per-channel scales preserve more accuracy than per-tensor, at a small metadata cost.

Primary sources: <https://arxiv.org/abs/2210.17323> and <https://arxiv.org/abs/2306.00978>.

## Decision rules

- Choose PTQ for speed and no retraining; QAT when aggressive bit-widths must keep quality.
- INT8 is near-lossless; INT4 is the usual floor for LLMs; below INT4 expect real degradation.
- Use GPTQ or AWQ for LLM weight-only PTQ; GGUF for CPU and edge deployment.
- Calibrate on data that represents real inputs; a skewed calibration set skews the ranges.
- Prefer per-channel granularity when the quality budget is tight.
- Measure quality and latency on the target device, not on the development machine.

## Procedure

1. Fix the bit-width target from the size and quality budgets.
2. Choose PTQ or QAT, then the scheme (GPTQ, AWQ, or a GGUF level for edge).
3. Assemble a representative calibration set; keep it disjoint from the eval set.
4. Quantize, keeping an unquantized copy as the baseline.
5. Evaluate quality and measure latency and memory on the target device.
6. Record the scheme, bit-width, calibration set, and measured deltas.

## Anti-patterns

- Quantizing to INT2 or INT1 and being surprised by the accuracy collapse.
- Calibrating on the eval set, contaminating the quality measurement.
- Per-tensor scales when per-channel would have saved the quality budget.
- Assuming smaller weights guarantee faster inference on any hardware.
- Deleting the unquantized baseline, so no regression comparison is possible.

## Done checklist

- [ ] Bit-width chosen from the size and quality budgets.
- [ ] PTQ/QAT and scheme selected and justified.
- [ ] Calibration set representative and disjoint from eval.
- [ ] Baseline kept for comparison.
- [ ] Quality, latency, and memory measured on target.
- [ ] Scheme, calibration, and deltas recorded.

## Sources

- GPTQ: <https://arxiv.org/abs/2210.17323> · implementation: <https://github.com/IST-DASLab/gptq>
- AWQ: <https://arxiv.org/abs/2306.00978> · implementation: <https://github.com/mit-han-lab/llm-awq>
- GGUF and llama.cpp for edge inference: <https://github.com/ggml-org/llama.cpp>
- Quantization-aware training in PyTorch: <https://pytorch.org/docs/stable/quantization.html>
