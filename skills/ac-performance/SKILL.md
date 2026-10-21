---
name: ac-performance
description: "Making software fast, server and browser: measure-first performance budgets, percentile targets, profiling and flame graphs, load and soak tests, N+1 and caching fixes, plus Core Web Vitals — LCP, INP, CLS — bundle cost and field versus lab data. Use when asking \"this is slow\", \"profile this\", \"p99 latency is too high\", \"set a performance budget\", \"load test this API\", \"improve LCP\", \"fix layout shift\", \"pass Core Web Vitals\", \"the bundle is too big\". Not for SLO definition, alerting, outage response, or UI structure; those sit outside this skill."
license: MIT
metadata:
  domain: software-engineering
---

# Performance

## Overview

Two leaves make software fast. One covers the server side: written budgets, measurement before change, profiling, load and soak tests, and the fix order from algorithm to cache. The other covers the browser: Core Web Vitals targets, bundle and render cost, and the field-versus-lab evidence split.

## When to use

- Slowness suspects: setting a budget, reproducing with realistic data, profiling.
- Hot spots: widest stacks, slow queries, N+1 loops, caching with invalidation.
- Load, stress, spike and soak tests; CI thresholds that fail the build.
- Web vitals work: LCP, INP, CLS, bundle splitting, third-party script cost.

## When not to use

- Setting SLOs, error budgets or alert rules — outside this skill.
- Adding telemetry so the system can be measured — outside this skill.
- Component structure and state placement — outside this skill.

## Precedence

> The deepest loaded instruction governs its uniquely-claimed scope; every `scope:` string is claimed by exactly one file in this tree; no leaf may widen a prohibition declared by an ancestor — leaves narrow, never override upward.

## Subskill index

| Leaf | Task | Trigger |
|---|---|---|
| `subskills/performance.md` | Measure-first server speed work | "this is slow" |
| `subskills/web-performance.md` | Core Web Vitals and bundle cost | "improve LCP" |

## See also

- `subskills/performance.md` — measure, then move the needle.
- `subskills/web-performance.md` — the p75 the user actually feels.
