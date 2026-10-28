---
name: domain-vocabulary
domain: skill-authoring/domain-vocabulary
trigger: "When minting a new top-level domain: segment for a skill, or checking a segment is legal."
anti_trigger: "The skill's domain chain reuses an existing top segment already in this enum."
scope: "The closed enum of legal top-level domain: segments; the only file allowed to define them."
status: "seedling"
---

# Domain Vocabulary (the closed enum)

This file owns the **closed enum** of legal top-level `domain:` segments. It is data, versioned, and the **only** file allowed to define legal top
segments. A leaf's `domain:` is `<top-segment>/<...>`; the linter rejects any top segment
not in this enum.

## Standard

An open vocabulary lets a leaf exit its parent's domain by naming a novel top segment —
defeating the in-domain constraint silently. A closed enum makes the
violation a linter error instead of a judgment call.

## The enum (top-level segments)

| top segment | governs | minted for |
|-------------|---------|-----------|
| `skill-authoring` | creating/decomposing/linting/vetting/install-gating skills-with-subskills | this meta-skill |
| `security-hardening` | application security, OWASP, privacy, supply-chain, LLM-security | ac-security-engineer (RSI pilot successor) |
| `research-operations` | multi-source deep-research: planning, retrieval, verification, synthesis, reporting | ac-deep-researcher |
| `prompt-engineering` | the craft of prompting models and agents: instruction design, patterns, evaluation, robustness, injection defense | ac-prompt-engineer |
| `rsi` | RESERVED — self-improvement observe/propose leaves (`00-rsi`) + the shared `ac-rsi` core; never a task/action domain | SPEC-rsi-skills (github.com/anoscranel/rsi-skills) |
| `software-engineering` | software lifecycle practice: requirements, design, construction, testing, delivery, operations, maintenance | ac-software-engineer pack |
| `writing` | non-fiction and professional writing process and genres, above sentence level | ac-writer pack |
| `collaboration` | transferring work between people, sessions, and agents: handoff artifacts, context selection, resumption checks | ac-handoff (v0.5.0) |
| `critical-thinking` | interrogating ideas, plans, and claims before commitment: assumption surfacing, failure mapping, evidence tests, alternatives, close-out | ac-interrogation (v0.5.0) |

The meta-skill's own chain is `skill-authoring`; the pilot's is `security-hardening`.

## Decision rules

- A skill whose domain fits an existing segment reuses that segment.
- No existing segment covers the domain → add exactly one row here, then lint.
- Keep segments coarse (a domain, not a topic); leaves add fine segments below the top
  via prefix-extension, which needs no enum entry.

## Procedure

1. Confirm no existing segment already covers the domain (dedup first).
2. Add one row: top segment | what it governs | the skill that minted it.
3. Re-run lint-tree on every authored tree that names a top segment.

## Anti-patterns

- Inventing a top segment inline in a leaf instead of editing THIS file.
- Adding a topic-level segment that a fine segment (prefix-extension) would cover.

## Done checklist

- New segment row committed; all authored trees lint PASS against the updated enum.

## Sources

- House standard for skills-with-subskills (unpublished).
- SPEC-rsi-skills (`rsi` reservation): https://github.com/anoscranel/rsi-skills