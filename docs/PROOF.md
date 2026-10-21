# Proof ledger

What was checked before this release, what passed, and what was not checked. Re-run the first three rows yourself; commands are given.

## Gates you can re-run (v0.2.0)

| Gate | Command (from the repo root) | Result |
|---|---|---|
| Structure lint | `python3 -B skills/ac-subskills-author/scripts/lint_tree.py skills/<name>` | 33 of 33 PASS |
| Security scan | `python3 -B skills/ac-subskills-author/scripts/skill_scan.py skills/<name>` | 33 of 33 PASS |
| Spec frontmatter | Strict YAML parse; `name` matches dir and `^[a-z0-9]+(-[a-z0-9]+)*$`; `description` 1–1024 chars; only spec keys (`name`, `description`, `license`, `metadata`) | 33 of 33 PASS |

The skill's own domain lives in `metadata.domain`, per the [Agent Skills spec](https://agentskills.io/specification), which reserves top-level keys.

## Checks run before release (evidence not shipped)

- **Routing evaluation, 31 of 33 skills.** A blind router saw only each skill's name and description, among about 150 installed skills, and picked a skill for each of 60 pre-registered tasks. Result: 58 of 60 correct at top 1. The 2 misses sit on contested boundaries with third-party skills. All 9 out-of-scope tasks were correctly routed to no skill. A second test routed tasks to leaves inside the software and writing suites: 24 of 24 and 24 of 24.
- **Not routing-tested:** `ac-prompt-engineer` and `ac-subskills-author`. Since that test, descriptions were re-quoted for strict YAML, and `ac-subskills-author`'s description was reworded.
- **Independent audits.** Two fresh-context auditors reviewed the pack before and after the first release. The second audit found 28 defects: false README claims, code samples with stripped `()` and indentation, private references, and non-strict YAML. v0.2.0 fixes them; see [CHANGELOG.md](../CHANGELOG.md).

The routing and audit records live in the author's private notes. Treat these results as the author's report, not as reproducible evidence.

## Limits

- Leaves cite public sources. Paywalled standards (ISO, CMOS, APA and similar) are cited, not quoted, and carry a ⚠️.
- A spot check of 18 load-bearing claims against primary sources found 11 exact matches, 2 arithmetic slips (fixed), 1 dead link (replaced), 1 broken code sample (fixed) and 3 that could not be checked (paywall or blocked page).
- No upstream endorsement is claimed.
- The longest leaf is 613 words; no linter caps length.
