---
name: compression-record
domain: software-engineering/compression-record
trigger: "Writing the record of how a model was compressed and what it cost."
anti_trigger: "Not for the compression itself, and not for the serving runbook."
scope: "The written record: scheme, calibration, deltas, device fit."
status: seedling
---

# Compression record

## Standard

The compression record is what lets the next engineer reproduce the artifact and trust it. It captures the full chain from baseline to deployed compressed model: which scheme was applied with which settings, what data calibrated it, what the quality and fit measurements showed, and what limitations shipped. Without it, a compressed model is an opaque binary whose provenance and quality nobody can check, and a later regression cannot be attributed to the compression step at all.

The record is honest about cost. It states the quality delta against the baseline on the task metric, the measured latency and memory on the target device, and the failures the evaluation exposed even if they were accepted. It names the baseline by version and the compressed artifact by a reproducible identifier, so the pair can be re-compared after any change. And it carries the known limitations — the tasks where quality dropped most, the inputs the calibration set never covered, the hardware where the expected speedup did not materialize — because those are exactly what the next incident will involve.

Primary sources: <https://arxiv.org/abs/2210.17323> and <https://arxiv.org/abs/1510.00149>.

## Decision rules

- Record the scheme, its settings, and the baseline version by identifier.
- Name the calibration set and confirm it was disjoint from the eval set.
- Record quality delta on the task metric and fit measurements on target hardware.
- List accepted degradations and known limitations explicitly.
- Version the compressed artifact so baseline and candidate can be re-compared.
- Update the record on every re-compression; never edit history silently.

## Procedure

1. Name the baseline model and version.
2. Record the scheme, bit-width or sparsity, and all settings.
3. Record the calibration set and its disjointness from eval.
4. Attach quality and fit measurements with the accept decision.
5. Write the limitations: worst tasks, uncovered inputs, failed speedups.
6. Version and store the record with the artifact.

## Anti-patterns

- A compressed artifact with no recorded provenance or settings.
- Calibration set undocumented, so eval disjointness cannot be checked.
- Only successes recorded; accepted degradations omitted.
- No baseline version, so the delta cannot be recomputed.
- Overwriting the old record after a re-compression instead of versioning.

## Done checklist

- [ ] Baseline and version named.
- [ ] Scheme and all settings recorded.
- [ ] Calibration set named, disjointness confirmed.
- [ ] Quality and fit measurements attached.
- [ ] Limitations and accepted degradations written.
- [ ] Artifact versioned with its record.

## Sources

- GPTQ, scheme and calibration detail: <https://arxiv.org/abs/2210.17323>
- Deep Compression, the staged pipeline to record: <https://arxiv.org/abs/1510.00149>
- Model soups, recording merge parents and coefficients: <https://arxiv.org/abs/2203.05482>
