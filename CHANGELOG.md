# Changelog

All notable changes to this pack. Versions follow [SemVer](https://semver.org/).

## 0.4.0 — 2026-10-26

### Added
- `ac-dataviz` (writing): chart judgment — claim-first design, chart selection by comparison type, perceptual accuracy, colour and accessibility, annotation, small multiples, misleading patterns, a pre-publish chart review. 8 leaves.
- `ac-security-engineer` (security-hardening, 29 leaves): threat modelling through incident response, OWASP/ASVS-anchored, with its private research references removed for publication.
- `ac-deep-researcher` (research-operations, 13 leaves): question scoping, plan, retrieval, claim verification, evidence cards and incremental archiving.
- All three passed a sealed blind routing run (8 of 8, 7 of 8, 5 of 6 content tasks at top 1; 4 of 4 out-of-scope tasks answered `none`) before release.

The pack is now 38 skills, 180 leaves.

## 0.3.1 — 2026-10-26

### Changed
- Every frontmatter block in the pack now parses as strict YAML. In the 103 rewritten files `description`, `trigger`, `anti_trigger`, `scope` and `status` are quoted scalars, and wrapped continuation lines are joined. 103 files changed; no prose changed. In 52 of them the only body difference is one blank line after the closing `---`.
- `lint_tree.py` still reads leaf headers line by line, so nothing about routing or the domain chain changed.

## 0.3.0 — 2026-10-26

### Added
- `ac-design-taste` (software-engineering): judging and critiquing UI quality — critique protocol, typography, spacing, color and WCAG contrast math, heuristic evaluation, AI-slop anti-patterns, a 0-10 rubric, a taste practice loop. 8 leaves.
- `ac-slide-decks` (writing): slide-deck craft — brief and audience, narrative spine, slide grammar, chart-per-claim, density and reading, type and media for projection, exported-deck accessibility, pre-send QA. 8 leaves.
- Both passed a sealed blind routing run (10/10 and 8/8 top-1, 3/4 negatives) before release.
- Leaf frontmatter in the new skills is strict YAML (`trigger`, `anti_trigger`, `scope` quoted).

The pack is now 35 skills, 130 leaves.

## 0.2.2 — 2026-10-24

### Changed
- PROOF: `ac-prompt-engineer` and `ac-subskills-author` are now routing-tested (12 of 12 and 10 of 10 top-1, 2 of 2 negatives). All 33 skills have a routing result.

## 0.2.1 — 2026-10-22

### Added
- `lint_tree.py` now FAILs when a markdown file shows the 0.1.0 publish-damage signature (a `def` with no parens, a method call with no parens, or a JS arrow with empty pseudo-parens), so the corruption is caught at audit time.

## 0.2.0 — 2026-10-22

Fixes from an independent audit of 0.1.0.

### Fixed
- Code samples: restored every empty `()` and all code indentation that a publish step had stripped (about 60 code blocks in 44 leaves, plus a few inline spans; counted as blocks that differ from 0.1.0 only by whitespace or `()`). One CI YAML sample was also made valid YAML.
- `SKILL.md` frontmatter is now strict YAML and spec-valid: `description` is quoted, and the skill's domain moved to `metadata.domain` (31 of 33 failed strict YAML before). Leaf routing headers in `subskills/` are read line by line by `lint_tree.py`; they are not strict YAML.
- `lint_tree.py` reads `metadata.domain` (top-level `domain:` is still accepted).
- Removed private-note references from leaf citations and script comments; public sources are kept. Where a research figure lost its only cited source, the line now carries a ⚠️.
- `ac-subskills-author` no longer tells an agent to install skills unattended through a gate this repo does not ship. Install now needs human approval, or a fail-closed gate the operator sets up.
- Paywalled standards (ISO, CMOS) now carry a ⚠️ in the leaves that summarise them.
- `00-rsi` reference leaf matches the rsi-skills v0.2.0 schema (`callID`, no outcome fields, logs only if the operator enables it).
- SLO arithmetic (99.9 % over 30 days ≈ 43 min); one dead OpenAI link replaced.
- README and PROOF rewritten: correct counts, real install paths, honest test scope.

### Added
- CHANGELOG, SECURITY, CONTRIBUTING, `.gitignore`.

## 0.1.0 — 2026-10-21

First release: 33 skills, 114 leaves.
