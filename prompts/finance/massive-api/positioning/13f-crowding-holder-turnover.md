# 13-F Crowding and Holder Turnover

Use this template for evaluating institutional crowding, holder turnover, and sponsorship quality.

## Metadata

- **Analysis type:** Institutional positioning analysis
- **Goal:** Determine whether `{TICKER}` ownership is stable, crowded, accumulating, or distributing.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Translate ownership changes into positioning risk.
- **Benjamin:** Pull 13-F filings, ticker overview, price history, volume, and related ownership data.
- **Lucas:** Audit filing lag, duplicate managers, and missing fields.

## Input

Analyze 13-F crowding and holder turnover for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Use Massive API 13-F data to analyze institutional positioning for {TICKER}.
Pull recent and historical 13-F filings, market data, and ticker overview. Identify top
holders, new buyers, sellers, adds, trims, concentration, turnover, and timing relative
to price changes.

Account for 13-F reporting lag and distinguish accumulation from stale disclosed positions.
```

## Output Requirements

- Include top holders, largest adds, largest trims, new positions, and exits.
- Include crowding and turnover assessment.
- Include filing dates, report periods, endpoints, and fields.
- End with positioning risks and follow-up signals.

## Quality Rules

- Always mention 13-F lag.
- Do not treat reported holdings as real-time positions.
- Flag incomplete manager or CUSIP mapping.
- Avoid over-interpreting one quarter.
- Do not present the output as financial advice.
