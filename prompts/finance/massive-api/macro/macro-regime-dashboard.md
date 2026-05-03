# Macro Regime Dashboard

Use this template for summarizing macro regime conditions across rates, inflation, labor, FX, indices, futures, and crypto.

## Metadata

- **Analysis type:** Macro regime dashboard
- **Goal:** Identify whether conditions are risk-on, risk-off, inflationary, disinflationary, growth-positive, or growth-negative.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`, `x_keyword_search`

## Grok Orchestration

- **Grok:** Deliver the regime call and market implications.
- **Harper:** Gather policy, central bank, and market narrative.
- **Benjamin:** Pull Massive economy, indices, futures, forex, crypto, snapshots, bars, and technicals.
- **Lucas:** Audit data freshness and market-session differences.

## Input

Build a macro regime dashboard for `{REGION_OR_MARKET}` over `{WINDOW}`.

## Prompt

```text
Use Massive API economy and cross-asset endpoints to build a macro regime dashboard.
Pull treasury yields, inflation, inflation expectations, labor market data, indices,
futures, forex, crypto, stock top movers, snapshots, historical bars, and technical
indicators where available.

Classify the current regime and explain the strongest supporting and contradicting data.
```

## Output Requirements

- Include regime scorecard table.
- Include cross-asset confirmation and contradiction table.
- Include endpoint, field, date, and timestamp citations.
- End with next regime-change signals.

## Quality Rules

- Do not overfit one data release.
- State when markets are closed or data is delayed.
- Separate realized macro data from expectations.
- Include contradictions, not only supporting evidence.
- Do not present the output as financial advice.
