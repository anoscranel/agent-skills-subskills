---
name: ac-project-management
description: 'Running a project from initiation to closure: the project charter and success criteria, scope definition and work breakdown structure, scheduling and the critical path, estimation and budgeting, risk and issue management, stakeholder and communication planning, and monitoring, control and closure with lessons learned. It owns the project lifecycle; it never promises a delivery date without a basis and never lets scope grow unexamined. Use when asking "manage a project", "project charter", "work breakdown structure", "critical path", "project schedule", "estimate a project", "risk register", "earned value", "project stakeholder management", "project closure", "scope creep". Not for slicing an approved spec into tasks (ac-task-planning), not for deciding what product to build (ac-product-management), not for internal platform work (ac-platform-engineering), not for writing the feature spec (ac-spec-writing).'
license: MIT
metadata:
  domain: software-engineering
status: seedling
---

# Project management

## Overview

A project is temporary work with a defined beginning and end, a goal, and constraints. Managing it is the discipline of defining what success looks like, breaking the work into plannable units, sequencing them against time and resources, and steering the whole against change, risk and competing stakeholders. The craft is distinct from deciding what product to build (product management), slicing a spec into tasks (task planning), and writing the feature spec (spec writing): it owns the lifecycle from charter to closure.

The core tensions are always the same. Scope, time, cost and quality trade against each other, and you cannot fix all four. Plans are estimates, not promises, and the honest manager states confidence and contingency instead of a single heroic date. Scope creep is the default unless every addition is examined. Risk is managed before it happens, not after.

Primary sources: <https://en.wikipedia.org/wiki/Project_management> and <https://en.wikipedia.org/wiki/Project_charter>.

## When to use

- Initiating a project and writing its charter and success criteria.
- Breaking work into a WBS and sequencing it against a critical path.
- Estimating effort, building a budget, and setting contingency.
- Managing risks, issues, stakeholders, and project change.
- Monitoring progress with earned value and closing with lessons learned.

## When NOT to use

- For slicing an approved spec into tasks (use ac-task-planning).
- For deciding what product to build (use ac-product-management).
- For writing a feature specification (use ac-spec-writing).
- For coordinating a human team's day-to-day norms (use ac-team-collaboration).

## Subskill Index

| Leaf | Domain segment | Scope (one line) |
|---|---|---|
| `subskills/project-framing-and-charter.md` | `software-engineering/project-framing-and-charter` | Defining the project, its objectives and success criteria. |
| `subskills/scope-and-work-breakdown.md` | `software-engineering/scope-and-work-breakdown` | Scope definition and the work breakdown structure. |
| `subskills/scheduling-and-critical-path.md` | `software-engineering/scheduling-and-critical-path` | Dependencies, the critical path, and the schedule. |
| `subskills/estimation-and-budgeting.md` | `software-engineering/estimation-and-budgeting` | Estimation techniques, budget, and contingency. |
| `subskills/risk-and-issue-management.md` | `software-engineering/risk-and-issue-management` | The risk register, mitigation, and issue tracking. |
| `subskills/stakeholder-and-communication.md` | `software-engineering/stakeholder-and-communication` | Stakeholder analysis and the communication plan. |
| `subskills/monitoring-control-and-closure.md` | `software-engineering/monitoring-control-and-closure` | Earned value, change control, and project closure. |

## Status and honest limits

A plan is a model, not a commitment to reality. Estimates carry uncertainty, and a project managed to a single date without contingency is a project managed by hope. The critical path is only as accurate as the dependencies and durations fed into it. Earned value measures planned-versus-actual work, not whether the work was worth doing. The project record exists so that the next project estimates from evidence rather than optimism.
