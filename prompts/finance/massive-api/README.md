# Massive API Investment Research Prompt Library

Use these templates with Grok and its agent team when an investment workflow needs structured market data from the Massive REST API and Massive API documentation at `https://massive.com/docs/llms.txt`.

Replace `{TICKER}` with the target symbol, such as `MU`, `NVDA`, or `AAPL`. Replace `{TICKERS}`, `{WINDOW}`, `{HORIZON}`, and other placeholders where present.

## Recommended Workflows

1. **Single-name deep dive:** Run prompts 1, 2, 4, 7, 9, 15, 20, 27, 28, and 32.
2. **Pre-earnings setup:** Run prompts 8, 11, 13, 17, 20, 24, and pair with X earnings prompts.
3. **Risk check before buying:** Run prompts 6, 16, 18, 19, 20, 21, 22, and 23.
4. **Macro and cross-asset monitor:** Run prompts 37, 38, 40, 41, and 42.
5. **Sector or basket screen:** Run prompts 10, 25, 27, 28, 33, 34, 39, and 42.

## Prompt Index

| # | Prompt | Category | Best For | File |
| --- | --- | --- | --- | --- |
| 1 | Fundamentals Snapshot | Fundamentals | Quickly checking business health, growth, profitability, and balance-sheet quality | [fundamentals/fundamentals-snapshot.md](fundamentals/fundamentals-snapshot.md) |
| 2 | Revenue Quality and Accruals | Fundamentals | Testing whether growth is supported by cash conversion and working capital | [fundamentals/revenue-quality-accruals.md](fundamentals/revenue-quality-accruals.md) |
| 3 | Margin Inflection | Fundamentals | Detecting gross, operating, net, and FCF margin turns | [fundamentals/margin-inflection.md](fundamentals/margin-inflection.md) |
| 4 | Capital Allocation and ROIC | Fundamentals | Assessing reinvestment, buybacks, dividends, leverage, and returns | [fundamentals/capital-allocation-roic.md](fundamentals/capital-allocation-roic.md) |
| 5 | Valuation vs. History and Peers | Valuation | Comparing current multiples with company history and sector peers | [valuation/valuation-vs-history-and-peers.md](valuation/valuation-vs-history-and-peers.md) |
| 6 | Reverse DCF Expectations | Valuation | Backing into growth and margin assumptions implied by current price | [valuation/reverse-dcf-expectations.md](valuation/reverse-dcf-expectations.md) |
| 7 | Multiples Dislocation | Valuation | Finding justified or unjustified valuation gaps versus peers and history | [valuation/multiples-dislocation.md](valuation/multiples-dislocation.md) |
| 8 | Shareholder Yield and Payout Durability | Valuation | Testing dividend, buyback, and cash-flow sustainability | [valuation/shareholder-yield-payout-durability.md](valuation/shareholder-yield-payout-durability.md) |
| 9 | Earnings Quality and Guidance Read | Earnings | Reviewing delivery, guidance changes, management tone, and market reaction | [earnings/earnings-quality-guidance-read.md](earnings/earnings-quality-guidance-read.md) |
| 10 | Pre-Earnings Setup | Earnings | Preparing consensus, guidance, implied move, and narrative risk before a report | [earnings/pre-earnings-setup.md](earnings/pre-earnings-setup.md) |
| 11 | Post-Earnings Estimate Reset | Earnings | Measuring whether a report changed estimates, guidance, and sentiment | [earnings/post-earnings-estimate-reset.md](earnings/post-earnings-estimate-reset.md) |
| 12 | Sell-Side Coverage and Target Dispersion | Consensus | Aggregating analyst ratings, price targets, and estimate revisions | [consensus/sell-side-coverage-target-dispersion.md](consensus/sell-side-coverage-target-dispersion.md) |
| 13 | Analyst Revision Momentum | Consensus | Tracking upgrades, downgrades, target moves, and guidance-linked revisions | [consensus/analyst-revision-momentum.md](consensus/analyst-revision-momentum.md) |
| 14 | Benzinga Bulls Bears Thesis Map | Consensus | Mapping analyst bull and bear cases to source-backed evidence | [consensus/benzinga-bulls-bears-thesis-map.md](consensus/benzinga-bulls-bears-thesis-map.md) |
| 15 | Ownership, Insider Activity, and Short Interest | Positioning | Detecting institutional, insider, activist, or short-interest signals | [positioning/ownership-insider-activity-short-interest.md](positioning/ownership-insider-activity-short-interest.md) |
| 16 | 13-F Crowding and Holder Turnover | Positioning | Evaluating institutional crowding, holder turnover, and sponsorship quality | [positioning/13f-crowding-holder-turnover.md](positioning/13f-crowding-holder-turnover.md) |
| 17 | Insider Activity and Short-Interest Squeeze Risk | Positioning | Combining Form 4 activity, float, short interest, short volume, and price action | [positioning/insider-short-interest-squeeze-risk.md](positioning/insider-short-interest-squeeze-risk.md) |
| 18 | Price Action and Risk Profile | Risk | Measuring volatility, beta, drawdowns, macro sensitivity, and trend position | [risk/price-action-risk-profile.md](risk/price-action-risk-profile.md) |
| 19 | Filing Risk-Factor Delta | Risk | Comparing risk-factor language across filings | [risk/filing-risk-factor-delta.md](risk/filing-risk-factor-delta.md) |
| 20 | 8-K Material Event Triage | Risk | Classifying recent 8-K events by materiality and thesis impact | [risk/8k-material-event-triage.md](risk/8k-material-event-triage.md) |
| 21 | Liquidity and Microstructure Stress | Risk | Detecting abnormal spreads, volume, quote quality, and execution risk | [risk/liquidity-microstructure-stress.md](risk/liquidity-microstructure-stress.md) |
| 22 | Options-Implied Outlook | Derivatives | Reading what options traders are pricing for volatility, direction, and earnings moves | [derivatives/options-implied-outlook.md](derivatives/options-implied-outlook.md) |
| 23 | Options Skew and Term Structure | Derivatives | Reading options volatility demand across strikes and expirations | [derivatives/skew-term-structure.md](derivatives/skew-term-structure.md) |
| 24 | Implied Versus Realized Move | Derivatives | Comparing options-implied moves with historical and event moves | [derivatives/implied-vs-realized-move.md](derivatives/implied-vs-realized-move.md) |
| 25 | Unusual Options Flow Verification | Derivatives | Verifying whether reported unusual flow is liquid, directional, and real | [derivatives/unusual-options-flow-verification.md](derivatives/unusual-options-flow-verification.md) |
| 26 | News and Catalyst Scan | Catalysts | Clustering recent news, filings, events, and upcoming catalysts | [catalysts/news-catalyst-scan.md](catalysts/news-catalyst-scan.md) |
| 27 | Corporate Events Calendar | Catalysts | Building a forward-looking earnings, guidance, dividend, split, and event calendar | [catalysts/corporate-events-calendar.md](catalysts/corporate-events-calendar.md) |
| 28 | Massive News Sentiment Validator | Catalysts | Checking news sentiment against price action, fundamentals, web, and X | [catalysts/massive-news-sentiment-validator.md](catalysts/massive-news-sentiment-validator.md) |
| 29 | IPO Split Dividend Action Monitor | Catalysts | Monitoring corporate actions that affect share structure, yield, or trading behavior | [catalysts/ipo-split-dividend-action-monitor.md](catalysts/ipo-split-dividend-action-monitor.md) |
| 30 | Supply Chain, Customers, and Competitive Position | Competitive Position | Mapping business relationships and disclosed structural risks | [competitive-position/supply-chain-customers-competitive-position.md](competitive-position/supply-chain-customers-competitive-position.md) |
| 31 | Related Ticker Peer Map | Competitive Position | Building a defensible peer set from related tickers, news, returns, and fundamentals | [competitive-position/related-ticker-peer-map.md](competitive-position/related-ticker-peer-map.md) |
| 32 | 10-K Moat Language | Competitive Position | Extracting competitive advantage and risk language from filings | [competitive-position/10k-moat-language.md](competitive-position/10k-moat-language.md) |
| 33 | Customer Concentration Readthrough | Competitive Position | Mapping customer, supplier, and end-market dependency risk | [competitive-position/customer-concentration-readthrough.md](competitive-position/customer-concentration-readthrough.md) |
| 34 | Investment Thesis Synthesis with Scenarios | Thesis | Producing bull/base/bear cases, expected return, and tracking signals | [thesis/investment-thesis-synthesis-scenarios.md](thesis/investment-thesis-synthesis-scenarios.md) |
| 35 | Multi-Timeframe Technical State | Technicals | Evaluating trend, momentum, volatility, and support/resistance | [technicals/multi-timeframe-technical-state.md](technicals/multi-timeframe-technical-state.md) |
| 36 | Relative Strength Rotation Screen | Technicals | Ranking tickers by relative strength, momentum, volatility, and breadth | [technicals/relative-strength-rotation-screen.md](technicals/relative-strength-rotation-screen.md) |
| 37 | Rates Inflation Labor Sensitivity | Macro | Connecting rates, inflation, and labor data to company or sector exposure | [macro/rates-inflation-labor-sensitivity.md](macro/rates-inflation-labor-sensitivity.md) |
| 38 | Macro Regime Dashboard | Macro | Summarizing macro regime across rates, inflation, labor, FX, futures, indices, and crypto | [macro/macro-regime-dashboard.md](macro/macro-regime-dashboard.md) |
| 39 | ETF Holdings and Fund-Flow Exposure | ETF | Analyzing ETF ownership, constituents, fund flows, and thematic exposure | [etf/etf-holdings-fund-flow-exposure.md](etf/etf-holdings-fund-flow-exposure.md) |
| 40 | Merchant Spending Readthrough | Alternative | Using merchant spending data to infer demand trends where coverage supports it | [alternative/merchant-spending-readthrough.md](alternative/merchant-spending-readthrough.md) |
| 41 | Crypto Risk-Appetite Readthrough | Cross-Asset | Using crypto behavior as a risk-appetite signal for equities or sectors | [cross-asset/crypto-risk-appetite-readthrough.md](cross-asset/crypto-risk-appetite-readthrough.md) |
| 42 | Futures and FX Transmission to Equities | Cross-Asset | Connecting futures and FX moves to equity sectors or single stocks | [cross-asset/futures-fx-transmission-to-equities.md](cross-asset/futures-fx-transmission-to-equities.md) |

## Operating Notes

- Prefer current Massive endpoints and avoid deprecated reference endpoints where replacements exist.
- Keep endpoint names, fields, dates, and timestamps in final outputs so research can be audited.
- Treat API gaps explicitly. If a field is unavailable, the agent should say so rather than substituting assumptions.
- Use Grok orchestration for complex workflows: Benjamin handles quantitative Massive queries, Harper handles web/X context, Lucas audits tool coverage and data freshness, and Grok synthesizes.
- These prompts support investment research workflows and should not be used as financial advice.
