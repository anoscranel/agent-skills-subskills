---
name: scheduling-and-critical-path
domain: software-engineering/scheduling-and-critical-path
trigger: "Building the project schedule and finding the critical path."
anti_trigger: "Not for task-level sprint planning, and not for estimation."
scope: "Dependencies, the critical path, and the schedule."
status: seedling
---

# Scheduling and critical path

## Standard

The schedule sequences the work packages against time, using the dependencies between them. The critical path is the longest chain of dependent activities: the sequence that determines the shortest possible project duration. Any delay on the critical path delays the whole project; delay off the critical path is absorbed by float. Knowing which activities are critical is what lets a manager protect the dates that actually matter.

Dependencies are recorded honestly. Finish-to-start is the common case, but start-to-start and finish-to-finish exist, and external dependencies on things the team does not control are named explicitly because they are where schedules break. The critical path is recalculated whenever durations or dependencies change, because it shifts. Compressing a schedule means shortening the critical path, by fast-tracking work in parallel or crashing it with added resource, each with a stated cost and risk.

Primary sources: <https://en.wikipedia.org/wiki/Critical_path_method> and <https://en.wikipedia.org/wiki/Gantt_chart>.

## Decision rules

- Sequence work by real dependencies, not by the order tasks were listed.
- Identify the critical path and protect its dates; off-path float absorbs delay.
- Recalculate the critical path whenever durations or dependencies change.
- Name external dependencies explicitly and track them as risks.
- Compress only the critical path; state the cost and risk of fast-tracking or crashing.
- Present the schedule with milestones and a baseline for later variance measurement.

## Procedure

1. List work packages and estimate each one's duration.
2. Record dependencies and their types between packages.
3. Build the network and compute the critical path and float.
4. Mark milestones and baseline the schedule.
5. Identify external dependencies and assign them owners.
6. Recalculate the path on every material change.

## Anti-patterns

- Treating every activity as equally important to the end date.
- A schedule built by listing tasks in the order they occurred to someone.
- Assuming the critical path is fixed once computed.
- Compressing non-critical work while the critical path is untouched.
- External dependencies left implicit until they slip.

## Done checklist

- [ ] Durations estimated per package.
- [ ] Dependencies and types recorded.
- [ ] Critical path and float computed.
- [ ] Milestones marked and schedule baselined.
- [ ] External dependencies owned and tracked.
- [ ] Recalculation triggered on change.

Float is worth managing explicitly, not just computing. Total float is the delay an activity can absorb without moving the project end date, and free float is the delay it can absorb without delaying its successors. Where float is small, a minor slip becomes a schedule problem quickly, so those near-critical chains deserve the same watching as the critical path itself. Reporting float alongside the path tells the team where the schedule is fragile.

## Sources

- Critical path method: <https://en.wikipedia.org/wiki/Critical_path_method>
- Gantt chart: <https://en.wikipedia.org/wiki/Gantt_chart>
- Project management: <https://en.wikipedia.org/wiki/Project_management>
