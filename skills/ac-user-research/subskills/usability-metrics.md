---
name: usability-metrics
domain: software-engineering/usability-metrics
trigger: "Measuring usability with task and questionnaire metrics."
anti_trigger: "Not for open-ended thematic analysis, and not for product analytics at scale."
scope: "Task success, time-on-task, errors, SUS and SEQ."
status: seedling
---

# Usability metrics

## Standard

Usability has measurable dimensions, and naming them separates a finding from a vibe. Effectiveness: task success rate, the share of participants who complete the task, with partial and assisted completions coded explicitly. Efficiency: time-on-task and error count. Satisfaction: a short standardised questionnaire. The System Usability Scale gives a single 0-100 score from ten items; the Single Ease Question gives a one-item task-difficulty rating. These are comparable across designs and over time when the tasks and participants are held roughly constant.

The honesty rule is what a small sample can and cannot support. A task success rate from five participants is a rough signal about severe problems, not a prevalence estimate with a confidence interval; a SUS score from the same five is a directional reading, not a benchmark result. Metrics are reported with their tasks, participants and conditions, and a score quoted without them is decoration. The point of a metric is comparison, against a prior version or a rival design, under matched conditions.

Primary sources: <https://measuringu.com/sus/> and <https://en.wikipedia.org/wiki/System_usability_scale>.

## Decision rules

- Measure effectiveness (task success), efficiency (time, errors) and satisfaction (questionnaire).
- Code partial and assisted completions explicitly, never as clean successes.
- Use a standard instrument (SUS, SEQ) rather than inventing a scale.
- Report every metric with its tasks, participants and conditions.
- Treat small-sample metrics as directional signals, not prevalence estimates.
- Compare against a baseline or rival under matched conditions.

## Procedure

1. Define the success criterion per task before testing.
2. Record success, time and errors per participant per task.
3. Administer the standard questionnaire after the session.
4. Score the instrument per its published method.
5. Compare against baseline or rival under matched conditions.
6. Report metrics with tasks, participants, conditions and sample size.

## Anti-patterns

- Quoting a SUS score with no tasks or sample size attached.
- Treating a five-person success rate as a population percentage.
- Inventing a home-made satisfaction scale when a standard one exists.
- Counting assisted completions as successes.
- Comparing scores collected under different tasks or conditions.

## Done checklist

- [ ] Success, time and errors recorded per task.
- [ ] Partial and assisted completions coded.
- [ ] Standard instrument used and scored per its method.
- [ ] Metrics reported with tasks, participants and conditions.
- [ ] Small-sample results labelled directional.
- [ ] Comparison made under matched conditions.

## Sources

- System Usability Scale and scoring: <https://measuringu.com/sus/>
- System Usability Scale: <https://en.wikipedia.org/wiki/System_usability_scale>
- Usability and its measurement: <https://en.wikipedia.org/wiki/Usability>
