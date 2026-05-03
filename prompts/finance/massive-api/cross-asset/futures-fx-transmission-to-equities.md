# Futures and FX Transmission to Equities

Use this template for connecting futures and FX moves to equity sectors or single stocks.

## Metadata

- **Analysis type:** Cross-asset transmission analysis
- **Goal:** Explain how futures and FX moves may affect `{TICKERS_OR_SECTOR}`.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Translate cross-asset moves into ticker or sector implications.
- **Harper:** Gather macro and policy context behind futures or FX moves.
- **Benjamin:** Pull futures snapshots, futures bars, FX quotes, FX bars, indices, stock bars, and technical indicators.
- **Lucas:** Audit session timing, contract selection, and causality claims.

## Input

Analyze futures and FX transmission to `{TICKERS_OR_SECTOR}` over `{WINDOW}`.

## Prompt

```text
Use Massive API futures, forex, indices, and stock data to analyze transmission to
{TICKERS_OR_SECTOR}. Pull futures contracts, futures snapshots, futures aggregates,
forex quotes, forex aggregates, indices, stock snapshots, stock bars, and technical
indicators. Add web context for macro drivers.

Explain whether commodity, rates, currency, or index futures moves are likely tailwinds,
headwinds, or noise for the target equities.
```

## Output Requirements

- Include futures/FX move table and equity impact table.
- Include timing alignment and confidence level.
- Include endpoint, field, contract/ticker, and timestamp citations.
- End with follow-up market signals.

## Quality Rules

- Do not use the wrong futures contract without caveat.
- State time zones and market sessions.
- Separate direct economic exposure from sentiment readthrough.
- Flag missing or delayed futures data.
- Do not present the output as financial advice.
