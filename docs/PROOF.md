# Proof ledger

What was checked before this release, what passed, and what was not checked. Re-run the first three rows yourself; commands are given.

## Gates you can re-run (v0.8.0)

| Gate | Command (from the repo root) | Result |
|---|---|---|
| Structure lint | `python3 -B skills/ac-subskills-author/scripts/lint_tree.py skills/<name>` | 47 of 47 PASS |
| Security scan | `python3 -B skills/ac-subskills-author/scripts/skill_scan.py skills/<name>` | 47 of 47 PASS |
| Strict YAML, every file | `yaml.safe_load` on every frontmatter block in the pack (SKILL.md and leaves) | 285 of 285 PASS (v0.8.0) |
| Spec frontmatter | Strict YAML parse; `name` matches dir and `^[a-z0-9]+(-[a-z0-9]+)*$`; `description` 1–1024 chars; only spec keys (`name`, `description`, `license`, `metadata`) | 47 of 47 PASS |

The skill's own domain lives in `metadata.domain`, per the [Agent Skills spec](https://agentskills.io/specification), which reserves top-level keys.

## Checks run before release (evidence not shipped)

- **Routing evaluation, 31 of 33 skills.** A blind router saw only each skill's name and description, among about 150 installed skills, and picked a skill for each of 60 pre-registered tasks. Result: 58 of 60 correct at top 1. The 2 misses sit on contested boundaries with third-party skills. All 9 out-of-scope tasks were correctly routed to no skill. A second test routed tasks to leaves inside the software and writing suites: 24 of 24 and 24 of 24.
- **All 47 skills routing-tested (v0.8.0).** Eight sealed blind runs: 31 of 33 skills at v0.2.2 (58 of 60 top-1, 9 of 9 negatives); the 2 remaining skills of that era at 12 of 12 (`ac-prompt-engineer`) and 10 of 10 (`ac-subskills-author`) with 2 of 2 negatives; the 2 skills added in v0.3.0 at 10 of 10 and 8 of 8 content tasks with 3 of 4 negatives; the 3 skills added in v0.4.0 at 8 of 8, 7 of 8 and 5 of 6 top-1 with 4 of 4 negatives (26 pre-registered tasks, 66-entry catalog); the 3 skills added in v0.5.0 at 8 of 8 (`ac-interrogation`), 7 of 7 (`ac-handoff`) and 5 of 5 (`ac-security-standards`) top-1 with 4 of 4 out-of-scope tasks answered `none` (24 pre-registered tasks, 68-entry frozen catalog); and the 2 skills added in v0.6.0 at 6 of 6 (`ac-adversarial-corpus-challenge`) and 5 of 6 (`ac-release-publish`) top-1 with 4 of 4 out-of-scope tasks answered `none` (16 pre-registered tasks, 68-entry frozen catalog, files hashed before the run); and the 2 skills added in v0.7.0 at 7 of 7 (`ac-ideation`) and 7 of 7 (`ac-inbound-triage`) top-1 with 4 of 4 out-of-scope tasks answered `none`, zero alternates needed (18 pre-registered tasks, 70-entry frozen catalog, files hashed before the run); and the 2 skills added in v0.8.0 at 7 of 7 (`ac-skill-adoption`) and 7 of 7 (`ac-mcp-authoring`) top-1 with 4 of 4 out-of-scope tasks answered `none`, zero alternates needed (18 pre-registered tasks, 72-entry frozen catalog, files hashed before the run). Documented misses from earlier runs remain contested boundaries, recorded in the PROOF history and the author's board.
- **Independent audits.** Two fresh-context auditors reviewed the pack before and after the first release. The second audit found 28 defects: false README claims, code samples with stripped `()` and indentation, private references, and non-strict YAML. v0.2.0 fixes them; see [CHANGELOG.md](../CHANGELOG.md).

The routing and audit records live in the author's private notes. Treat these results as the author's report, not as reproducible evidence.

## Limits

- Leaves cite public sources. Paywalled standards (ISO, CMOS, APA and similar) are cited, not quoted, and carry a ⚠️.
- A spot check of 18 load-bearing claims against primary sources found 11 exact matches, 2 arithmetic slips (fixed), 1 dead link (replaced), 1 broken code sample (fixed) and 3 that could not be checked (paywall or blocked page).
- No upstream endorsement is claimed.
- The longest leaf body is 568 words (`ac-editing/subskills/revision-line.md`, 612 with its frontmatter); no linter caps length.
