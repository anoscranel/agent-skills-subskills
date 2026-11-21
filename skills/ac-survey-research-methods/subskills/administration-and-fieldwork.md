---
name: administration-and-fieldwork
domain: research-operations/administration-fieldwork
trigger: "Running the fieldwork so the data collected matches the design."
anti_trigger: "Not for sampling design, and not for item wording."
scope: "Mode effects, interviewers, incentives, and field monitoring."
status: seedling
---

# Administration and fieldwork

## Standard

The best instrument fails in careless hands. Administration is how the survey reaches respondents, and each mode carries effects the analyst must know. Interviewer-administered surveys introduce interviewer effects: tone, pacing, and probing vary, and interviewers can influence answers, especially on sensitive items. Self-administered surveys remove the interviewer but place the burden on the respondent's reading and motivation. Mode also changes measurement — a question answered by phone may draw a different distribution than the same question on a screen.

Fieldwork is managed, not launched. Incentives raise response but must be proportionate and not coercive; the choice and amount are recorded. Contact attempts and follow-ups are scheduled, because a single contact misses most of the sample and biases toward the easy-to-reach. Reminders lift response rates substantially, but each wave is logged so late responders can be compared with early ones — late responders often resemble non-respondents and offer a cheap non-response check.

Monitoring runs throughout. Paradata — the record of the process itself, contact attempts, refusals, break-offs, timestamps, item-level drop-off — shows where the instrument fails in the field. A question with a high break-off rate is a defect found live. Fieldwork metrics are reviewed on a schedule, and the protocol is adjusted within the limits the design allows, with every change logged.

Primary sources: <https://unstats.un.org/unsd/hhsurveys/> and <https://www.pewresearch.org/our-methods/>.

## Decision rules

- Record the mode and its known effects on response and measurement.
- Train and monitor interviewers to reduce interviewer variance.
- Set incentives proportionate and non-coercive; record them.
- Schedule multiple contact attempts and follow-up reminders.
- Compare late responders with early ones as a non-response proxy.
- Review paradata on a schedule; log every protocol adjustment.

## Procedure

1. Choose administration procedures per mode.
2. Train interviewers; standardise probing and pacing.
3. Set the incentive and the contact-attempt schedule.
4. Field the survey with reminders; log every attempt.
5. Collect paradata: refusals, break-offs, timestamps, drop-off.
6. Review metrics; adjust within design limits and log changes.

## Anti-patterns

- A single contact attempt reported as the response rate.
- Untrained interviewers introducing variance.
- Incentives large enough to coerce or to attract only one group.
- No paradata, so field failures surface only at analysis.
- Unlogged mid-field protocol changes.

## Done checklist

- [ ] Mode and its effects recorded.
- [ ] Interviewers trained and monitored.
- [ ] Incentive proportionate and recorded.
- [ ] Contact attempts and reminders scheduled.
- [ ] Late-versus-early comparison planned.
- [ ] Paradata reviewed and adjustments logged.

## Sources

- UN household survey guidance: <https://unstats.un.org/unsd/hhsurveys/>
- Pew Research methods: <https://www.pewresearch.org/our-methods/>
- Survey methodology: <https://en.wikipedia.org/wiki/Survey_methodology>
