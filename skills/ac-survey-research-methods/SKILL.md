---
name: ac-survey-research-methods
description: 'Designing and running a survey that measures what it claims to: the research question and survey mode, sampling frames and coverage, questionnaire design and cognitive pretesting, question wording and response bias, administration and fieldwork, non-response and weighting, and the survey methods record. It owns the craft of primary survey data collection; it never generalises a convenience sample to a population and never reports a result without its response rate and limitations. Use when asking "design a survey", "survey methodology", "questionnaire design", "sampling frame", "response rate", "non-response bias", "survey weighting", "how many responses do I need", "write survey questions". Not for synthesising existing studies (ac-systematic-review-conduct), not for synthesising qualitative findings (ac-qualitative-synthesis), not for labelling ML datasets (ac-data-annotation), not for causal estimation (ac-causal-inference).'
license: MIT
metadata:
  domain: research-operations
status: seedling
---

# Survey research methods

## Overview

A survey is a measurement instrument, not a form. It answers a question about a population by asking a sample, and every design choice — who is asked, what is asked, how it is asked, who actually answers — moves the result. The craft is keeping four error sources visible: coverage error (the frame misses part of the population), sampling error (the sample differs by chance), measurement error (the question does not elicit the construct), and non-response error (respondents differ from non-respondents). A survey that reports only a number hides all four.

This skill owns primary survey data collection. Its neighbours carve the rest: ac-systematic-review-conduct synthesises existing studies, ac-qualitative-synthesis synthesises qualitative findings, ac-data-annotation labels ML data, ac-causal-inference estimates effects from observational data. The survey researcher builds and fields the instrument itself.

Primary sources: <https://www.pewresearch.org/our-methods/> and <https://en.wikipedia.org/wiki/Survey_methodology>.

## When to use

- Designing a new survey instrument and sampling plan.
- When a questionnaire must measure a construct reliably.
- When deciding sample size, mode, and fieldwork approach.
- When analysing and reporting response rates and non-response bias.

## When NOT to use

- For synthesising existing literature (use ac-systematic-review-conduct).
- For qualitative data collection and analysis (use ac-qualitative-synthesis).
- For labelling ML training data (use ac-data-annotation).
- For causal estimation from existing data (use ac-causal-inference).

## Subskill Index

| Leaf | Domain segment | Scope (one line) |
|---|---|---|
| `subskills/the-survey-question-and-mode.md` | `research-operations/survey-question-mode` | Construct, mode, and the descriptive-versus-analytic choice. |
| `subskills/sampling-and-coverage.md` | `research-operations/sampling-coverage` | Target population, frame, probability design, and precision. |
| `subskills/questionnaire-design.md` | `research-operations/questionnaire-design` | From construct to item, scales, order, and pretesting. |
| `subskills/wording-and-response-bias.md` | `research-operations/wording-response-bias` | Neutral wording and the response-style biases. |
| `subskills/administration-and-fieldwork.md` | `research-operations/administration-fieldwork` | Mode effects, interviewers, incentives, and field monitoring. |
| `subskills/nonresponse-and-weighting.md` | `research-operations/nonresponse-weighting` | Response rates, weighting, and non-response bias analysis. |
| `subskills/survey-record-and-reporting.md` | `research-operations/survey-record` | The methods record every survey must publish. |

## Status and honest limits

A survey measures its sample, and generalises only as far as its design allows. A large convenience sample is not a representative sample, and a high response rate does not by itself remove non-response bias. Question wording and mode can move a result as much as the construct being measured, so the instrument is part of the finding. Nothing here turns a non-probability sample into a population estimate; the methods record must state the design and its limits.
