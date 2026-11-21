---
name: ac-user-research
description: 'Understanding users and testing whether a product works for them: research framing, usability testing with task-based metrics, usability measurement (task success, time-on-task, SUS, SEQ), user interviews and personas, recruiting representative participants, analysing findings into recommendations, and the research record with consent and ethics. It owns the observe-real-users craft; it never substitutes expert opinion for observed user behaviour and never generalises a handful of participants to a population. Use when asking "usability testing", "user research", "test with users", "SUS score", "think aloud", "user interview", "personas", "how many users to test", "journey map", "usability metrics". Not for expert heuristic evaluation and design critique (ac-design-taste), not for open-ended qualitative research (ac-qualitative-research-methods), not for product discovery and what-to-build (ac-product-management), not for quantitative survey design (ac-survey-research-methods).'
license: MIT
metadata:
  domain: software-engineering
status: seedling
---

# User research

## Overview

A product team can argue for months about what users want and learn more in one afternoon watching five of them try to use the thing. User research replaces assumption with observation: real people, real tasks, real struggles. Its two complementary modes are generative (understand users, their goals and their context, to inform what to build) and evaluative (test whether a design works, by watching users attempt tasks and measuring where they fail). The craft is not asking users what they want and building it, nor confirming that a design is fine; it is observing behaviour and letting that change the decision.

This skill owns that craft. Its neighbours carve the rest: ac-design-taste evaluates a design with expert judgement and heuristics; ac-qualitative-research-methods conducts open-ended qualitative studies; ac-product-management decides what to build; ac-survey-research-methods measures attitudes quantitatively. User research sits between them: empirical, task-focused, tied to a product decision. It never treats five participants as a population estimate, never lets a leading question script the answer, and never reports a usability score without the tasks and participants behind it.

Primary sources: <https://www.nngroup.com/articles/usability-testing-101/> and <https://en.wikipedia.org/wiki/Usability_testing>.

## When to use

- Before building, to understand users, their goals and their current alternatives.
- Before shipping, to test whether a design works by watching users attempt tasks.
- When a team argues about usability and needs observed evidence instead of opinion.
- When a product needs personas, journey maps or measured usability baselines.

## When NOT to use

- For expert heuristic evaluation and design critique (use ac-design-taste).
- For open-ended qualitative research questions (use ac-qualitative-research-methods).
- For product discovery and what-to-build decisions (use ac-product-management).
- For quantitative attitude measurement at scale (use ac-survey-research-methods).

## Subskill Index

| Leaf | Domain segment | Scope (one line) |
|---|---|---|
| `subskills/research-framing.md` | `software-engineering/research-framing` | Generative versus evaluative questions and when to test. |
| `subskills/usability-testing.md` | `software-engineering/usability-testing` | Task-based testing, think-aloud, moderated versus unmoderated. |
| `subskills/usability-metrics.md` | `software-engineering/usability-metrics` | Task success, time-on-task, errors, SUS and SEQ. |
| `subskills/interviews-and-personas.md` | `software-engineering/interviews-and-personas` | User interviews, personas and journey maps from evidence. |
| `subskills/recruiting-and-screening.md` | `software-engineering/recruiting-and-screening` | Recruiting representative participants and honest sample sizes. |
| `subskills/analysis-and-synthesis.md` | `software-engineering/analysis-and-synthesis` | Affinity mapping, severity ratings, findings to recommendations. |
| `subskills/research-record-and-ethics.md` | `software-engineering/research-record-and-ethics` | Consent, privacy, the research report and actionable findings. |

## Status and honest limits

Five users can reveal most severe usability problems in a design; they cannot tell you what proportion of your users will hit them. Qualitative findings identify and explain problems, they do not quantify their prevalence, and the record must never blur that line. Participants are not your users unless recruiting was honest about who you excluded, and a task that only your team understands measures your briefing, not your product. Personas and journey maps are synthesis tools that go stale; without fresh evidence they become the assumptions they replaced. Nothing here replaces statistical measurement at scale when a prevalence or comparison question needs a number, and a usability score means nothing without the tasks, participants and conditions it came from.
