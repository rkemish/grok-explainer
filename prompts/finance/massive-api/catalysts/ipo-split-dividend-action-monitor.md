# IPO Split Dividend Action Monitor

Use this template for monitoring corporate actions that can change share structure, yield, or trading behavior.

## Metadata

- **Analysis type:** Corporate action monitor
- **Goal:** Detect IPO, split, and dividend events relevant to `{TICKER}` or `{TICKERS}`.
- **Tools leveraged:** Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Explain investment relevance and avoid mechanical overreaction.
- **Harper:** Cross-check corporate action announcements and company sources.
- **Benjamin:** Pull dividends, splits, IPOs, ticker events, snapshots, historical bars, and fundamentals.
- **Lucas:** Audit dates, adjustment factors, deprecated endpoints, and data freshness.

## Input

Monitor IPO, split, and dividend actions for `{TICKERS}` over `{WINDOW}`.

## Prompt

```text
Use Massive API current corporate action endpoints to monitor IPOs, splits, dividends,
and ticker events for {TICKERS}. Pull dividends, splits, IPOs, ticker events, stock
snapshots, historical bars, ratios, and cash-flow data where relevant.

Classify each action by mechanical impact, investor relevance, liquidity impact, and
whether it changes the thesis or only changes share/yield presentation.
```

## Output Requirements

- Include corporate action table with event date, declaration date, ex-date, pay date, ratio or amount, and source.
- Include expected mechanical impact and thesis relevance.
- Cite endpoints, fields, and timestamps.
- End with watch items and data gaps.

## Quality Rules

- Use current Massive dividends and splits endpoints, not deprecated reference endpoints.
- Distinguish split optics from valuation change.
- Flag special dividends and adjustment-factor issues.
- Cross-check event dates when material.
- Do not present the output as financial advice.
