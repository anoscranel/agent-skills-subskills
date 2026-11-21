---
name: ac-qualitative-research-methods
description: 'Conducting primary qualitative research: the exploratory research question and design family (grounded theory, ethnography, case study, phenomenology), purposive and theoretical sampling, interviews, observation and focus groups, coding and thematic analysis, theoretical sampling and saturation, trustworthiness and reflexivity, and the written qualitative record. It owns collecting and analysing qualitative data to build understanding; it never synthesises existing studies and never claims statistical generalisation. Use when asking "design a qualitative study", "grounded theory", "thematic analysis", "run interviews or focus groups", "purposive sampling", "data saturation", "coding qualitative data", "reflexivity", "ethnography". Not for synthesising published qualitative studies (ac-qualitative-synthesis), not for systematic-review protocol compliance (ac-systematic-review-conduct), not for quantitative survey design (ac-survey-research-methods), not for labeling ML datasets (ac-data-annotation).'
license: MIT
metadata:
  domain: research-operations
status: seedling
---

# Qualitative research methods

## Overview

Qualitative research builds understanding of meaning, process, and context from non-numerical data: interviews, observation, documents, focus groups. The craft is a disciplined path from an exploratory question through purposive sampling and iterative collection to a trustworthy, well-evidenced account. It is not a smaller, softer version of a survey: the sampling logic, the analysis, and the warrant for the claims are different in kind, and treating qualitative rigour as "fewer numbers" is the central error this skill exists to prevent.

This skill owns primary qualitative conduct. Its neighbours carve the rest: ac-qualitative-synthesis brings existing qualitative studies together; ac-systematic-review-conduct runs review protocols; ac-survey-research-methods designs quantitative surveys; ac-data-annotation produces ML labels. The line: this skill collects and analyses new qualitative data to understand a phenomenon, not to pool the literature, estimate a population parameter, or label a dataset.

Primary sources: <https://doi.org/10.1191/1478088706qp063oa> and <https://en.wikipedia.org/wiki/Qualitative_research>.

## When to use

- Framing an exploratory question about meaning, experience, or process.
- Choosing a design: grounded theory, ethnography, case study, phenomenology.
- Planning interviews, observation, or focus groups with purposive sampling.
- Coding qualitative data and judging saturation and trustworthiness.

## When NOT to use

- For synthesising published qualitative studies (use ac-qualitative-synthesis).
- For systematic-review protocol compliance (use ac-systematic-review-conduct).
- For quantitative survey design and sampling (use ac-survey-research-methods).
- For labeling ML datasets (use ac-data-annotation).

## Subskill Index

| Leaf | Domain segment | Scope (one line) |
|---|---|---|
| `subskills/design-and-framing.md` | `research-operations/design-and-framing` | The exploratory question, the design family, and the stated paradigm. |
| `subskills/sampling-and-recruitment.md` | `research-operations/sampling-and-recruitment` | Purposive and theoretical sampling for information richness, not representation. |
| `subskills/data-collection-methods.md` | `research-operations/data-collection-methods` | Interviews, observation, focus groups, and documents done well. |
| `subskills/coding-and-analysis.md` | `research-operations/coding-and-analysis` | Open coding, constant comparison, and thematic analysis to build an account. |
| `subskills/saturation-and-iteration.md` | `research-operations/saturation-and-iteration` | Iterating collection toward saturation and what saturation actually means. |
| `subskills/trustworthiness-and-reflexivity.md` | `research-operations/trustworthiness-and-reflexivity` | Credibility, transferability, dependability, confirmability, and the reflexive stance. |
| `subskills/qualitative-record.md` | `research-operations/qualitative-record` | The written record: design, sampling, analysis trail, and the reporting checklist. |

## Status and honest limits

Qualitative findings are not statistically generalisable; the warrant is transferability to comparable contexts, argued through thick description, not a margin of error. The researcher is the instrument, so the account is shaped by the researcher's position — reflexivity is a methodological requirement, not a confession. Saturation is a judgment about the adequacy of the data for the emerging account, not a number of interviews, and "we interviewed twelve people" is not evidence of it. No coding software or checklist produces understanding; they support a reasoning process the researcher must still perform. This skill builds trustworthy qualitative accounts; it does not turn them into population estimates.
