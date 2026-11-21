---
name: inter-annotator-agreement
domain: software-engineering/inter-annotator-agreement
trigger: "Measuring label consistency and reading what low agreement means."
anti_trigger: "Not for adjudicating specific items, and not for model scoring."
scope: "Measuring consistency and reading what low agreement actually means."
status: seedling
---

# Inter-annotator agreement

## Standard

Agreement is the evidence that the instrument is being applied consistently. Raw percent agreement is not that evidence: two annotators guessing the majority label will agree often by chance alone. The chance-corrected coefficients exist to remove that floor — Cohen's kappa for two raters, Fleiss' kappa for a fixed panel, Krippendorff's alpha for any number of raters, missing data, and any measurement level. Artstein and Poesio's survey is the reference for choosing among them and for the discipline of reporting which coefficient was used, on what data, with what expected agreement.

The reading matters more than the number. Low agreement is a diagnostic, not a verdict: it can mean the guidelines are ambiguous, the task is genuinely hard, the taxonomy forces bad fits, or one annotator is miscalibrated — and each cause has a different fix. The survey's central caution is that there is no universal threshold that certifies a dataset; a kappa that is acceptable for an exploratory corpus can be unacceptable for a safety-critical label. Agreement must be reported per label as well as overall, because a rare but important class can be failing while the aggregate looks healthy. And high agreement never proves correctness: a panel can agree consistently on a biased reading.

Primary sources: <https://doi.org/10.1162/coli.07-034-R2> and <https://en.wikipedia.org/wiki/Krippendorff%27s_alpha>.

## Decision rules

- Use a chance-corrected coefficient, never raw percent agreement alone.
- Match the coefficient to the design: Cohen two raters, Fleiss fixed panel, alpha for missing/ordinal/many raters.
- Report the coefficient, the data it was computed on, and the expected agreement.
- Compute agreement per label, not only overall; watch rare classes.
- Treat low agreement as a diagnostic: guidelines, task difficulty, taxonomy, or annotator.
- Set the acceptance bar from the task's stakes, not from a generic threshold.

## Procedure

1. Double-label a representative sample (or all items, if budget allows).
2. Choose the coefficient that matches the rating design and measurement level.
3. Compute overall and per-label agreement with expected agreement stated.
4. Compare against the stakes-based bar set before labeling began.
5. If below bar, diagnose the cause from the disagreement patterns.
6. Fix the cause (guidelines, taxonomy, calibration) and re-measure; record both.

## Anti-patterns

- Reporting raw percent agreement as if it were reliability.
- Quoting a kappa without saying which coefficient or on what sample.
- A single overall number hiding a failing rare class.
- Treating one universal threshold as certifying any dataset.
- Reading high agreement as proof the labels are correct.

## Done checklist

- [ ] Chance-corrected coefficient chosen for the design.
- [ ] Coefficient, sample, and expected agreement reported.
- [ ] Per-label agreement computed.
- [ ] Stakes-based acceptance bar set in advance.
- [ ] Low agreement diagnosed, not just flagged.
- [ ] Re-measurement after the fix recorded.

## Sources

- Inter-Coder Agreement for Computational Linguistics (Artstein & Poesio): <https://doi.org/10.1162/coli.07-034-R2>
- Krippendorff's alpha: <https://en.wikipedia.org/wiki/Krippendorff%27s_alpha>
- Cohen's kappa: <https://en.wikipedia.org/wiki/Cohen%27s_kappa>
- Fleiss' kappa: <https://en.wikipedia.org/wiki/Fleiss%27_kappa>