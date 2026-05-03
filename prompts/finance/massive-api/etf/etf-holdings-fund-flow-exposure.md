# ETF Holdings and Fund-Flow Exposure

Use this template for analyzing ETF ownership, constituents, flows, and exposure to a ticker or theme.

## Metadata

- **Analysis type:** ETF exposure analysis
- **Goal:** Identify ETF demand, flow risk, and thematic exposure for `{TICKER_OR_THEME}`.
- **Tools leveraged:** Massive REST API, `code_execution`

## Grok Orchestration

- **Grok:** Explain ETF-driven positioning and flow implications.
- **Benjamin:** Pull ETF Global profiles, constituents, fund flows, analytics, taxonomies, and relevant stock data.
- **Lucas:** Audit ETF coverage, holdings dates, and partner-data availability.

## Input

Analyze ETF holdings and fund-flow exposure for `{TICKER_OR_THEME}` over `{WINDOW}`.

## Prompt

```text
Use Massive API ETF Global partner data to analyze ETF exposure for {TICKER_OR_THEME}.
Pull ETF profiles, constituents, fund flows, analytics, taxonomies, stock snapshots, and
historical bars for relevant funds and underlying tickers.

Identify funds with meaningful exposure, recent inflows/outflows, concentration, sector
or theme classification, and whether ETF flows could amplify price moves.
```

## Output Requirements

- Include ETF exposure table and fund-flow table.
- Include concentration, liquidity, and theme-classification notes.
- Cite endpoints, fields, holdings dates, and timestamps.
- End with ETF-flow risks and watch items.

## Quality Rules

- Do not assume ETF holdings are real-time.
- Flag partner-data access gaps.
- Separate ETF flow from underlying company fundamentals.
- Avoid double-counting overlapping funds.
- Do not present the output as financial advice.
