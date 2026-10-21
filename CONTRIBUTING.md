# Contributing

Issues and pull requests are welcome.

A change to a skill must keep these passing (run from the repo root):

```sh
python3 -B skills/ac-subskills-author/scripts/lint_tree.py skills/<name>
python3 -B skills/ac-subskills-author/scripts/skill_scan.py skills/<name>
```

House rules for leaves:
- One leaf, one job. A leaf never hands the task to another skill.
- Every load-bearing claim cites a public primary source inline. Paywalled or single-source claims carry ⚠️.
- Any irreversible action (install, delete, push, spend, send) is a human gate.
- Plain English: short sentences, active voice.

By contributing you agree your contribution is licensed under the MIT License.
