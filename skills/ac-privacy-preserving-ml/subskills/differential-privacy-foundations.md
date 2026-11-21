---
name: differential-privacy-foundations
domain: software-engineering/differential-privacy-foundations
trigger: "Understanding or choosing the epsilon-delta guarantee and its composition."
anti_trigger: "Not for the DP-SGD training mechanics, and not for federation."
scope: "The epsilon-delta guarantee and its composition."
status: seedling
---

# Differential privacy foundations

## Standard

Differential privacy is a property of a mechanism, not of a dataset. A randomised mechanism M is (epsilon, delta)-differentially private if, for any two datasets differing in a single individual's record, and any output set S, the probability that M returns something in S changes by at most a factor of e^epsilon, plus an additive slack delta. The guarantee is about the indistinguishability of neighbouring inputs: an adversary looking at the output cannot tell whether any one person was included.

The two parameters carry distinct meanings. Epsilon is the privacy loss — small epsilon means the output barely depends on any individual, so epsilon is the number that bounds leakage, and it compounds across queries. Delta is the probability of outright failure, and it must be cryptographically negligible relative to the dataset size; a delta larger than one over the population is no guarantee at all. The composition theorem is what makes the budget real: running an (epsilon1, delta1) mechanism and an (epsilon2, delta2) mechanism yields roughly (epsilon1+epsilon2, delta1+delta2) privacy, so every query and every training step spends from a finite budget.

Primary sources: <https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf> and <https://en.wikipedia.org/wiki/Differential_privacy>.

## Decision rules

- Define the neighbouring-dataset relation explicitly (one record added, removed, or changed).
- Treat epsilon as the leakage bound and delta as the failure probability; never conflate them.
- Set delta well below one over the number of individuals.
- Sum epsilon and delta across every release and every training step; the total is the real guarantee.
- Distinguish central DP (a trusted curator adds noise) from local DP (each user adds their own).
- A guarantee is only as strong as its worst composition; advanced composition tightens but never eliminates the spend.

## Procedure

1. Fix the neighbouring relation and the unit of privacy (record, user, or group).
2. Choose the mechanism family (Laplace, Gaussian, exponential) and its sensitivity.
3. Calibrate noise to the target epsilon and delta.
4. Track cumulative epsilon and delta across all compositions.
5. Report the final (epsilon, delta) with the neighbouring relation and unit.
6. State what the guarantee does not cover (population facts, side channels, poisoning).

## Anti-patterns

- Calling a dataset "differentially private" — the property belongs to the mechanism.
- A delta larger than the inverse of the population size.
- Reporting epsilon for a single query while ignoring the composed total.
- Assuming small epsilon makes the model useless, or large epsilon makes it safe.
- Treating DP as protection against a malicious training client.

## Done checklist

- [ ] Neighbouring relation and privacy unit defined.
- [ ] Epsilon and delta meanings separated.
- [ ] Delta set below inverse population.
- [ ] Composition accounted across all releases and steps.
- [ ] Central versus local DP chosen and stated.
- [ ] Residual risks named.

## Sources

- The Algorithmic Foundations of Differential Privacy (Dwork and Roth): <https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf>
- Differential privacy overview: <https://en.wikipedia.org/wiki/Differential_privacy>
- Deep Learning with Differential Privacy: <https://arxiv.org/abs/1607.00133>
