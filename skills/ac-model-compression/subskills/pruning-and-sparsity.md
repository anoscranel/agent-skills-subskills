---
name: pruning-and-sparsity
domain: software-engineering/pruning-and-sparsity
trigger: "Removing weights or structures to shrink and speed up a model."
anti_trigger: "Not for quantization, and not for distilling into a new architecture."
scope: "Removing weights; structured versus unstructured sparsity."
status: seedling
---

# Pruning and sparsity

## Standard

Pruning removes parameters the model can do without. The central distinction is what is removed. Unstructured pruning deletes individual weights by magnitude, producing a sparse weight matrix; it reaches high sparsity with little accuracy loss, but a sparse matrix does not run faster unless the hardware and kernels exploit the sparsity — on dense hardware the zeros are still multiplied. Structured pruning removes whole units: channels, attention heads, neurons, or entire layers. It yields a genuinely smaller, denser model that runs faster on ordinary hardware, at a larger accuracy cost per parameter removed.

The pipeline that made the approach famous is Deep Compression: prune the small weights, quantize the survivors, then entropy-code the result, with retraining between stages to recover accuracy. The Lottery Ticket Hypothesis adds a caution: dense networks contain sparse subnetworks that can train to full accuracy, but finding them requires iterative pruning and retraining, so it is a research finding about trainability, not a free compression method. Some hardware supports structured N:M sparsity (for example 2:4, two non-zeros per four weights) through sparse tensor cores; that is the case where sparsity does translate into speed, and it is a specific, measurable target rather than a general hope.

Primary sources: <https://arxiv.org/abs/1510.00149> and <https://arxiv.org/abs/1803.03635>.

## Decision rules

- Choose structured pruning for real latency gains on ordinary hardware.
- Choose unstructured pruning for storage reduction via sparse encoding; expect a speedup only with sparse kernels and hardware.
- Retrain after pruning to recover accuracy; pruning without retraining loses more.
- Prune gradually and re-measure; one aggressive pass costs more than staged removal.
- Treat N:M sparsity as a hardware-specific target, measured on that hardware.
- Do not claim a speedup from sparsity without a kernel that exploits it.

## Procedure

1. Decide structured or unstructured from the deployment hardware.
2. Rank units or weights by a saliency criterion (magnitude, or a sensitivity estimate).
3. Remove a fraction, then retrain to recover accuracy.
4. Iterate prune-and-retrain toward the target size.
5. Measure accuracy and real latency on the target hardware.
6. Record the sparsity pattern, ratio, retraining, and measured effects.

## Anti-patterns

- Reporting unstructured sparsity as a latency win on dense hardware.
- Pruning once, hard, with no retraining to recover accuracy.
- Citing the Lottery Ticket Hypothesis as a cheap compression recipe.
- Structured pruning of whole layers without checking the accuracy collapse.
- No measurement of the actual speedup on the target device.

## Done checklist

- [ ] Structured versus unstructured decided from hardware.
- [ ] Saliency criterion chosen.
- [ ] Prune-and-retrain iterated.
- [ ] Target size reached with accuracy measured.
- [ ] Real latency measured on target hardware.
- [ ] Sparsity pattern, ratio, and effects recorded.

## Sources

- Deep Compression (prune, quantize, Huffman): <https://arxiv.org/abs/1510.00149>
- The Lottery Ticket Hypothesis: <https://arxiv.org/abs/1803.03635>
- Pruning in neural networks, overview: <https://en.wikipedia.org/wiki/Pruning_(neural_networks)>
