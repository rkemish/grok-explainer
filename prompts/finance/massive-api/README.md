# Massive API Investment Research Prompt Library

Use these templates with an LLM agent that has access to the Massive REST API and Massive API documentation at `https://massive.com/docs/llms.txt`.

Replace `{TICKER}` with the target symbol, such as `MU`, `NVDA`, or `AAPL`.

## Recommended Workflows

1. **Single-name deep dive:** Run prompts 1 through 10 in order to produce a full investment memo.
2. **Quick screen:** Run prompts 1, 2, and 4 to triage a company quickly.
3. **Risk check before buying:** Run prompts 5, 6, and 7 to stress-test position sizing.
4. **Monitoring an existing position:** Schedule prompt 3 after earnings and prompt 8 weekly.

## Prompt Index

| # | Prompt | Category | Best For | File |
| --- | --- | --- | --- | --- |
| 1 | Fundamentals Snapshot | Fundamentals | Quickly checking business health, growth, profitability, and balance-sheet quality | [fundamentals/fundamentals-snapshot.md](fundamentals/fundamentals-snapshot.md) |
| 2 | Valuation vs. History and Peers | Valuation | Comparing current multiples with company history and sector peers | [valuation/valuation-vs-history-and-peers.md](valuation/valuation-vs-history-and-peers.md) |
| 3 | Earnings Quality and Guidance Read | Earnings | Reviewing delivery, guidance changes, management tone, and market reaction | [earnings/earnings-quality-guidance-read.md](earnings/earnings-quality-guidance-read.md) |
| 4 | Sell-Side Coverage and Target Dispersion | Consensus | Aggregating analyst ratings, price targets, and estimate revisions | [consensus/sell-side-coverage-target-dispersion.md](consensus/sell-side-coverage-target-dispersion.md) |
| 5 | Ownership, Insider Activity, and Short Interest | Positioning | Detecting institutional, insider, activist, or short-interest signals | [positioning/ownership-insider-activity-short-interest.md](positioning/ownership-insider-activity-short-interest.md) |
| 6 | Price Action and Risk Profile | Risk | Measuring volatility, beta, drawdowns, macro sensitivity, and trend position | [risk/price-action-risk-profile.md](risk/price-action-risk-profile.md) |
| 7 | Options-Implied Outlook | Derivatives | Reading what options traders are pricing for volatility, direction, and earnings moves | [derivatives/options-implied-outlook.md](derivatives/options-implied-outlook.md) |
| 8 | News and Catalyst Scan | Catalysts | Clustering recent news, filings, events, and upcoming catalysts | [catalysts/news-catalyst-scan.md](catalysts/news-catalyst-scan.md) |
| 9 | Supply Chain, Customers, and Competitive Position | Competitive Position | Mapping business relationships and disclosed structural risks | [competitive-position/supply-chain-customers-competitive-position.md](competitive-position/supply-chain-customers-competitive-position.md) |
| 10 | Investment Thesis Synthesis with Scenarios | Thesis | Producing bull/base/bear cases, expected return, and tracking signals | [thesis/investment-thesis-synthesis-scenarios.md](thesis/investment-thesis-synthesis-scenarios.md) |

## Notes

- Prompts 2, 5, and 9 rely heavily on Massive API peer, relationship, ownership, and filing data. They are useful checks for whether the agent is actually querying the API instead of answering from memory.
- Keep endpoint names and fields in the final output whenever the prompt asks for them, so later research can be audited.
- Treat API gaps explicitly. If a field is unavailable, the agent should say so rather than substituting unsourced assumptions.
