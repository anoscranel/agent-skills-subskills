---
name: ac-edge-ml-deployment
description: 'Deploying ML models to run on-device at the edge: the on-device-versus-cloud decision, model formats and conversion (ONNX, TFLite, CoreML), runtime and hardware-delegate selection (NNAPI, CoreML Neural Engine, ONNX Runtime execution providers), browser inference with WASM and WebGPU, honest on-device benchmarking, the memory, thermal and power envelope, and cloud-fallback integration with the written deployment record. It puts a trained model onto a phone, embedded device or browser and proves it runs acceptably there; it never promises a latency on unmeasured hardware. Use when asking "run a model on-device", "ONNX conversion", "TFLite or CoreML", "NNAPI delegate", "WebGPU inference", "on-device benchmarking", "edge AI deployment", "cloud fallback". Not for shrinking the model artifact (ac-model-compression), not for building the mobile app (ac-mobile-client-engineering), not for server-side serving and KV-cache (ac-inference-serving), not for GPU kernel craft (ac-gpu-and-parallel-compute).'
license: MIT
metadata:
  domain: software-engineering
status: seedling
---

# Edge ML deployment

## Overview

A trained model is not a deployed model. Between the artifact and a running on-device feature sit a chain of decisions that determine whether the thing works at all: which format to ship, which runtime executes it, which hardware backend runs the ops, how to measure it honestly on a phone that throttles, and what to do when a device cannot run it. Each decision has failure modes that only appear on real hardware, and each is independent of how the model was trained or compressed.

This skill owns that deployment chain. Its neighbours own the rest: ac-model-compression shrinks the artifact; ac-mobile-client-engineering builds and ships the app around it; ac-inference-serving runs models on servers; ac-gpu-and-parallel-compute writes kernels. The seam here is the device: getting a model onto a phone, an embedded board, or a browser tab and proving it runs acceptably, with a fallback when it cannot.

Primary sources: <https://arxiv.org/abs/2106.08962> and <https://onnxruntime.ai/docs/>.

## When to use

- Deciding whether a feature should run on-device or in the cloud.
- Converting a model to ONNX, TFLite or CoreML and validating the conversion.
- Choosing a runtime and hardware delegate for a target device.
- Running inference in a browser with WASM or WebGPU.
- Benchmarking latency, memory and power on real devices.
- Wiring cloud fallback for devices that cannot run the model.

## When NOT to use

- For quantizing, pruning or distilling the model itself (use ac-model-compression).
- For app release cycles, push, deep links and store review (use ac-mobile-client-engineering).
- For server-side serving, batching and KV-cache (use ac-inference-serving).
- For writing GPU kernels (use ac-gpu-and-parallel-compute).

## Subskill Index

| Leaf | Domain segment | Scope (one line) |
|---|---|---|
| `subskills/whether-on-device.md` | `software-engineering/whether-on-device` | The on-device-versus-cloud decision, in numbers. |
| `subskills/model-formats-and-conversion.md` | `software-engineering/model-formats-and-conversion` | ONNX, TFLite, CoreML and conversion validation. |
| `subskills/runtimes-and-delegates.md` | `software-engineering/runtimes-and-delegates` | CPU, GPU, NPU backends and execution providers. |
| `subskills/browser-and-web-inference.md` | `software-engineering/browser-and-web-inference` | WASM and WebGPU inference in the browser. |
| `subskills/on-device-benchmarking.md` | `software-engineering/on-device-benchmarking` | Honest latency, memory and power measurement. |
| `subskills/memory-thermal-and-power.md` | `software-engineering/memory-thermal-and-power` | The resource envelope: size, RAM, heat, battery. |
| `subskills/integration-fallback-and-record.md` | `software-engineering/integration-fallback-and-record` | Cloud fallback, model updates, and the record. |

## Status and honest limits

On-device performance is a property of a specific device, OS version and thermal state, not of the model; a number measured on one handset says little about another, and nothing about a device never measured. Op-support gaps mean a converted model can silently differ from the original, so conversion correctness must be validated against the source, not assumed. WebGPU and NNAPI capabilities vary across devices and versions, and a delegate that exists is not a delegate that is faster — some ops fall back to CPU mid-graph. Nothing here promises a latency figure; every performance claim is scoped to the hardware and conditions it was measured under.
