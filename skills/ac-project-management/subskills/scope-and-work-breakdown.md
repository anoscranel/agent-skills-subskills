---
name: scope-and-work-breakdown
domain: software-engineering/scope-and-work-breakdown
trigger: "Defining project scope and decomposing it into a work breakdown structure."
anti_trigger: "Not for slicing a spec into development tasks, and not for scheduling."
scope: "Scope definition and the work breakdown structure."
status: seedling
---

# Scope and work breakdown

## Standard

Scope definition fixes what the project will and will not deliver, in terms specific enough that a later dispute can be settled by reading it. The work breakdown structure then decomposes the total scope into a hierarchy of deliverables, descending until each work package is small enough to estimate, assign and control. The WBS is deliverable-oriented, not a task list: it answers "what must be produced", leaving "how and when" to the schedule.

The discipline is the one-hundred-percent rule: the WBS captures all the work, and only the work, of the project. Each level decomposes its parent completely, and nothing outside the project's scope appears. Work packages sit at the bottom, each with a clear owner and a deliverable that can be verified as done. Scope creep is controlled by measuring every proposed addition against the WBS baseline and routing it through change control rather than absorbing it quietly.

Primary sources: <https://en.wikipedia.org/wiki/Work_breakdown_structure> and <https://en.wikipedia.org/wiki/Project_management>.

## Decision rules

- Define scope in terms specific enough to settle later disputes.
- Decompose by deliverable, not by activity; the WBS answers "what", not "how".
- Apply the one-hundred-percent rule: all the work, and only the work.
- Stop decomposing when a work package is estimable, assignable and verifiable.
- Treat the approved WBS as the scope baseline; changes go through change control.
- Assign every work package a single accountable owner.

## Procedure

1. Write the scope statement with deliverables and exclusions.
2. Decompose top-level deliverables into smaller components.
3. Continue until each work package is estimable and verifiable.
4. Check each level against the one-hundred-percent rule.
5. Assign owners and done-criteria to each work package.
6. Baseline the WBS and route additions through change control.

## Anti-patterns

- A WBS written as a list of activities instead of deliverables.
- Decomposing so far that packages become unmanageable overhead.
- Missing work discovered late because the rule was not applied.
- Absorbing additions without examining their effect on scope.
- Work packages with no owner or no verifiable done state.

## Done checklist

- [ ] Scope statement written with exclusions.
- [ ] WBS decomposed by deliverable.
- [ ] One-hundred-percent rule checked at each level.
- [ ] Work packages estimable and verifiable.
- [ ] Owners and done-criteria assigned.
- [ ] WBS baselined under change control.

A useful test for the WBS is whether an outsider could read it and understand exactly what will be produced. If a work package cannot be shown to a sponsor as a finished thing, it is probably an activity in disguise and belongs in the schedule instead. The WBS and the schedule are deliberately separate artifacts: confusing them produces a plan that is detailed about activity and vague about deliverables, which is the opposite of what controls a project.

## Sources

- Work breakdown structure: <https://en.wikipedia.org/wiki/Work_breakdown_structure>
- Project management: <https://en.wikipedia.org/wiki/Project_management>
- Scope creep: <https://en.wikipedia.org/wiki/Scope_creep>
