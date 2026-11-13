# agent-skills-subskills

227 MIT-licensed [Agent Skills](https://agentskills.io/specification) for professional work: software engineering, writing, prompt engineering, security hardening, research operations, critical thinking, collaboration, and one meta-skill that builds and audits skills like these.

Each skill is a short routing index (`SKILL.md`) over a flat set of leaf files (`subskills/*.md`). The agent loads the index, picks one leaf, and follows it. Every leaf holds its full procedure and never hands the task to another skill.

## What's in the pack

| Suite | Skills | Leaves |
|---|---|---|
| Software engineering | 92 | 599 |
| Writing | 17 | 70 |
| Prompt engineering | 7 | 58 |
| Skill authoring | 3 | 24 |
| Security hardening | 4 | 46 |
| Research operations | 5 | 46 |
| Critical thinking | 2 | 15 |
| Collaboration | 3 | 21 |
| Crypto trading | 20 | 141 |
| Investing | 74 | 522 |
| **Total** | **227** | **1543** |

**Skill authoring:** subskills-author · release-publish · skill-adoption

**Research operations:** deep-researcher · adversarial-corpus-challenge · meta-analysis-and-synthesis · qualitative-synthesis · systematic-review-conduct

**Critical thinking:** interrogation · ideation

**Collaboration:** handoff · inbound-triage · multi-agent-orchestration

**Crypto trading:** cascade-forensics · crypto-trading-discipline · derivatives-instrument-selection · funding-and-basis · liquidation-hunt-analysis · liquidation-risk-management · market-data-collection · onchain-flow-analysis · order-execution · perp-venue-diligence · portfolio-construction · stablecoin-collateral-risk · token-diligence · trading-agent-desk · trading-operations-runbook · backtest-integrity

**Investing:** activism · capital-return · corporate-treasury · credit-rating-mechanics · distressed-and-restructuring · ma-transaction-execution · venture-financing · equity-capital-markets · direct-real-estate · forensic-accounting · fund-structures-and-wrappers · fund-reporting-and-metrics · infrastructure-and-project-finance · insurance-linked-securities · investment-oversight-and-ocio · liability-driven-investing · municipal-bonds · pension-risk-transfer · securitisation-and-tranches · share-based-compensation · sovereign-debt · trade-policy-and-restrictions · transaction-cost-analysis · climate · convertible-and-hybrid-capital · emerging-market-access · litigation · manager-diligence · portfolio-financing · private-credit · trade-finance · alternatives-and-real-assets · bank-and-credit-analysis · broker-and-custody-selection · commodity-options · commodity-trading · credit-derivatives · credit-options · equity-options · equity-index-futures · forex-trading · fx-options · rates-options · rates-trading · portfolio-leverage · estate-and-succession · insurance-and-risk-transfer · structured-products · behavioral-investing · corporate-actions · currency-and-fx-risk · equity-market-structure · equity-research · fixed-income-and-rates · investment-policy-statement · trading-records-and-tax · valuation

**Security hardening:** security-engineer · security-standards · compliance-program-engineering

**Software engineering:** agent-coding-governance · agent-run-observability · analytical-data-modeling · api-design · api-limit-operations · architecture · architecture-survey · async-and-concurrency · audit-logging · binary-formats · byzantine-consensus · caching-and-invalidation · chaos-and-capacity-testing · ci-and-release · cli-and-tool-design · client-state-and-interaction · code-construction · code-generation-and-apis · code-review · codebase-maintenance · compilers-and-abis · consensus-protocols · content-addressed-storage · content-moderation · cost-aware-engineering · data-contracts · data-migration-cutover · data-pipeline-orchestration · database-changes · database-engine-internals · debugging · design-taste · distributed-state-and-replication · domain-modeling · durable-execution · email-deliverability · event-driven-architecture · frontend-bundling · frontend-ui · geospatial-data · git-workflow · gpu-and-parallel-compute · graphql-and-streaming-apis · i18n-and-localisation · inference-serving · lexical-search-engineering · llm-api-integration · low-level-io-and-syscalls · mcp-authoring · media-pipelines · memory-layout-and-caches · message-queues · ml-systems-practice · mobile-client-engineering · money-arithmetic · monorepo-and-build-systems · multitenancy-and-isolation · network-edge-and-delivery · notification-systems · online-experiments · payments-and-billing-engineering · performance · platform-engineering · privacy-engineering · production-debugging · quality-verification · query-and-index-design · realtime-media-transport · recommendation-systems · reliability · resilience-budgets · resource-exhaustion-diagnosis · retrieval-and-vector-systems · saas-tax-and-geography · scheduled-jobs · sdk-and-client-library-design · service-lifecycle · sharding-and-placement · software-engineering-standards · software-supply-chain · spec-writing · static-analysis · stream-processing · task-planning · test-environments · testing · text-encoding · time-and-clocks · time-series-storage · transaction-isolation · wasm-and-sandboxes · webhook-and-async-delivery
**Prompt engineering:** agent-memory-and-recall · agent-tool-design · model-evaluation · prompt-engineer · rag-systems · single-request-value · token-cost-optimization

**Writing:** academic-writing · business-writing · brand-guidelines · doc-coauthoring · drafting · editing · evidence-and-citation · narrative-writing · news-writing · persuasive-writing · plain-language · proposal-writing · technical-writing · voice-and-style · writing-standards · slide-decks · dataviz

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
