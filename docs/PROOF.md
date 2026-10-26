# Proof ledger

What was checked before this release, what passed, and what was not checked. Re-run the first three rows yourself; commands are given.

## Gates you can re-run (v0.4.0)

| Gate | Command (from the repo root) | Result |
|---|---|---|
| Structure lint | `python3 -B skills/ac-subskills-author/scripts/lint_tree.py skills/<name>` | 38 of 38 PASS |
| Security scan | `python3 -B skills/ac-subskills-author/scripts/skill_scan.py skills/<name>` | 38 of 38 PASS |
| Strict YAML, every file | `yaml.safe_load` on every frontmatter block in the pack (SKILL.md and leaves) | 218 of 218 PASS (v0.4.0) |
| Spec frontmatter | Strict YAML parse; `name` matches dir and `^[a-z0-9]+(-[a-z0-9]+)*$`; `description` 1–1024 chars; only spec keys (`name`, `description`, `license`, `metadata`) | 38 of 38 PASS |

The skill's own domain lives in `metadata.domain`, per the [Agent Skills spec](https://agentskills.io/specification), which reserves top-level keys.

## Checks run before release (evidence not shipped)

- **Routing evaluation, 31 of 33 skills.** A blind router saw only each skill's name and description, among about 150 installed skills, and picked a skill for each of 60 pre-registered tasks. Result: 58 of 60 correct at top 1. The 2 misses sit on contested boundaries with third-party skills. All 9 out-of-scope tasks were correctly routed to no skill. A second test routed tasks to leaves inside the software and writing suites: 24 of 24 and 24 of 24.
- **All 38 skills routing-tested (v0.4.0).** Four sealed blind runs: 31 of 33 skills at v0.2.2 (58 of 60 top-1, 9 of 9 negatives); the 2 remaining skills of that era at 12 of 12 (`ac-prompt-engineer`) and 10 of 10 (`ac-subskills-author`) with 2 of 2 negatives; the 2 skills added in v0.3.0 at 10 of 10 and 8 of 8 content tasks with 3 of 4 negatives; and the 3 skills added in v0.4.0 against 26 pre-registered tasks and a 66-entry frozen catalog carrying a real description for every entry (all three files hashed before the run): `ac-dataviz` 8 of 8, `ac-security-engineer` 7 of 8, `ac-deep-researcher` 5 of 6 top-1, and 4 of 4 out-of-scope tasks answered `none`. Of the 24 hits, 2 matched a declared accepted alternate rather than the expected skill. Two tasks missed: one sits at rank 2 (incident response, which overlaps `ac-reliability`), the other at neither rank (archiving a study, which overlaps `ac-findings-ceiling-format`).
- **Independent audits.** Two fresh-context auditors reviewed the pack before and after the first release. The second audit found 28 defects: false README claims, code samples with stripped `()` and indentation, private references, and non-strict YAML. v0.2.0 fixes them; see [CHANGELOG.md](../CHANGELOG.md).

The routing and audit records live in the author's private notes. Treat these results as the author's report, not as reproducible evidence.

## Limits

- Leaves cite public sources. Paywalled standards (ISO, CMOS, APA and similar) are cited, not quoted, and carry a ⚠️.
- A spot check of 18 load-bearing claims against primary sources found 11 exact matches, 2 arithmetic slips (fixed), 1 dead link (replaced), 1 broken code sample (fixed) and 3 that could not be checked (paywall or blocked page).
- No upstream endorsement is claimed.
- The longest leaf body is 568 words (`ac-editing/subskills/revision-line.md`, 612 with its frontmatter); no linter caps length.
