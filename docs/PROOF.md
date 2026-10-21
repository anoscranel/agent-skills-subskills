---
id: proof-ledger
status: verified
created: 2026-10-20
---

# Proof ledger (what ran against this pack before it shipped)

## Quality gates (every skill, every file)

| Gate | Tool | Result |
|---|---|---|
| Structure lint | `lint_tree.py` (subskills family linter, this repo) | 36 PASS; domain chains checked, unique scopes, no leaf over 600 words (machine rule) |
| Adversarial scan | `skill_scan.py` (self-contained scanner, this repo) | 36 PASS; no delegation/cross-skill instruction lines |
| Install gate | `skill-install` scan (hosts install); script-only profile for the meta-skill | 36 PASS |
| Integrity lock | `skill-install verify` against the recorded tree hash | 36 of 36 OK after repair |

## Independent audit (findings/job-004-audit-report.md)

A fresh-context validator checked name/dir parity, staged-vs-installed equality, license declarations, citation integrity, human-gating, section rules, and domain-collision safety. Eleven defects were returned (names D1–D11) and resolved; the repair log is job-005.

## Routing evaluation (findings/job-004a/…; the frozen scores)

Every published skill's SKILL.md description went through a sealed router task stack (60 prompts per suite). The router sees only name + description; the label set is pre-registered and hash-frozen. Final test run: **58/60 correct first choice** against the full installed catalog (150 skills, including strong third-party applicants). The two misses are contested boundary takes (documented in that op board) rather than defects.

The publish set here targets names that the router test proved win their declared entrance phrases.

## What is NOT claimed

- No claim of upstream endorsements; this pack is independently authored.
- ⚠️ Paywalled primary standards (ISO / CMOS / APA proprietary text) carry the ⚠️ note inside the leaves that cite them.
- Two skills were deliberately excluded from this subject pack: `ac-deep-researcher` and `ac-security-engineer`/`ac-ac-security-standards` — they live in the same system but publish under a fragment/later release.
