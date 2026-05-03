# Grok Portfolio Risk Radar

Use this template for a multi-name portfolio risk monitor covering drawdowns, filings, short interest, insider activity, news, options, and sentiment.

## Metadata

- **Analysis type:** Portfolio risk monitoring
- **Goal:** Surface the names in `{TICKERS}` with the highest near-term risk and explain the evidence.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`, `x_keyword_search`, `x_semantic_search`, `chatroom_send`

## Grok Orchestration

- **Grok:** Rank risks and decide which names require action or deeper review.
- **Harper:** Find news, X narratives, rumors, and external catalysts for the watchlist.
- **Benjamin:** Pull Massive price action, volatility, short interest, filings, options, analyst, and news data for every ticker.
- **Lucas:** Audit coverage gaps, stale data, and whether risk rankings are evidence-backed.

## Input

Run a portfolio risk radar for `{TICKERS}` over `{WINDOW}`.

## Prompt

```text
Run a Grok portfolio risk radar for {TICKERS} over {WINDOW}.

Benjamin: use Massive to compute drawdowns, realized volatility, beta proxies, abnormal
volume, technical breaks, short interest changes, short volume trends, insider selling,
13-F holder turnover, 8-K events, risk-factor changes, options activity, analyst changes,
and news sentiment.

Harper: scan web and X for company-specific controversies, product problems, management
issues, macro readthroughs, and coordinated bear narratives.

Lucas: verify data freshness and separate source-backed risks from unverified chatter.

Grok: rank the portfolio from highest to lowest risk and explain the top drivers.
```

## Output Requirements

- Include a portfolio risk ranking table with severity, evidence, source, and actionability.
- Include separate sections for market risk, fundamental risk, event risk, sentiment risk, and liquidity/options risk.
- Flag any ticker requiring a dedicated war room.
- Show endpoints, fields, and search windows used.
- End with monitoring triggers for the next week.

## Quality Rules

- Do not over-rank a risk based on one viral claim.
- Normalize price and volatility metrics across tickers.
- State when a risk is only a watch item, not a confirmed impairment.
- Include data gaps for any ticker with incomplete coverage.
- Do not present the output as financial advice.
