# Changelog

All notable changes to this pack. Versions follow [SemVer](https://semver.org/).

## 0.48.0 — 2026-11-10

### Fixed
- **Dead citation URL across the whole pack.** `https://www.sec.gov/about/about-securities` returns
  404. It appeared 600 times in 363 files across 55 skill trees, in every release since the first
  investing skills. Replaced with `https://www.sec.gov/investor`, verified live.
- **Three thresholds that named a quantity without a value**, found by reading rather than by script:
  - 13F filing threshold now states investment discretion over at least one hundred million dollars.
  - 13D/13G threshold now states five percent of a class of beneficial ownership.
  - Settlement cycle now states T+1 or T+2 depending on market and instrument.

### Changed
- The gate review log records the auditing model in every section heading, and a new auditor identity
  policy binds sections from v0.47.1 onward.

### Known debt (recorded, not repaired)
Structural citation defects in five pre-v0.39 skills: 20 leaves with no `## Sources` section, 10 using
`## The standard` as the heading, 33 `Sources` sections with no URL, 90 leaves with fewer than two body
URLs. Recorded in `findings/job-078-preexisting-citation-defects.md`.

No skill count changed. The pack remains 162 skills, 1045 leaves.

## 0.47.1 — 2026-11-10

### Fixed
A re-audit of the sixty skills shipped between v0.39.0 and v0.47.0 found three defects that every
prior gate review had passed:

- `ac-index-methodology-design`: the description carried no `Not for` boundary. Three named
  boundaries added; 820 characters, strict YAML.
- `ac-insurance-linked-securities`: the description carried no `Not for` boundary. Three named
  boundaries added; 926 characters, strict YAML.
- `ac-trade-finance`: `subskills/inventory-and-receivables-finance.md` was missing its
  `## Done checklist` section, and two paragraphs had been stranded inside `## Anti-patterns`.
  The section was added and the paragraphs moved into `## Standard`.

### Changed
- The gate review log now records the auditing model in every section heading. A new auditor
  identity policy binds sections from this release onward.

No skill count changed. The pack remains 162 skills, 1045 leaves.

## 0.47.0 — 2026-11-10

### Added
Nine software-engineering skills, each with a written record leaf:

- `ac-graphql-and-streaming-apis` (7): schema shape and nullability, N+1 and batching, query cost and depth, federation and ownership, cursor pagination, subscriptions and SSE, interface record.
- `ac-retrieval-and-vector-systems` (7): chunking strategy, embedding models, vector index types, hybrid search and reranking, freshness and rebuilds, relevance evaluation, retrieval record.
- `ac-multitenancy-and-isolation` (7): tenancy models, isolation levels, tenant context propagation, noisy neighbour, quotas and limits, row-level security, isolation record.
- `ac-resilience-budgets` (7): timeout budgets, retry budgets, backoff and jitter, circuit breaking, bulkheads and pools, load shedding, resilience record.
- `ac-durable-execution` (7): workflow state and checkpoints, sagas and compensation, idempotent activities, activity timeouts and heartbeats, workflow versioning, human in the loop, workflow record.
- `ac-platform-engineering` (7): golden path, service catalogue, self-service and guardrails, toil measurement, on-call design, developer experience metrics, platform record.
- `ac-data-contracts` (7): contract schema and semantics, freshness and completeness, schema evolution rules, ownership and escalation, quality checks at the boundary, contract enforcement, contract record.
- `ac-webhook-and-async-delivery` (7): delivery contract, at-least-once and dedup, signature and replay, ordering guarantees, endpoint health and disabling, consumer-side idempotency, delivery record.
- `ac-sdk-and-client-library-design` (7): public surface, error types, defaults and timeouts, configuration and credentials, versioning and deprecation, idiom and packaging, SDK record.

Routing runs 89-91 were combined (46 tasks each) over a 187-entry catalog. Runs 89 and 91 scored 14 of 14 for every skill; run 90 scored 13 of 14 for resilience and durable execution and 14 of 14 for platform engineering, within the pass threshold, with both misses also correct at top 2.

### Fixed
- The `software-engineering` domain row named 22 of its 41 skills. All 41 are now listed.

The pack is now 162 skills, 1045 leaves.

## 0.46.0 — 2026-11-10

### Added
Nine software-engineering skills, each with a written record leaf:

- `ac-mobile-client-engineering` (7): release train and store review, offline-first state, version skew and forced upgrade, network and battery budgets, push and deep links, fragmentation, record.
- `ac-i18n-and-localisation` (7): string externalisation, plurals and gender, RTL and bidi, collation and search, locale formatting, localisation workflow, record.
- `ac-privacy-engineering` (7): data inventory, minimisation, retention and deletion, subject requests, pseudonymisation versus anonymisation, encryption and keys, record.
- `ac-event-driven-architecture` (7): events versus commands, ordering and partitioning, idempotency and delivery, outbox, schema evolution, replay and rebuild, backpressure.
- `ac-chaos-and-capacity-testing` (7): failure injection and blast radius, game days, load model validity, soak and spike, capacity headroom, dependency failure, record.
- `ac-cost-aware-engineering` (7): unit economics, cost drivers, storage and egress, attribution, build versus buy, budget alarms, record.
- `ac-monorepo-and-build-systems` (7): dependency graph, affected targets, cache keys, hermetic builds, generated code, incremental CI, record.
- `ac-cli-and-tool-design` (7): exit codes, stdout and stderr, flag conventions, idempotency and re-runs, interactive modes, signals, record.
- `ac-money-arithmetic` (7): representation and types, rounding modes, allocation and remainders, conversion and precision, accrual and day-count, reconciliation tolerance, record.

Each passed a sealed blind routing run. Runs 86-88 were combined (46, 60 and 32 tasks) over a 178-entry catalog: **all nine scored 14 of 14 at top 1 on the first attempt**, with 4 of 4 out-of-scope tasks answered `none` in each run. No description corrections were required.

### Changed
- The `software-engineering` domain row now names all thirty-two software-engineering skills.

The pack is now 153 skills, 982 leaves.

## 0.45.0 — 2026-11-10

### Added
Nine investing skills, each with a written record leaf:

- `ac-distressed-and-restructuring` (8 leaves): priority and waterfall, fulcrum determination, out-of-court exchange, DIP and priming, automatic stay, claims trading, plan and cramdown, record.
- `ac-equity-capital-markets` (7): bookbuilding, greenshoe and stabilisation, lock-up expiry, follow-on and blocks, rights issues, direct listings and SPACs, record.
- `ac-municipal-bonds` (7): GO versus revenue, tax-equivalent yield, calls and refunding, insurer wraps, disclosure, pension and OPEB liabilities, record.
- `ac-fund-structures-and-wrappers` (7): open versus closed end, European wrappers, US registered funds, ETF creation, BDC and listed vehicles, eligibility and distribution, record.
- `ac-share-based-compensation` (7): grant types and vesting, expense and add-back, fully diluted count, buyback offset, dilution per year, performance and market conditions, record.
- `ac-corporate-treasury` (7): liquidity policy, counterparty limits, hedging programme design, hedge accounting, maturity ladder, facility covenants, record.
- `ac-pension-risk-transfer` (7): buy-in versus buy-out, insurer pricing, longevity swaps, partial and phased transfers, member options, settlement accounting, record.
- `ac-infrastructure-and-project-finance` (7): concession and handback, availability versus demand, DSCR and lock-up, capex lifecycle, tariff and inflation linkage, refinancing and equity return, record.
- `ac-sovereign-debt` (7): sovereign versus corporate, collective action clauses, restructuring process, local versus foreign law, holdouts and enforcement, recovery and exit yield, record.

Each passed a sealed blind routing run. Runs 83-85 were combined (46, 60 and 32 tasks) over a 169-entry catalog: **all nine scored 14 of 14 at top 1 on the first attempt**, with 4 of 4 out-of-scope tasks answered `none` in each run. No description corrections were required.

### Changed
- The `investing` domain row now names all seventy-two investing skills.

The pack is now 144 skills, 919 leaves.

## 0.44.0 — 2026-11-09

### Added
- Ten investing skills across three tiers:
  - `ac-securitisation-and-tranches` (8 leaves): SPV and true sale, waterfall and subordination, credit enhancement, tranche attachment, triggers and amortisation, servicer operations, prepayment and WAL, structure record.
  - `ac-fund-reporting-and-metrics` (6): IRR assumptions, TVPI/DPI/RVPI, the J-curve, vintage and peer benchmarks, dry powder, reporting record.
  - `ac-liability-driven-investing` (7): funding ratio and surplus, liability discounting, duration and key-rate matching, immunisation conditions, de-risking glide path, contribution and benefit policy, LDI record.
  - `ac-transaction-cost-analysis` (7): implementation shortfall, VWAP and participation benchmarks, cost decomposition, broker scorecards, transition management, research payment governance, cost record.
  - `ac-credit-rating-mechanics` (7): what a rating measures, agency methodologies, outlooks and watches, migration and default tables, fallen angels, contract triggers, rating record.
  - `ac-trade-policy-and-restrictions` (7): tariff incidence, export controls, sanctions reach, investment screening, local content and transfer pricing, resource nationalism, policy exposure record.
  - `ac-insurance-linked-securities` (7): trigger design, collateral and SPV, expected loss and spread, modelled versus realised, perils and correlation, seasonality and reset, ILS record.
  - `ac-investment-oversight-and-ocio` (7): oversight function, mandate design, compliance monitoring, board reporting, OCIO conflicts, fee oversight, oversight record.
  - `ac-direct-real-estate` (7): net operating income, lease structure and tenant credit, cap rates, appraisal, capex and deferred maintenance, property debt, property record.
  - `ac-forensic-accounting` (7): related-party transactions, off-balance-sheet entities, round-tripping, capitalised costs, segment disclosure, cash conversion forensics, forensic record.
- All ten passed sealed blind routing on the first attempt: 14 of 14 at top 1 each, 4 of 4 out-of-scope tasks answering `none`, across three combined runs over a 160-entry catalog.

### Changed
- The `investing` domain row now names all sixty-three investing skills.

The pack is now 135 skills, 855 leaves.

## 0.43.0 — 2026-11-09

### Added
Ten investing skills, each a 7-leaf tree except manager diligence at 8:

- `ac-convertible-and-hybrid-capital` — parity and premium, bond floor, yield to worst, busted and distressed, contingent capital, perpetuals, record.
- `ac-capital-return-policy` — buyback execution, accelerated repurchases, dividend sustainability, specials, buyback timing, debt-funded buybacks, record.
- `ac-private-credit` — direct lending structure, unitranche splits, covenants, PIK, sponsor dynamics, marks, record.
- `ac-shareholder-activism` — campaign archetypes, 13D, settlements, proxy arithmetic, proposals, campaign economics, record.
- `ac-climate-and-transition-risk` — emissions scopes, disclosure regimes, scenarios, transition by sector, physical risk, stranded assets, record.
- `ac-manager-and-vehicle-diligence` — questionnaire, operational diligence, fee stack, side letters and MFN, key person, governance, liquidity and gates, record.
- `ac-securities-litigation` — class action mechanics, claims and funds, opting out, damages, funding, D&O, record.
- `ac-emerging-market-access` — depositary receipts, local channels, capital controls, settlement and custody, index flows, currency access, record.
- `ac-portfolio-financing` — subscription lines, NAV loans, continuation funds, LP secondaries, conflicts, fund leverage, record.
- `ac-trade-finance` — letters of credit, collections, title documents, prepayment, inventory finance, fraud patterns, record.

Every skill passed a sealed blind routing run over a 150-entry catalog: all ten at or above 12 of 14 top-1 matches, negatives 4 of 4. Two descriptions were corrected after a first pass and re-verified on a fresh catalog.

### Changed
- The `investing` domain row now names all fifty-three investing skills.

The pack is now 125 skills, 785 leaves.

## 0.42.0 — 2026-11-09

### Added
- `ac-credit-curve` (investing, 7 leaves): curve shape, spread versus risk-free, roll and carry in credit, curve trade structure, inversion and stress, cross-issuer relative value, and the credit curve record.
- `ac-index-methodology-design` (investing, 7 leaves): eligibility and selection, weighting schemes, rebalancing and buffers, concentration caps, inclusion arbitrage, methodology integrity, and the index design record.
- Each passed a sealed blind routing run (18 pre-registered tasks over a 140-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all forty-three investing skills.

Tier 3 completes the ten-skill brainstorm. Across the three tiers the pack gained measurement (performance, liquidity, stress, data quality), forensics (earnings quality), event arithmetic (special situations), decision framing (tax, factors, credit curve, index design).

The pack is now 115 skills, 714 leaves.

## 0.41.0 — 2026-11-09

### Added
- `ac-liquidity-risk` (investing, 7 leaves): market versus funding liquidity, days to liquidate, the liquidity ladder, fire-sale discounts, margin calls as liquidity events, stress liquidity, and the liquidity record.
- `ac-factor-investing` (investing, 7 leaves): what a factor is, factor construction, standardisation and neutralisation, sorts and regressions, capacity and crowding, factor timing, and the factor record.
- `ac-scenario-and-stress-testing` (investing, 7 leaves): reverse stress testing, historical versus hypothetical, correlation breakdown, severity calibration, pass and fail criteria, scenario construction, and the scenario record.
- `ac-alternative-data` (investing, 7 leaves): provenance and vendor claims, point-in-time integrity, coverage and representativeness, signal decay, licensing and permitted use, cost and build, and the vendor record.
- Each passed a sealed blind routing run (18 pre-registered tasks over a 138-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all forty-one investing skills.

Tier 2 of the brainstormed backlog. Each of these measures something the pack could previously only assert: how fast a portfolio becomes cash, how a factor is actually built, what would break the book, and whether a dataset is what its vendor says.

The pack is now 113 skills, 700 leaves.

## 0.40.0 — 2026-11-09

### Added
- `ac-performance-measurement` (investing, 7 leaves): time- versus money-weighted returns, benchmark selection, Brinson attribution, risk-adjusted ratios, drawdown depth and duration, peer-group traps, and the performance record.
- `ac-earnings-quality` (investing, 7 leaves): accruals and cash flow, cash conversion, non-GAAP bridges, revenue recognition, recurring one-offs, guidance and consensus, and the quality record.
- `ac-special-situations` (investing, 7 leaves): merger spread arithmetic, deal timeline and risk, spin-off mechanics, tender and odd-lot, rights issues, index deletion flows, and the event record.
- `ac-tax-aware-investing` (investing, 7 leaves): asset location, loss harvesting, gain deferral, charitable routes, rebalancing with tax, withdrawal ordering, and the tax-aware policy.
- Each passed a sealed blind routing run (18 pre-registered tasks over a 134-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all thirty-seven investing skills.

These four close gaps the pack had left open: how a result is measured, how reported earnings are read, how corporate events are priced, and how tax constrains a decision. None of them gives advice; each ends in a record of what was measured and what remains a question for a professional.

The pack is now 109 skills, 672 leaves.

## 0.39.0 — 2026-11-09

### Added
- `ac-institutional-positioning` (investing, 7 leaves): holdings disclosures, insider transactions, short interest and fails, Commitments of Traders, blocks and activist stakes, ownership reconstruction, and the positioning record.
- `ac-institutional-order-flow` (investing, 7 leaves): block prints and crossings, trade-size clustering, order-book imbalance, volume profile and VWAP, relative volume, auction and rebalance flows, and the footprint record.
- `ac-institutional-operations` (investing, 8 leaves): order lifecycle, prime brokerage, clearing and CCPs, settlement and fails, margin and collateral, custody and segregation, securities lending, and the operations record.
- Each passed a sealed blind routing run (18 pre-registered tasks over a 130-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all thirty-three investing skills.

The three cover what institutions must disclose, what their execution leaves in the tape, and the plumbing that moves their orders. None of them infers intent: the positioning skill reads filings with their lags, the order-flow skill records an alternative explanation beside every observation, and the operations skill maps obligations rather than recommending trades.

The pack is now 105 skills, 644 leaves.

## 0.38.0 — 2026-11-09

### Added
- `ac-crypto-options` (crypto-trading, 7 leaves): inverse and linear contracts, expiry and settlement, the volatility surface, venues and RFQ, margin and liquidation, yield selling and its tail, and the record.
- Passed a sealed blind routing run (18 pre-registered tasks over a 127-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `crypto-trading` domain row now names all nineteen crypto skills.

With this release the futures-and-options matrix is complete for every market the pack covers: equities, index futures, FX, commodities, rates, credit and crypto each have both a venue skill and an option-conventions skill.

The pack is now 102 skills, 622 leaves.

## 0.37.0 — 2026-11-09

### Added
- `ac-credit-options` (investing, 7 leaves): CDS option mechanics, credit spread volatility, index options and tranches, settlement into protection, dealer liquidity, hedging with credit options, and the record.
- Passed a sealed blind routing run (18 pre-registered tasks over a 126-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all thirty investing skills.

Credit was the last asset class without an option skill. Futures and options now each exist per market: equities, FX, commodities, rates, index futures, and credit.

The pack is now 101 skills, 615 leaves.

## 0.36.0 — 2026-11-09

### Added
- `ac-commodity-options` (investing, 7 leaves): options on futures, American exercise, commodity volatility skew, seasonal volatility, average and spread options, physical hedging, and the record.
- `ac-equity-options` (investing, 7 leaves): single-name versus index, expiry and settlement, dividends and early exercise, borrow and put parity, index volatility and dispersion, corporate actions, and the record.
- Each passed a sealed blind routing run (18 pre-registered tasks over a 125-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all twenty-nine investing skills.

The pack reaches 100 skills. Option conventions now exist per asset class for FX, rates, commodities and equities, on top of the market-agnostic greeks and structures skill.

The pack is now 100 skills, 608 leaves.

## 0.35.0 — 2026-11-08

### Added
- `ac-fx-options` (investing, 7 leaves): option conventions, delta conventions, volatility quotes, exercise and delivery, barriers and digitals, hedging, and the record.
- `ac-rates-options` (investing, 7 leaves): swaptions and caps, normal versus lognormal volatility, exercise styles, the volatility cube, hedging, liquidity and clearing, and the record.
- Each passed a sealed blind routing run (18 pre-registered tasks over a 123-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all twenty-seven investing skills.

These two add the option layer to venues that already had a futures or spot skill. The generic greeks and structures remain in `ac-options-and-volatility`; these cover the quoting conventions each market actually uses.

The pack is now 98 skills, 594 leaves.

## 0.34.0 — 2026-11-08

### Added
- `ac-credit-derivatives` (investing, 7 leaves): CDS mechanics, spread DV01, credit indices, the CDS-bond basis, credit events, liquidity and terms, and the credit trading record.
- Passed a sealed blind routing run (18 pre-registered tasks over a 121-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all twenty-five investing skills.

Credit was the last asset class without a trading-venue skill. The pack now covers equities, FX, commodities, rates, index futures and credit as venues, alongside the exposure and portfolio skills.

The pack is now 96 skills, 580 leaves.

## 0.33.0 — 2026-11-08

### Added
- `ac-rates-trading` (investing, 7 leaves): bond futures basics, DV01 and hedging, cheapest-to-deliver and basis, repo and financing, curve trades, central-bank and event calendars, and the rates trading record.
- `ac-equity-index-futures` (investing, 7 leaves): contract specifications, fair value and basis, roll and expiry, the overnight session, hedging with contracts, futures versus ETF, and the record.
- Each passed a sealed blind routing run (18 pre-registered tasks over a 120-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all twenty-four investing skills.

The pack is now 95 skills, 573 leaves.

## 0.32.0 — 2026-11-08

### Added
- `ac-stock-trading` (investing, 7 leaves): session structure, single-name liquidity, earnings and event risk, halts and news, index and flow events, borrow and short constraints, and the stock trading record.
- `ac-forex-trading` (investing, 7 leaves): quoting and pip value, venues and spreads, rollover and swap, sessions and liquidity, leverage and margin, the trade process, and the FX trading record.
- `ac-commodities-trading` (investing, 7 leaves): contract specifications, curve shape and carry, storage and convenience yield, seasonality and inventory, margin and delivery risk, spreads, and the commodity trading record.
- Each passed a sealed blind routing run (18 pre-registered tasks over a 118-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all twenty-two investing skills.

The three cover the asset-class venues rather than the exposures: FX risk in a portfolio, commodity allocation, and equity market structure remain separate skills with their own boundaries.

The pack is now 93 skills, 559 leaves.

## 0.31.0 — 2026-11-08

### Added
- `ac-portfolio-leverage` (investing, 7 leaves): margin mechanics, the cost of leverage, forced-sale mechanics, securities-backed lending, leverage and drawdown, leverage sizing, and the leverage record.
- Passed a sealed blind routing run (18 pre-registered tasks over a 115-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all nineteen investing skills.

The pack is now 90 skills, 538 leaves.

## 0.30.0 — 2026-11-08

### Added
- `ac-exchange-account-security` (crypto-trading, 7 leaves): key and permission hygiene, withdrawal controls, authentication and second factors, phishing and social engineering, compromise response, custody of secrets, and the account-security record.
- `ac-broker-and-custody-selection` (investing, 7 leaves): custody structure, broker insolvency, the fee stack, execution quality, conflicts and incentives, access and transfer, and the provider record.
- Each passed a sealed blind routing run (18 pre-registered tasks over a 114-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Fixed
- `ac-trading-operations-runbook` pointed at `ac-exchange-account-security` for key and account compromise; that skill now exists and the reference resolves.

### Changed
- The `crypto-trading` and `investing` domain rows now name the two new skills.

The pack is now 89 skills, 531 leaves.

## 0.29.0 — 2026-11-08

### Added
- `ac-structured-products` (investing, 7 leaves): payoff architecture, autocalls and reverse convertibles, capital protection, issuer and embedded derivative, pricing and decomposition, suitability and mis-selling, and the product record.
- Passed a sealed blind routing run (18 pre-registered tasks over a 112-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all seventeen investing skills.

The pack is now 87 skills, 517 leaves.

## 0.28.0 — 2026-11-08

### Added
- `ac-estate-and-succession` (investing, 6 leaves): beneficiary designations, titling and transfer, estate liquidity, account succession, executor checklist, and the succession record. It prepares the questions and the record; it does not practice law or compute tax.
- Passed a sealed blind routing run (18 pre-registered tasks over a 111-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all sixteen investing skills.

The pack is now 86 skills, 510 leaves.

## 0.27.0 — 2026-11-08

### Added
- `ac-options-and-volatility` (crypto-trading, 7 leaves): greeks, implied volatility and the surface, structures, the volatility risk premium, hedging, execution and assignment, and the record.
- `ac-insurance-and-risk-transfer` (investing, 7 leaves): what to insure, coverage and deductibles, policy terms, insurer strength, insurance in the portfolio, claims and records, and the coverage record.
- Each passed a sealed blind routing run (18 pre-registered tasks over a 110-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `crypto-trading` and `investing` domain rows now name the options and insurance skills respectively.

The pack is now 85 skills, 504 leaves.

## 0.26.0 — 2026-11-08

### Added
- Three investing skills, each a 7-leaf tree: `ac-bank-and-credit-analysis` (bank balance sheet, net interest margin, credit quality, capital and liquidity, bank valuation, corporate credit, record), `ac-retirement-and-drawdown` (decumulation arithmetic, sequence of returns, withdrawal policy, allocation in drawdown, longevity and inflation, account ordering, record), `ac-fund-selection` (cost stack, tracking difference, index methodology, structure and counterparty, liquidity, tax efficiency, record).
- Each passed a sealed blind routing run (18 pre-registered tasks over a 108-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row now names all fourteen investing skills.

The pack is now 83 skills, 490 leaves.

## 0.25.0 — 2026-11-07

### Added
- Five investing skills, each a 7-leaf tree: `ac-alternatives-and-real-assets`, `ac-equity-market-structure`, `ac-corporate-actions`, `ac-currency-and-fx-risk`, `ac-macro-and-policy-reading`.
- Each passed a sealed blind routing run (18 pre-registered tasks over a 105-entry catalog): 14 of 14 at top 1, 4 of 4 out-of-scope tasks answered `none`.

### Changed
- The `investing` domain row in the authoring vocabulary now names all eleven investing skills.

The pack is now 80 skills, 469 leaves.

## 0.24.0 — 2026-11-07

### Added
Twenty-one skills in two new domains, all routing-tested.

**crypto-trading (15):**
- `ac-liquidation-hunt-analysis` — reading a hunt set-up: cascade anatomy, folklore audit, what has evidence, forensics, venue backstop risk, risk posture, measurement layer.
- `ac-perp-venue-diligence` — liquidity realism, fee and clearance structure, backstop and continuity, data transparency, jurisdiction and access, counterparty and custody, venue scorecard.
- `ac-cascade-forensics` — fill-log reading, branching ratio, participation, proxies and tape, evidence standards, report writing, case anatomy.
- `ac-market-data-collection` — collector design, watermarks and gaps, survivorship and universe, series design, source tiering, storage integrity, study readiness.
- `ac-backtest-integrity` — multiple testing, look-ahead and leakage, sample and regime, cost and execution, placebo and null, pre-registration, verdict and kill.
- `ac-funding-and-basis` — funding mechanics, funding as positioning, basis trade, carry economics, open-interest reading, funding and cascade, carry risk register.
- `ac-liquidation-risk-management` — liquidation geometry, margin modes, leverage bands, hedge and basis risk, cascade exposure, margin monitoring, post-liquidation recovery.
- `ac-order-execution` — order types, execution in cascades, slippage and impact, placement tactics, slicing and timing, execution record, failure modes.
- `ac-stablecoin-collateral-risk` — collateral quality, depeg mechanics, haircuts and liquidation distance, custody versus collateral, cross-collateral contagion, monitoring, depeg playbook.
- `ac-trading-agent-desk` — division of labour, verifiable outputs, sandbox and trifecta, regime blindness, herd amplification, desk cadence, agent failure modes.
- `ac-derivatives-instrument-selection` — instrument landscape, perp versus dated, options as hedges, horizon matching, collateral and margin fit, liquidity and execution fit, selection record.
- `ac-portfolio-construction` — risk budgeting across strategies, correlation regimes, drawdown budgeting, capital allocation, concentration and single points, rebalancing and drift, portfolio review.
- `ac-token-diligence` — supply and unlocks, holder concentration, treasury and runway, governance and control, liquidity and market structure, red flags, diligence record.
- `ac-trading-operations-runbook` — preflight checks, order and position reconciliation, venue outage response, stuck and partial orders, liquidation and ADL verification, incident log and postmortem, automation safety.
- `ac-onchain-flow-analysis` — data sources and labels, exchange flows, holder cohorts, whale-watching limits, stablecoin and liquidity flows, flow signals and failures, on-chain record.

**investing (6):**
- `ac-equity-research` — filings and sources, financial statements, ratio analysis, moat and competitive position, management and capital allocation, equity red flags, equity diligence record.
- `ac-valuation` — valuation methods, DCF construction, multiples, terminal value and growth, discount rate, scenarios and sensitivity, valuation record.
- `ac-investment-policy-statement` — goals and horizon, risk capacity and tolerance, constraints register, asset allocation policy, rebalancing policy, monitoring and review, IPS record.
- `ac-behavioral-investing` — bias inventory, decision journals, precommitment devices, information diet, drawdown psychology, social and herd, behavioural review.
- `ac-fixed-income-and-rates` — yield and price mechanics, duration and convexity, yield curve, credit spreads, inflation-linked, liquidity and vehicles, rates record.
- `ac-trading-records-and-tax` — record keeping, cost-basis methods, reconciliation for tax, jurisdiction frames, crypto tax issues, tax pack assembly, tax record audit.

### Changed
- New `crypto-trading` and `investing` domain rows in the authoring vocabulary.
- Fixed a duplicated entry in the README's software-engineering cluster list.

### Routing evidence
- Each of the 21 skills passed its own sealed blind run (18 pre-registered tasks each; 14 or better at top 1, 4 of 4 out-of-scope tasks answered `none`).

The pack is now 75 skills, 434 leaves.

## 0.15.0 — 2026-11-03

### Added
- `ac-crypto-trading-discipline` (crypto-trading, 7 leaves — new domain): the documented decision process of discretionary crypto trading — pre-trade-memo, risk-budget, position-sizing, invalidation-and-kill, journal-and-review, behavioral-rails, desk-routine. The skill records decisions; it never recommends an asset, a direction, a size, or a timing.
- Passed a sealed blind routing run (18 pre-registered tasks over a 79-entry catalog): 14 of 14 at top 1; 4 of 4 out-of-scope tasks answered `none`; zero alternates needed.

### Changed
- New `crypto-trading` domain row added to the authoring vocabulary (first new domain since v0.7.0).

The pack is now 54 skills, 287 leaves.

## 0.14.0 — 2026-11-02

### Added
- `ac-domain-modeling` (software-engineering, 7 leaves): the craft of modeling a business domain — ubiquitous-language, bounded-contexts, aggregates-and-consistency, domain-events, repositories-and-ports, value-objects-and-entities, model-evolution.
- Passed a sealed blind routing run (18 pre-registered tasks over a 78-entry catalog): 14 of 14 at top 1; 4 of 4 out-of-scope tasks answered `none`; zero alternates needed.

### Changed
- The `software-engineering` domain row in the authoring vocabulary now covers modeling business domains: ubiquitous language, bounded contexts, aggregates, domain events.

The pack is now 53 skills, 280 leaves.

## 0.13.0 — 2026-11-01

### Added
- `ac-architecture-survey` (software-engineering, 7 leaves): read-only, evidence-backed whole-repository survey — survey-scope, evidence-versus-judgment, structural-smells, candidate-formation, ranking-criteria, report-discipline, follow-up-boundary. Produces a prioritized report of bounded improvement candidates and stops there; the only permitted write is the report.
- Passed a sealed blind routing run (18 pre-registered tasks over a 77-entry catalog): 14 of 14 at top 1; 4 of 4 out-of-scope tasks answered `none`; zero alternates needed.

### Changed
- The `software-engineering` domain row in the authoring vocabulary now covers read-only evidence-ranked architecture surveys of existing codebases.

The pack is now 52 skills, 273 leaves.

## 0.12.0 — 2026-11-01

### Added
- `ac-llm-api-integration` (software-engineering, 7 leaves): calling model APIs from application code, provider-agnostic — provider-and-endpoint, request-shape, streaming-and-timeouts, tool-use-loop, caching-and-batching, error-and-resilience, evaluation-and-migration.
- Passed a sealed blind routing run (18 pre-registered tasks over a 76-entry catalog): 14 of 14 at top 1; 4 of 4 out-of-scope tasks answered `none`; zero alternates needed.

### Changed
- The `software-engineering` domain row in the authoring vocabulary now covers integrating model APIs into application code.

The pack is now 51 skills, 266 leaves.

## 0.11.0 — 2026-11-01

### Added
- `ac-multi-agent-orchestration` (collaboration, 7 leaves): running more than one agent on one job — when-to-split, role-and-scope, context-budget, delegation-prompts, verification-loops, failure-and-recovery, ledger-and-leverage.
- Passed a sealed blind routing run (18 pre-registered tasks over a 75-entry catalog): 14 of 14 at top 1; 4 of 4 out-of-scope tasks answered `none`; zero alternates needed. An earlier task-set draft failed 10 of 14 and was redesigned before scoring; both runs are documented.

### Changed
- The `collaboration` domain row in the authoring vocabulary now covers designing and supervising multi-agent work.

The pack is now 50 skills, 259 leaves.

## 0.10.0 — 2026-10-31

### Added
- `ac-doc-coauthoring` (writing, 7 leaves): staged co-authoring workflow for structured documents — when to offer the workflow, context gathering, section planning, iterative building, fresh-reader testing, decision records, session handoff.
- Passed a sealed blind routing run (18 pre-registered tasks over a 74-entry catalog): 14 of 14 top 1; 4 of 4 out-of-scope tasks answered `none`; zero alternates needed.

### Changed
- The `writing` domain row in the authoring vocabulary now covers co-authoring structured documents through a staged authoring workflow.

The pack is now 49 skills, 252 leaves.

## 0.9.0 — 2026-10-31

### Added
- `ac-brand-guidelines` (writing, 7 leaves): codifying a brand's voice and style rules across a document corpus — brand specification, style-sheet intake, checklist construction, corpus audit, slip detection, remediation pass, sign-off and reporting.
- Passed a sealed blind routing run (18 pre-registered tasks over a 73-entry catalog): 14 of 14 content tasks at top 1; 4 of 4 out-of-scope tasks answered `none`; zero alternates needed.

### Changed
- The `writing` domain row in the authoring vocabulary now covers codifying and auditing a brand's voice and style rules across a document corpus.

The pack is now 48 skills, 245 leaves.

## 0.8.0 — 2026-10-31

### Added
- `ac-skill-adoption` (skill-authoring, 7 leaves): consumer-side governance for third-party skills — registries and trust signals, security vetting, provenance and licenses, staged install gating, build-vs-adopt, post-install lifecycle.
- `ac-mcp-authoring` (software-engineering, 7 leaves): authoring Model Context Protocol servers — protocol model, tool design, resources and prompts, transports, security, testing, versioning.
- Both passed a sealed blind routing run (18 pre-registered tasks over a 72-entry catalog): 7 of 7 and 7 of 7 at top 1; 4 of 4 out-of-scope tasks answered `none`; zero alternates needed.

### Changed
- The `skill-authoring` and `software-engineering` domain rows in the authoring vocabulary now cover third-party adoption and agent-tool server authoring.

The pack is now 47 skills, 238 leaves.

## 0.7.0 — 2026-10-30

### Added
- `ac-ideation` (critical-thinking, 7 leaves): generating and converging on options for a decision — framing, divergence rules, technique bank, nominal group, convergence scoring, idea capture, session record.
- `ac-inbound-triage` (collaboration, 7 leaves): routing inbound work before it is worked — queue definition, triage axes, the four dispositions, severity and escalation, batching and WIP limits, the triage log, false urgency.
- Both passed a sealed blind routing run (18 pre-registered tasks over a 70-entry catalog): 7 of 7 and 7 of 7 at top 1; 4 of 4 out-of-scope tasks answered `none`; zero alternates needed.

### Changed
- The `collaboration` and `critical-thinking` domain rows in the authoring vocabulary now cover triage and option generation.

The pack is now 45 skills, 224 leaves.

## 0.6.0 — 2026-10-29

### Added
- `ac-release-publish` (skill-authoring, 7 leaves): publishing a small public release of an agent-written artifact as a claim set — claim files, gates on the shipping bytes, an independent audit, repair and the delta audit, the release gate, push/tag/release mechanics, and live verification from a fresh clone.
- `ac-adversarial-corpus-challenge` (research-operations, 6 leaves): running a break-mandate round against a finished research corpus — charter, breaker selection, scoring, propagating breaks without rewriting the corpus, reserved judgment, and the round record. Converted from an earlier single-file skill, renamed with the `ac-` prefix, and its provenance notes rewritten as unnamed illustrations.

### Changed
- `ac-subskills-author` domain vocabulary: the `skill-authoring` row now covers publishing as well as authoring.

The pack is now 43 skills, 210 leaves.

## 0.5.0 — 2026-10-28

### Added
- `ac-interrogation` (critical-thinking, 8 leaves): interrogating an idea, plan, or decision before commitment — session protocol, question craft, assumption audit, failure mapping, evidence dial, alternative forcing, steelman discipline, close-and-stop.
- `ac-handoff` (collaboration, 7 leaves): transferring work between people, sessions, and agents — the handoff artifact, context selection, verbatim constraints, resumption checks, session and person handoffs, the quality bar.
- `ac-security-standards` (security-hardening, 2 leaves): which security standard exists, which edition is current, and what done means per hardening-task class.
- Two new top-level domains minted in the closed enum: `critical-thinking`, `collaboration`.
- All three passed a sealed blind routing run (24 pre-registered tasks over a 68-entry catalog): 8 of 8, 7 of 7, 5 of 5 at top 1; 4 of 4 out-of-scope tasks answered `none`.

### Changed
- Removed the last private dossier tags (`G-SEn`, `CE §n`) — bare Sources bullets and inline parentheticals in 12 files across 10 skills; three sentences reworded and two ⚠️ provenance flags added.
- `ac-security-engineer` and `ac-software-engineering-standards` descriptions now name each other as the boundary (security editions vs SE-lifecycle standards).

The pack is now 41 skills, 197 leaves.

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
