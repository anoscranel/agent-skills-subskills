# Changelog

All notable changes to this pack. Versions follow [SemVer](https://semver.org/).

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
