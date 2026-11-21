---
name: usability-testing
domain: software-engineering/usability-testing
trigger: "Running a task-based usability test with real users."
anti_trigger: "Not for open-ended interviews, and not for expert heuristic review."
scope: "Task-based testing, think-aloud, moderated versus unmoderated."
status: seedling
---

# Usability testing

## Standard

A usability test watches a real user attempt real tasks with the product and records where they succeed, struggle and fail. The method is observation, not opinion: the participant works through tasks while thinking aloud, and the facilitator notes behaviour, hesitations, errors and comments. What users do outweighs what they say they would do, and a task completed confidently wrong is a finding, not a pass.

The discipline is in the tasks and the neutrality. Tasks describe a goal in the user's language, not a click-path through the interface, and they use realistic scenarios rather than leading instructions. The facilitator does not teach, rescue or defend the design; a test that helps the participant succeed measures the help, not the product. Moderated testing allows probing the why behind behaviour; unmoderated testing scales and removes facilitator influence but loses the follow-up question. Remote and in-person trade richness for reach, and a prototype tests the flow it simulates, not the polish it omits.

Primary sources: <https://www.nngroup.com/articles/usability-testing-101/> and <https://en.wikipedia.org/wiki/Think_aloud_protocol>.

## Decision rules

- Write tasks as user goals in realistic scenarios, never as click instructions.
- Facilitator stays neutral: no teaching, rescuing or defending the design.
- Participant thinks aloud; behaviour is recorded over stated preference.
- Choose moderated for probing the why, unmoderated for scale and less bias.
- Test the highest-risk or highest-traffic flows first.
- A wrong-but-confident completion is a finding, not a pass.

## Procedure

1. Define the flows and tasks that carry the most risk.
2. Write each task as a realistic user goal with a success criterion.
3. Recruit participants who match the target users.
4. Run the session: neutral facilitation, think-aloud, observe and note.
5. Record success, errors, hesitations and verbatim comments per task.
6. Debrief on observed behaviour, not on whether they liked it.

## Anti-patterns

- Tasks that read as a guided tour of the interface.
- Rescuing the participant and recording a success.
- Asking "do you like it" instead of watching what they do.
- Testing trivial flows while the risky one goes untested.
- Treating a confident wrong answer as task success.

## Done checklist

- [ ] Tasks written as goals with success criteria.
- [ ] Neutral facilitation maintained.
- [ ] Think-aloud captured.
- [ ] Moderated/unmoderated chosen for the question.
- [ ] Behaviour recorded per task.
- [ ] Wrong-confident completions logged as findings.

## Sources

- Usability testing method: <https://www.nngroup.com/articles/usability-testing-101/>
- Think-aloud protocol: <https://en.wikipedia.org/wiki/Think_aloud_protocol>
- Usability testing practice: <https://en.wikipedia.org/wiki/Usability_testing>
