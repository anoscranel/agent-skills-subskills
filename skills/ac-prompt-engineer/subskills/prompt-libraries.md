---
name: prompt-libraries
domain: prompt-engineering/prompt-libraries
trigger: When prompts multiply past a handful and need versioning, testing, distribution, or meta-prompt maintenance.
anti_trigger: A single prompt under active drafting, or evaluating one specific change.
scope: Running a prompt library: folder-per-prompt layout, metadata, co-located tests, CI gates, distribution formats, and meta-prompt audits.
status: seedling
---

# Meta-prompt libraries and prompt lifecycle

## The standard

Power-user libraries converge on git-tracked, folder-per-prompt layouts with YAML
frontmatter: identifier, version, category, tags, provenance with source and license,
and a recorded eval score. Categories work
best as a verb taxonomy (`analyze_paper`, `extract_wisdom`), because verbs are mutually
exclusive where topics overlap. Co-locate tests with each prompt: at least three eval
cases in a sibling config, plus a regression baseline (library-systems §2). Treat
prompts like code: immutable versions, human-readable aliases (prod, staging) as the
only moving pointers, rollbacks as alias switches. Distribute through open formats: an
Agent Skills folder for capability sharing, or the MCP Prompts primitive so any client
discovers the library without code changes (library-systems §3).

## Meta-prompting, safely

A strong model can audit a prompt for contradictions, dead rules, and invalid tool
calls; OpenAI's GPT-5 prompting guide recommends exactly this audit pattern
(https://platform.openai.com/docs/guides/gpt-5-prompting). The audit is a draft, not a
verdict: adopt a suggested change only after it moves the golden set (see this skill's
eval leaf). Otherwise you have automated folklore generation.

## Procedure

1. One folder per prompt; `prompt.md` plus frontmatter plus test fixtures.
2. Declare the category verb list once; new prompts file under an existing verb or
 propose a new one.
3. Version on every edit that changes behavior; retest against the stored baseline.
4. Gate merges in CI: schema validity, golden-set pass rate, lint on the frontmatter.
5. Tag one alias per environment; never edit "prod" content in place.
6. Run a model self-audit quarterly; adopt findings only through the eval gate.

## Anti-patterns

- One shared "prompts.txt" graveyard; no ownership, no tests, no rollback.
- Library entries with no provenance; licensing and reuse become untraceable.
- Adopting meta-prompt rewrites unmeasured because they read well.
- Versioning via filenames like `final_v2_REAL.md`; use versioned folders or tags.

## Done checklist

- [ ] Every prompt has frontmatter with version, category, provenance.
- [ ] Each prompt folder carries its own test fixtures and baseline.
- [ ] CI blocks a merge that drops the golden-set pass rate.
- [ ] Rollback is an alias switch, tested once per quarter.
