---
name: ac-model-compression
description: 'Compressing a trained model for deployment: quantization from FP16 to INT8 and INT4 (PTQ versus QAT, GPTQ, AWQ, GGUF), knowledge distillation into a smaller student, structured and unstructured pruning, and model merging that combines fine-tuned weights without retraining. It covers whether to compress, the quality-versus-size trade-off, calibration, and the evaluation that proves the compressed model still does the job. It compresses the model artifact; it never promises a speedup on unmeasured hardware and never treats a smaller model as automatically better. Use when asking "quantize a model", "GPTQ vs AWQ", "INT4 or INT8", "distill a model", "prune a network", "merge fine-tuned models", "model soup", "compress an LLM for edge", "GGUF". Not for serving infrastructure and KV-cache (ac-inference-serving), not for adapting weights by training (ac-model-fine-tuning), not for GPU kernel and hardware craft (ac-gpu-and-parallel-compute).'
license: MIT
metadata:
  domain: software-engineering
status: seedling
---

# Model compression

## Overview

A trained model is often too large, too slow, or too expensive for where it must run. Compression changes the artifact itself so it fits a constraint: fewer bytes per weight (quantization), fewer effective weights (pruning), a smaller model taught by a larger one (distillation), or several fine-tuned variants folded into one (merging). These are distinct operations with distinct costs, and they compose: Deep Compression combined pruning, quantization, and entropy coding.

The craft is not "make it small" but "make it small enough while keeping the behaviour the task depends on, on the hardware that will run it." Compression trades quality for size and speed, and the trade is not free: below some bit-width accuracy drops sharply; unstructured sparsity rarely speeds anything up without sparse hardware; a merged model can inherit interference between its parents. Every claimed win is a measurement on a target device, not an assumption.

This skill owns compression of the artifact; its neighbours are ac-inference-serving (production serving), ac-model-fine-tuning (training), ac-gpu-and-parallel-compute (hardware and kernels), and ac-model-evaluation (offline selection). Compression sits between training and serving: it takes a trained model, produces a smaller one, and hands it to the serving layer.

Primary sources: <https://arxiv.org/abs/2210.17323> and <https://arxiv.org/abs/1503.02531>.

## When to use

- When a model must fit a memory, storage, latency, or cost constraint.
- When choosing between quantization, distillation, pruning, or merging.
- When compressing for edge, CPU, or on-device deployment (GGUF, INT4).
- When evaluating whether a compressed model still meets the quality bar.

## When NOT to use

- For serving infrastructure, KV-cache, and batching (use ac-inference-serving).
- For adapting weights by training (use ac-model-fine-tuning).
- For GPU kernel and hardware craft (use ac-gpu-and-parallel-compute).
- For offline model selection suites (use ac-model-evaluation).

## Subskill Index

| Leaf | Domain segment | Scope (one line) |
|---|---|---|
| `subskills/whether-to-compress.md` | `software-engineering/whether-to-compress` | The decision: constraint, quality budget, and the alternatives. |
| `subskills/quantization.md` | `software-engineering/quantization` | Lowering weight precision: PTQ, QAT, GPTQ, AWQ, GGUF. |
| `subskills/knowledge-distillation.md` | `software-engineering/knowledge-distillation` | Teaching a smaller student from a larger teacher. |
| `subskills/pruning-and-sparsity.md` | `software-engineering/pruning-and-sparsity` | Removing weights; structured versus unstructured sparsity. |
| `subskills/model-merging.md` | `software-engineering/model-merging` | Combining fine-tuned weights: soups, task arithmetic, DARE. |
| `subskills/evaluating-compression.md` | `software-engineering/evaluating-compression` | Proving the compressed model still meets the bar. |
| `subskills/compression-record.md` | `software-engineering/compression-record` | The written record: scheme, calibration, deltas, device fit. |

## Status and honest limits

Compression is a measured trade, never a guarantee. Quantization below four bits usually costs noticeable accuracy; unstructured sparsity does not accelerate inference without sparse kernels and hardware; model soups require a shared base and architecture and can fail silently when parents interfere; a distilled student inherits its teacher's blind spots as well as its strengths. No scheme here promises a latency or memory number on unmeasured hardware — that measurement is part of the work. The evaluation gate is what separates a compressed model from a broken one; skipping it is the most common way compression goes wrong.
