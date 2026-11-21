# agent-skills-subskills

243 MIT-licensed [Agent Skills](https://agentskills.io/specification) for professional work: software engineering, writing, prompt engineering, security hardening, research operations, critical thinking, collaboration, and one meta-skill that builds and audits skills like these.

Each skill is a short routing index (`SKILL.md`) over a flat set of leaf files (`subskills/*.md`). The agent loads the index, picks one leaf, and follows it. Every leaf holds its full procedure and never hands the task to another skill.

## What's in the pack

| Suite | Skills | Leaves |
|---|---|---|
| Software engineering | 102 | 670 |
| Writing | 17 | 70 |
| Prompt engineering | 7 | 58 |
| Skill authoring | 3 | 24 |
| Security hardening | 5 | 53 |
| Research operations | 7 | 60 |
| Critical thinking | 4 | 29 |
| Collaboration | 4 | 28 |
| Crypto trading | 20 | 141 |
| Investing | 74 | 523 |
| **Total** | **243** | **1656** |

**Skill authoring:** subskills-author · release-publish · skill-adoption

**Research operations:** deep-researcher · adversarial-corpus-challenge · meta-analysis-and-synthesis · qualitative-research-methods · qualitative-synthesis · survey-research-methods · systematic-review-conduct

**Critical thinking:** causal-inference · decision-analysis · ideation · interrogation

**Collaboration:** handoff · inbound-triage · multi-agent-orchestration · team-collaboration

**Crypto trading:** cascade-forensics · crypto-trading-discipline · derivatives-instrument-selection · funding-and-basis · liquidation-hunt-analysis · liquidation-risk-management · market-data-collection · onchain-flow-analysis · order-execution · perp-venue-diligence · portfolio-construction · stablecoin-collateral-risk · token-diligence · trading-agent-desk · trading-operations-runbook · backtest-integrity

**Investing:** activism · capital-return · corporate-treasury · credit-rating-mechanics · distressed-and-restructuring · ma-transaction-execution · venture-financing · equity-capital-markets · direct-real-estate · forensic-accounting · fund-structures-and-wrappers · fund-reporting-and-metrics · infrastructure-and-project-finance · insurance-linked-securities · investment-oversight-and-ocio · liability-driven-investing · municipal-bonds · pension-risk-transfer · securitisation-and-tranches · share-based-compensation · sovereign-debt · trade-policy-and-restrictions · transaction-cost-analysis · climate · convertible-and-hybrid-capital · emerging-market-access · litigation · manager-diligence · portfolio-financing · private-credit · trade-finance · alternatives-and-real-assets · bank-and-credit-analysis · broker-and-custody-selection · commodity-options · commodity-trading · credit-derivatives · credit-options · equity-options · equity-index-futures · forex-trading · fx-options · rates-options · rates-trading · portfolio-leverage · estate-and-succession · insurance-and-risk-transfer · structured-products · behavioral-investing · corporate-actions · currency-and-fx-risk · equity-market-structure · equity-research · fixed-income-and-rates · investment-policy-statement · trading-records-and-tax · valuation

**Security hardening:** compliance-program-engineering · security-engineer · security-operations · security-standards · threat-intelligence

**Software engineering:** academic-writing · adversarial-corpus-challenge · agent-coding-governance · agent-eval-harness · agent-guardrails · agent-memory-and-recall · agent-run-observability · agent-tool-design · alternative-data · alternatives-and-real-assets · analytical-data-modeling · api-design · api-limit-operations · architecture · architecture-survey · async-and-concurrency · audit-logging · backtest-integrity · bank-and-credit-analysis · behavioral-investing · binary-formats · brand-guidelines · broker-and-custody-selection · business-writing · byzantine-consensus · caching-and-invalidation · capital-return-policy · cascade-forensics · chaos-and-capacity-testing · ci-and-release · cli-and-tool-design · client-state-and-interaction · climate-and-transition-risk · code-construction · code-generation-and-apis · code-review · codebase-maintenance · commodities-trading · commodity-options · compilers-and-abis · compliance-program-engineering · consensus-protocols · content-addressed-storage · content-moderation · convertible-and-hybrid-capital · corporate-actions · corporate-treasury · cost-aware-engineering · credit-curve · credit-derivatives · credit-options · credit-rating-mechanics · crypto-options · crypto-trading-discipline · currency-and-fx-risk · data-annotation · data-contracts · data-migration-cutover · data-pipeline-orchestration · database-changes · database-engine-internals · dataviz · debugging · deep-researcher · derivatives-instrument-selection · design-taste · direct-real-estate · distressed-and-restructuring · distributed-state-and-replication · doc-coauthoring · domain-modeling · drafting · durable-execution · earnings-quality · edge-ml-deployment · editing · email-deliverability · emerging-market-access · equity-capital-markets · equity-index-futures · equity-market-structure · equity-options · equity-research · estate-and-succession · event-driven-architecture · evidence-and-citation · exchange-account-security · factor-investing · fixed-income-and-rates · forensic-accounting · forex-trading · frontend-bundling · frontend-ui · fund-reporting-and-metrics · fund-selection · fund-structures-and-wrappers · funding-and-basis · fx-options · geospatial-data · git-workflow · gpu-and-parallel-compute · graphql-and-streaming-apis · handoff · i18n-and-localisation · ideation · inbound-triage · index-methodology-design · inference-serving · infrastructure-and-project-finance · institutional-operations · institutional-order-flow · institutional-positioning · insurance-and-risk-transfer · insurance-linked-securities · interrogation · investment-oversight-and-ocio · investment-policy-statement · lexical-search-engineering · liability-driven-investing · liquidation-hunt-analysis · liquidation-risk-management · liquidity-risk · llm-api-integration · low-level-io-and-syscalls · ma-transaction-execution · macro-and-policy-reading · manager-and-vehicle-diligence · market-data-collection · mcp-authoring · media-pipelines · memory-layout-and-caches · message-queues · meta-analysis-and-synthesis · ml-systems-practice · mobile-client-engineering · model-compression · model-evaluation · model-fine-tuning · money-arithmetic · monorepo-and-build-systems · multi-agent-orchestration · multitenancy-and-isolation · municipal-bonds · narrative-writing · network-edge-and-delivery · news-writing · notification-systems · onchain-flow-analysis · online-experiments · options-and-volatility · order-execution · payments-and-billing-engineering · pension-risk-transfer · performance · performance-measurement · perp-venue-diligence · persuasive-writing · plain-language · platform-engineering · portfolio-construction · portfolio-financing · portfolio-leverage · privacy-engineering · privacy-preserving-ml · private-credit · product-analytics-instrumentation · product-management · production-debugging · prompt-engineer · proposal-writing · qualitative-synthesis · quality-verification · quantitative-methods-for-trading · query-and-index-design · rag-systems · rates-options · rates-trading · realtime-media-transport · recommendation-systems · release-publish · reliability · resilience-budgets · resource-exhaustion-diagnosis · retirement-and-drawdown · retrieval-and-vector-systems · saas-tax-and-geography · scenario-and-stress-testing · scheduled-jobs · sdk-and-client-library-design · securities-litigation · securitisation-and-tranches · security-engineer · security-operations · security-standards · service-lifecycle · sharding-and-placement · share-based-compensation · shareholder-activism · single-request-value · skill-adoption · slide-decks · software-engineering-standards · software-supply-chain · sovereign-debt · spec-writing · special-situations · stablecoin-collateral-risk · static-analysis · stock-trading · stream-processing · structured-products · subskills-author · systematic-review-conduct · task-planning · tax-aware-investing · technical-writing · test-environments · testing · text-encoding · threat-intelligence · time-and-clocks · time-series-storage · token-cost-optimization · token-diligence · trade-finance · trade-policy-and-restrictions · trading-agent-desk · trading-operations-runbook · trading-records-and-tax · transaction-cost-analysis · transaction-isolation · user-research · valuation · venture-financing · voice-and-style · wasm-and-sandboxes · webhook-and-async-delivery · writing-standards
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
