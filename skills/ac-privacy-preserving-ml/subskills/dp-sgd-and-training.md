---
name: dp-sgd-and-training
domain: software-engineering/dp-sgd-and-training
trigger: "Training a model with DP-SGD and accounting its privacy budget."
anti_trigger: "Not for the DP theory, and not for federated transport."
scope: "Per-example clipping, calibrated noise, the accountant."
status: seedling
---

# DP-SGD and training

## Standard

DP-SGD turns ordinary stochastic gradient descent into a differentially private mechanism with two changes. First, each example's gradient is clipped to a maximum L2 norm C, which bounds the sensitivity of the update to any single example. Second, Gaussian noise with standard deviation proportional to C times a noise multiplier sigma is added to the averaged gradient before the step. Clipping alone bounds influence; the noise is what delivers the guarantee, and sigma is the knob that trades privacy against accuracy.

The privacy cost is computed, not guessed. Each step consumes privacy proportional to the sampling rate and the noise multiplier, and the total over T steps is composed with a Renyi-differential-privacy accountant that converts to an (epsilon, delta) figure at the end. Batch sampling matters because sampling without replacement amplifies privacy: a smaller sampling fraction means each example is touched less often, which buys privacy per step. The practical loop is to fix the clipping norm and the sampling rate, then raise or lower sigma until the accountant reports the target epsilon at the planned number of steps and delta.

Primary sources: <https://arxiv.org/abs/1607.00133> and <https://opacus.ai/>.

## Decision rules

- Clip per-example gradients, not the batch gradient; the per-example bound is the sensitivity.
- Add Gaussian noise scaled to the clipping norm and the noise multiplier sigma.
- Compute epsilon with a Renyi-DP accountant over the actual step count and sampling rate.
- Choose delta below one over the number of training examples.
- Use sampling amplification honestly: state whether sampling is with or without replacement.
- Report the accuracy delta against a non-private baseline on the same data and budget.

## Procedure

1. Set the clipping norm C, the sampling rate, and the target step count.
2. Fix delta below the inverse example count and choose a starting sigma.
3. Wrap the optimizer with per-example gradient clipping and noise.
4. Run the accountant to read epsilon at the planned steps.
5. Adjust sigma to hit the target epsilon; retrain and measure accuracy.
6. Record C, sigma, sampling rate, steps, delta, and the resulting epsilon and accuracy.

## Anti-patterns

- Clipping the averaged batch gradient instead of each example's.
- Quoting an epsilon without the accountant and the step count behind it.
- A delta comparable to or above one over the dataset size.
- Comparing DP accuracy to a baseline trained with a different budget or data split.
- Raising sigma until the model stops learning and shipping the degradation unexamined.

## Done checklist

- [ ] Per-example clipping configured with a stated C.
- [ ] Gaussian noise scaled to C and sigma.
- [ ] Renyi-DP accountant used for epsilon.
- [ ] Delta below inverse example count.
- [ ] Sampling scheme and amplification stated.
- [ ] Accuracy delta versus non-private baseline recorded.

## Sources

- Deep Learning with Differential Privacy (Abadi et al.): <https://arxiv.org/abs/1607.00133>
- Opacus, a DP-SGD library: <https://opacus.ai/>
- Opacus FAQ on clipping and noise: <https://opacus.ai/docs/faq>
- The Algorithmic Foundations of Differential Privacy: <https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf>
