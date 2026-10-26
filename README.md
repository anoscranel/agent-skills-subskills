# agent-skills-subskills

35 MIT-licensed [Agent Skills](https://agentskills.io/specification) for professional work: software engineering, writing, prompt engineering, and one meta-skill that builds and audits skills like these.

Each skill is a short routing index (`SKILL.md`) over a flat set of leaf files (`subskills/*.md`). The agent loads the index, picks one leaf, and follows it. Every leaf holds its full procedure and never hands the task to another skill.

## What's in the pack

| Suite | Skills | Leaves |
|---|---|---|
| Software engineering | 19 | 60 |
| Writing | 14 | 48 |
| Prompt engineering (`ac-prompt-engineer`) | 1 | 12 |
| Skill authoring (`ac-subskills-author`) | 1 | 10 |
| **Total** | **35** | **130** |

**Software engineering:** agent-coding-governance · api-design · architecture · ci-and-release · code-construction · code-review · codebase-maintenance · database-changes · debugging · frontend-ui · git-workflow · performance · quality-verification · reliability · software-engineering-standards · spec-writing · task-planning · testing · design-taste

**Writing:** academic-writing · business-writing · drafting · editing · evidence-and-citation · narrative-writing · news-writing · persuasive-writing · plain-language · proposal-writing · technical-writing · voice-and-style · writing-standards · slide-decks

Every skill name carries the `ac-` prefix (for example `ac-testing`).

## How a leaf is built

Each leaf has a routing header (name, domain, trigger, anti-trigger, scope, status) and, for the craft leaves, six sections: Standard, Decision rules, Procedure, Anti-patterns, Done checklist, Sources. Claims cite public primary sources inline. Paywalled or single-source claims carry a ⚠️ flag.

## Install

Copy one skill directory (or all of them) into a skills directory your harness reads:

| Harness | Global path | Project path |
|---|---|---|
| opencode | `~/.config/opencode/skills/<name>/` or `~/.agents/skills/<name>/` | `.opencode/skills/<name>/` |
| Claude Code | `~/.claude/skills/<name>/` | `.claude/skills/<name>/` |
| Other Agent Skills harnesses | see your harness's docs | |

```sh
git clone https://github.com/anoscranel/agent-skills-subskills.git
cp -r agent-skills-subskills/skills/ac-testing ~/.claude/skills/
```

Restart the harness, then confirm the skill is listed (opencode: `opencode debug skill`). Paths per the [opencode skills docs](https://opencode.ai/docs/skills/).

## Code in this repo

The only executable code is four Python checkers in `skills/ac-subskills-author/scripts/`; leaves may show illustrative snippets that nothing runs. The four checkers use the standard library only, make no network calls and write no files, and run only when you call them:

| Script | What it does |
|---|---|
| `lint_tree.py <skill-dir>` | Checks a skill tree's structure: frontmatter, domain chain, index ↔ disk, links, no hand-off lines |
| `skill_scan.py <skill-dir>` | Scans every file for injection, hand-off, credential-path and build-artifact patterns |
| `route_score.py` | Scores a blind routing evaluation against pre-registered labels |
| `tree_hash.py <dir>` | Prints a content hash of a tree, for tamper checks |

No skill ships hooks or install scripts.

## Safety

`ac-subskills-author` audits a skill before install. It never installs on its own judgment: install needs a human's approval, or a fail-closed install gate that you set up yourself. This repo does not ship such a gate.

## Proof

What was tested, what passed, and what was not tested: [`docs/PROOF.md`](docs/PROOF.md).

## License

MIT, © 2026 Anos Cranel. See [LICENSE](LICENSE). The skills are self-authored. Their content draws on public standards and published research, which each leaf cites.
