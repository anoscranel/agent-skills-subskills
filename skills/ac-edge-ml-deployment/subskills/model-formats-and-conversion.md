---
name: model-formats-and-conversion
domain: software-engineering/model-formats-and-conversion
trigger: "Converting a model to a deployable edge format."
anti_trigger: "Not for training the model, and not for choosing the hardware backend."
scope: "ONNX, TFLite, CoreML and conversion validation."
status: seedling
---

# Model formats and conversion

## Standard

The format is the contract between the trained model and the runtime that executes it. ONNX is the interchange format: a portable graph description that many runtimes accept, useful as the common intermediate and as the deployment format where ONNX Runtime runs. TFLite is the mobile and embedded format for TensorFlow Lite, and CoreML is Apple's format for its devices. The usual path is framework to ONNX to the target format, or framework directly to the target where a converter exists.

The trap is that conversion is not a lossless copy. Every runtime supports a subset of operators, and an unsupported op must be rewritten, replaced, or run on a fallback backend. Quantization parameters, dynamic shapes and custom ops are the usual breakage points. A converted model is therefore a new artifact that must be validated against the source: run the same inputs through both and compare outputs within a stated tolerance, because a silent numeric divergence ships as a quality regression nobody can explain.

Primary sources: <https://onnx.ai/> and <https://onnxruntime.ai/docs/>.

## Decision rules

- Choose the target format from the runtime and device, not from habit.
- Use ONNX as the interchange when more than one target runtime is involved.
- Check operator support for the target before committing; an unsupported op is a rewrite, not a warning.
- Validate the converted model against the source on a representative input set within a stated tolerance.
- Treat dynamic shapes, custom ops and quantization parameters as the likely failure points.
- Version the converted artifact separately from the source and record the converter version.

## Procedure

1. Enumerate the model's operators and any custom or dynamic-shape components.
2. Check the target runtime's supported-op list against that enumeration.
3. Convert, resolving unsupported ops by rewrite, replacement or declared fallback.
4. Run a representative input set through source and converted models.
5. Compare outputs; require agreement within the stated tolerance.
6. Package the validated artifact with its converter version and validation result.

## Anti-patterns

- Assuming a successful conversion means an equivalent model.
- Shipping without comparing outputs against the source.
- Discovering an unsupported op on the device instead of at conversion time.
- Using a heavy framework runtime on-device when a purpose-built one exists.
- Losing track of which converter version produced the shipped artifact.

## Done checklist

- [ ] Operators enumerated and checked against target support.
- [ ] Unsupported ops resolved deliberately.
- [ ] Outputs compared against source within tolerance.
- [ ] Dynamic shapes and custom ops handled.
- [ ] Artifact versioned with converter version.
- [ ] Validation result recorded.

## Sources

- ONNX format and ecosystem: <https://onnx.ai/>
- ONNX Runtime documentation: <https://onnxruntime.ai/docs/>
- Apple CoreML framework: <https://developer.apple.com/documentation/coreml>
