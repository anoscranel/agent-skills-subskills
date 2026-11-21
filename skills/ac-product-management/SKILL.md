---
name: ac-product-management
description: 'Deciding what to build before you build it: product discovery and problem framing, customer discovery and evidence, prioritisation frameworks (RICE, WSJF, Kano), outcome-based roadmapping, MVP scoping and dual-track discovery and delivery, product metrics and the north-star metric, and the product decision record. It owns the discover-and-decide layer that precedes specification; it never substitutes a feature list for a strategy and never ships on opinion over evidence. Use when asking "what should we build", "product discovery", "jobs to be done", "prioritise the roadmap", "RICE scoring", "MVP scope", "north star metric", "product strategy", "dual-track agile". Not for writing the spec for a decided feature (ac-spec-writing), not for breaking an approved spec into tasks (ac-task-planning), not for controlled A/B experiments (ac-online-experiments), not for product event instrumentation (ac-product-analytics-instrumentation).'
license: MIT
metadata:
  domain: software-engineering
status: seedling
---

# Product management

## Overview

Product management is the craft of deciding what is worth building, for whom, and in what order — before a line of specification is written. It is the layer that answers "why this, why now, why these users" and then proves the answer with evidence rather than seniority. Done well it produces a prioritised, outcome-framed direction the rest of the pipeline can execute; done badly it produces a feature list that confuses motion with progress.

This skill owns the discover-and-decide layer. Its neighbours own the stages around it: ac-spec-writing turns a decided feature into requirements; ac-task-planning breaks an approved spec into work; ac-online-experiments runs controlled tests; ac-product-analytics-instrumentation wires the events that measure behaviour. The product craft here is upstream of all of them: choosing the opportunity, gathering evidence, prioritising, framing outcomes, scoping the smallest test, and deciding what success means.

Primary sources: <https://www.svpg.com/> and <https://www.producttalk.org/>.

## When to use

- Deciding what to build, for whom, and in what order.
- Framing a problem and testing it with customers before committing.
- Prioritising a backlog or building an outcome-based roadmap.
- Scoping an MVP or setting up discovery alongside delivery.
- Defining the north-star metric and the measures of success.

## When NOT to use

- For writing requirements for a decided feature (use ac-spec-writing).
- For breaking an approved spec into ordered tasks (use ac-task-planning).
- For controlled A/B or randomised experiments (use ac-online-experiments).
- For event taxonomy and analytics instrumentation (use ac-product-analytics-instrumentation).

## Subskill Index

| Leaf | Domain segment | Scope (one line) |
|---|---|---|
| `subskills/product-discovery-and-framing.md` | `software-engineering/product-discovery-and-framing` | Framing the opportunity and the problem worth solving. |
| `subskills/customer-discovery-and-evidence.md` | `software-engineering/customer-discovery-and-evidence` | Testing the problem with customers, evidence over opinion. |
| `subskills/prioritization-frameworks.md` | `software-engineering/prioritization-frameworks` | Ranking opportunities with explicit, evidence-weighted frameworks. |
| `subskills/roadmapping-and-outcomes.md` | `software-engineering/roadmapping-and-outcomes` | Outcome-based roadmaps over feature lists. |
| `subskills/mvp-and-dual-track.md` | `software-engineering/mvp-and-dual-track` | Scoping the smallest test; discovery alongside delivery. |
| `subskills/product-metrics-and-north-star.md` | `software-engineering/product-metrics-and-north-star` | North-star metric, input metrics, and success criteria. |
| `subskills/product-record-and-decisions.md` | `software-engineering/product-record-and-decisions` | The written product decision record and assumptions log. |

## Status and honest limits

Product craft improves the odds of building the right thing; it never guarantees a product succeeds. Prioritisation frameworks structure judgment, they do not replace it, and a RICE score is only as honest as the evidence estimates behind it. Customer discovery reduces but never eliminates the risk of building the wrong thing — people say one thing and do another, so stated preference must be checked against behaviour. A north-star metric aligns a team but can be gamed, and a roadmap is a statement of intent that must change as evidence arrives, not a promise. Nothing here substitutes for the decision-maker's accountability for the call.
