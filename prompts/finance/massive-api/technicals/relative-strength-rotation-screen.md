# Relative Strength Rotation Screen

Use this template for ranking tickers by relative strength, momentum, volatility, and breadth.

## Metadata

- **Analysis type:** Relative strength screen
- **Goal:** Identify leaders, laggards, improving names, and deteriorating names in `{TICKERS}`.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Rank the screen and explain investable conclusions.
- **Benjamin:** Pull historical bars, snapshots, indices, technical indicators, and volume data.
- **Lucas:** Audit benchmark selection, adjusted prices, and missing tickers.

## Input

Run a relative strength rotation screen for `{TICKERS}` versus `{BENCHMARK}` over `{WINDOW}`.

## Prompt

```text
Use Massive API data to run a relative strength screen for {TICKERS} against {BENCHMARK}.
Pull snapshots, custom bars, previous-day bars, SMA, EMA, RSI, MACD, and volume data.
Compute 1D, 5D, 20D, 3M, 6M, YTD, and 1Y returns where available, plus volatility,
drawdown, trend state, and volume confirmation.

Rank names by leadership, improvement, deterioration, and avoid/watch status.
```

## Output Requirements

- Include ranked relative strength table.
- Include leader/laggard and improving/deteriorating buckets.
- Include endpoint, field, benchmark, and timestamp citations.
- End with names requiring deeper research.

## Quality Rules

- Use consistent windows across tickers.
- Flag missing or stale data.
- Do not rank illiquid names without caveats.
- Separate absolute momentum from benchmark-relative strength.
- Do not present the output as financial advice.
