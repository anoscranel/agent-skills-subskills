---
name: nonresponse-and-weighting
domain: research-operations/nonresponse-weighting
trigger: "Handling who did not answer and adjusting the sample."
anti_trigger: "Not for sampling design, and not for fieldwork."
scope: "Response rates, weighting, and non-response bias analysis."
status: seedling
---

# Non-response and weighting

## Standard

Not everyone sampled responds, and non-respondents rarely resemble respondents. Unit non-response — a sampled unit that never answers — is the central threat to a survey's claim, because if the people who declined differ on the construct, the result is biased regardless of sample size. A high response rate reduces the risk but does not eliminate it: a 70% response rate can still hide a biased 30%, and a low rate does not automatically mean a biased result if non-respondents resemble respondents.

The response rate is computed and reported by a standard convention, not asserted. The numerator is completed responses; the denominator is all eligible sampled units, with the disposition of every sampled case (complete, partial, refusal, non-contact, ineligible, unknown eligibility) recorded so the rate is reproducible. Different conventions exist, so the convention used is named alongside the number.

Weighting adjusts the achieved sample back toward the population. Design weights correct for unequal selection probabilities; non-response weights adjust for differential response across known groups; post-stratification or calibration forces the weighted sample to match known population totals on variables like age, sex, and region. Weighting reduces bias on the weighted variables but inflates variance, so the weighting and its effect on precision are both reported.

Primary sources: <https://en.wikipedia.org/wiki/Non-response_bias> and <https://en.wikipedia.org/wiki/Response_rate_(survey)>.

## Decision rules

- Record the disposition of every sampled unit; compute the response rate by a named convention.
- Analyse non-response bias using frame variables, paradata, or late-versus-early comparison.
- Weight for unequal selection, then non-response, then post-stratification as needed.
- Report both the bias reduction and the variance inflation from weighting.
- Never claim a high response rate proves an unbiased result.
- State what remains unknown about non-respondents.

## Procedure

1. Tabulate dispositions for every sampled case.
2. Compute the response rate by a named convention.
3. Assess non-response bias with available auxiliary data.
4. Compute design weights, then non-response adjustments.
5. Post-stratify to known population totals; cap extreme weights.
6. Report the response rate, weights, and their effect on precision.

## Anti-patterns

- A response rate quoted with no convention and no dispositions.
- Treating a high response rate as proof of representativeness.
- Weighting without reporting the variance cost.
- Extreme weights left uncapped, letting a few cases dominate.
- No analysis of how non-respondents might differ.

## Done checklist

- [ ] Dispositions recorded for every sampled unit.
- [ ] Response rate computed by a named convention.
- [ ] Non-response bias analysed with auxiliary data.
- [ ] Weights computed and extreme weights capped.
- [ ] Variance inflation from weighting reported.
- [ ] Residual uncertainty about non-respondents stated.

## Sources

- Non-response bias: <https://en.wikipedia.org/wiki/Non-response_bias>
- Response rate: <https://en.wikipedia.org/wiki/Response_rate_(survey)>
- UN household survey guidance: <https://unstats.un.org/unsd/hhsurveys/>
