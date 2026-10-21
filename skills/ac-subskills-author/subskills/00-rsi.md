---
name: 00-rsi
domain: rsi
trigger: Always — passively, after any leaf in this skill fires, to log the event.
anti_trigger: Never blocks a task; never rewrites a file; never installs anything.
scope: Observe this skill's (ac-subskills-author's) trigger/outcome events and queue typed edit proposals for THIS skill only. Acts on no other skill and on no shared core.
status: seedling
---

# RSI — self-improvement logger + proposer (this skill only)

This leaf NEVER edits a file, NEVER installs, and NEVER blocks a task. It only appends
and proposes. Append-only is a HARD rule (SPEC-rsi-skills.md §4 rule 1), not just an instruction.

## Standard

Stage 1 posture is log-only. One append-only event log lives outside every skill tree; the
`task_outcome` and `validator_verdict` fields are filled by the HARNESS or validator, NOT
by this skill — a skill never records its own outcome (SPEC-rsi-skills.md §4 rule 3). The
Stage-1 gate thresholds are ≥100 events, ≥95% independent outcomes, intact append-only,
≥30 days (SPEC-rsi-skills.md §0 house-set thresholds, not derived from prior art).

## Decision rules

- Every routing event in THIS skill → append one line (never batch, never skip).
- An optimization pass (run by the operator, or the shared `ac-rsi` core from Stage 2) →
 surface this skill's queued typed edit proposals as evidence cards. Never apply them.
- Prune-lane proposals are the default; additive proposals get the strictest review.

## Procedure

1. Append one line to `~/.local/share/opencode/rsi/leaf-events.jsonl` (outside every skill
 tree) with `{ ts, skill, leaf_routed, model, sessionID }`:

```
{ ts, skill, leaf_routed, model, sessionID }
```

2. Never write a file inside a skill tree at run time.
3. On demand, hand the queued proposals for THIS skill to the human + validator gate
 (SPEC-rsi-skills.md §6). Apply nothing yourself.

## Anti-patterns

- Editing, deleting or truncating ANY file — including the log itself.
- Logging secrets, credentials or personal data; `trigger_text` is the index trigger,
 never the user's words.
- Recording this skill's own outcome, or acting on another skill or the shared core.

## Done checklist

- One jsonl line per routing event, schema-conformant, appended, never rewritten.
- Proposals surface as evidence cards only; zero self-applied edits.

## Sources

- SPEC-rsi-skills (the rsi-skills op spec; internal, §0/§4/§6/§7).
- Event schema: `~/.agents/skills/ac-rsi/schema/log-schema.md`.
