---
name: 00-rsi
domain: security-hardening/00-rsi
trigger: Always — passively, after any leaf in this skill fires, to log the event.
anti_trigger: Never blocks a task; never rewrites a file; never installs anything.
scope: Observe this skill's (security-engineer's) trigger/outcome events and queue typed edit proposals for THIS skill only. Acts on no other skill and on no shared core.
status: seedling
---

# RSI — self-improvement logger + proposer (this skill only)

This leaf NEVER edits a file, NEVER installs, and NEVER blocks a task. It only appends.
Append-only is a HARD rule of the RSI spec (§4 rule 1), not just an instruction.

## On every routing event (append-only)

If the operator has enabled RSI logging, append one line to the log path they configured (opencode default `~/.local/share/opencode/rsi/leaf-events.jsonl`, outside every skill tree). Never write a file inside a skill tree at run time. Schema: `ac-rsi/schema/log-schema.md` in https://github.com/anoscranel/rsi-skills.

```
{ ts, skill, leaf_routed, trigger_text, model, sessionID, callID }
```

This leaf NEVER edits, deletes, or truncates any file — including the log itself. The
`task_outcome` and `validator_verdict` fields are filled by the HARNESS or validator, NOT
by this skill — a skill never records its own outcome (SPEC-rsi-skills.md §4 rule 3).
Never log secrets, credentials or personal data; `trigger_text` is the index trigger, never the user's words.

## On demand (propose, never apply)

When the operator (or the shared `rsi` core, from Stage 2) runs an optimization pass, this
leaf surfaces the typed edit proposals queued for THIS skill as evidence cards. It does
NOT apply them. Every proposal goes to the human + validator gate (SPEC-rsi-skills.md §6). Prune-lane
proposals are the default; additive proposals get the strictest review.

## Stage 1 posture

Log-only. No proposals yet. This leaf exists to build the trustworthy, independently-
recorded log the Stage-1 gate requires (SPEC-rsi-skills.md §0 house-set thresholds, not derived from prior art: ≥100 events, ≥95% independent outcomes,
intact append-only, ≥30 days).
