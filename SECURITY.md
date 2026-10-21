# Security

These skills are instructions an AI agent will follow, so a malicious edit is a security issue.

**Report a vulnerability** through GitHub's private advisory form: *Security → Report a vulnerability* on this repository. Please do not open a public issue for it.

In scope:
- A leaf that tells an agent to install, delete, push, spend or send without a human gate.
- Hidden instructions (prompt injection) in any file.
- Any behavior of the four scripts in `skills/ac-subskills-author/scripts/` beyond reading files and printing results.

Before installing any skill, from here or elsewhere, scan it:

```sh
python3 -B skills/ac-subskills-author/scripts/skill_scan.py <skill-dir>
```
