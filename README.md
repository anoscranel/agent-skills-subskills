# agent-skills-subskills

An MIT-licensed family of Agent Skills for professional work: writing, software engineering, prompting, and one meta-skill that authors them all. Built and updated by Anos Cranel.

The pack ships three suites of craft skills and one author tool.

## What's here

```
skills/
  ac-<cluster>/SKILL.md      the agent-loadable entry point for the cluster
  ac-<cluster>/subskills/    flat depth-1 leaf files — each holds one standard's procedures
docs/
  the reference docs and the proof ledger (audit + routing tests)
```

Format: each `SKILL.md` is a routing index over its leaves. Every leaf carries a six-field header (name, domain, trigger, anti-trigger, scope, status) and six sections (Standard, Decision rules, Procedure, Anti-patterns, Done checklist, Sources), and is self-contained — it never hands the task to another skill. Every published skill passes a local lint, a security scan, an independent audit, and a routing evaluation before it lands; see `docs/PROOF.md`.

## Suites

### `ac-subskills-author` — the meta-skill

Builds and audits skill trees to this pack's own rules: research-gate, the closed-enum domain map, flat-or-nest routing rule (depth-1, 60-leaf budget), the delegation-free lint gate, staging behind a fail-closed install gate (you supply the installer; nothing is copied in by hand), and a routing evaluation per tree. It ships four stdlib-only Python checkers in `scripts/`: `lint_tree.py`, `skill_scan.py`, `route_score.py` and `tree_hash.py`.

### Software engineering (18 clusters)

spec-writing · task-planning · architecture · database-changes · code-construction · codebase-maintenance · testing · code-review · ci-and-release · reliability · performance · frontend-ui · debugging · api-design · git-workflow · agent-coding-governance · quality-verification · software-engineering-standards

Each covers the model professional's craft X with decision rules, a procedure, anti-patterns, and a done-checklist — sourced from SWEBOK v4, SWEBOK-aligned operations, Google's eng-practices set, SLSA's public specs, and the OWASP/ASVS lines, independently audited.

### Writer (13 clusters)

drafting · plain-language · voice-and-style · technical-writing · business-writing · persuasive-writing · proposal-writing · news-writing · narrative-writing · academic-writing · editing · evidence-and-citation · writing-standards

### `ac-prompt-engineer`

A 12-leaf working skill: decompose-the-task, instruction-form/topology, model knobs, tokens-and-capacity, prompt patterns with fallbacks, debug-prompt, eval-proof with seeded design, agent-harness's instructions, injection defense, RAG prompts, prompt libraries, multimodal dialects.

## Install

Each skill is a self-contained directory. In opencode or any harness that reads Agent Skills:

1. Pick the skill directory from `skills/ac-*/`.
2. Copy it into your harness's skills directory (commonly `~/.agents/skills/<skill-name>/` or a project-local `.agents/skills/`; check your harness's docs).
3. Restart the harness and confirm the skill is listed (opencode: `opencode debug skill`).

No third-party dependency: leaves are markdown with plain-YAML frontmatter. The only code is the four checker scripts in `skills/ac-subskills-author/scripts/`, which use the Python standard library only and run only when you call them. No skill ships hooks or install scripts.

## License

MIT — §LICENSE. All 33 + 1 skills © Anos Cranel 2026. The pack is a self-authored original: derived only from public-documented industry standards, our own research, and the runs of our desk; nothing has been copied from another repository's material.
