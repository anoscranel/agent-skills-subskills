---
name: sampling-and-coverage
domain: research-operations/sampling-coverage
trigger: "Deciding who is sampled and how the frame covers the population."
anti_trigger: "Not for questionnaire wording, and not for weighting."
scope: "Target population, frame, probability design, and precision."
status: seedling
---

# Sampling and coverage

## Standard

The target population is the set the result should describe; the sampling frame is the list actually drawn from. The gap between them is coverage error, and it is not random — a frame built from a customer list, a phone directory, or a website's users systematically excludes everyone outside it. Coverage error is the quiet killer of survey claims: a perfectly executed survey of a partial frame describes only that frame.

The design is probability or non-probability. A probability sample gives every population unit a known, non-zero chance of selection — simple random, stratified, cluster, or systematic — and supports a population estimate with a measurable margin of error. A non-probability sample (convenience, quota, panel opt-in, snowball) does not, and cannot produce a design-based margin of error no matter how large it is. Sample size buys precision only within a probability design: the margin of error shrinks roughly with the square root of n, so quadrupling the sample halves it, and beyond a few thousand the returns diminish sharply.

Primary sources: <https://en.wikipedia.org/wiki/Sampling_(statistics)> and <https://en.wikipedia.org/wiki/Stratified_sampling>.

## Decision rules

- Define the target population, then the frame; state the coverage gap explicitly.
- Use a probability design when a population estimate with a margin of error is required.
- Never report a margin of error for a non-probability sample.
- Stratify when subgroups must be measured separately or vary in size.
- Compute sample size from the required precision, not from a round number.
- State the diminishing returns: beyond a point, more responses add little precision.

## Procedure

1. Write the target population and the frame; name who the frame excludes.
2. Choose probability or non-probability, with the justification.
3. If probability, choose the design (simple, stratified, cluster, systematic).
4. Compute the sample size for the required margin of error.
5. Document the coverage error and the design's assumptions.
6. Record the design and the precision it supports.

## Anti-patterns

- Treating a large opt-in panel as a representative sample.
- Reporting a margin of error computed as if a convenience sample were random.
- A frame that silently excludes a population segment.
- Ignoring stratification when a small subgroup must be measured.
- Claiming precision the design cannot support.

## Done checklist

- [ ] Target population and frame defined.
- [ ] Coverage gap stated.
- [ ] Probability/non-probability chosen and justified.
- [ ] Sample size computed from precision.
- [ ] No margin of error claimed for non-probability samples.
- [ ] Design and assumptions recorded.

## Sources

- Sampling (statistics): <https://en.wikipedia.org/wiki/Sampling_(statistics)>
- Stratified sampling: <https://en.wikipedia.org/wiki/Stratified_sampling>
- Pew Research methods: <https://www.pewresearch.org/our-methods/>
