# Multi-Timeframe Technical State

Use this template for evaluating trend, momentum, volatility, and support/resistance across multiple timeframes.

## Metadata

- **Analysis type:** Technical analysis
- **Goal:** Determine whether `{TICKER}` is trending, consolidating, reversing, or breaking down.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Translate technical state into risk/reward context.
- **Benjamin:** Pull Massive bars, SMA, EMA, RSI, MACD, snapshots, quotes, trades, and volume data.
- **Lucas:** Audit market session, adjusted prices, indicator settings, and incomplete bars.

## Input

Analyze the multi-timeframe technical state for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Use Massive API technical and price endpoints to analyze {TICKER}.
Pull daily and intraday aggregates where available, snapshot, previous-day bar, SMA, EMA,
RSI, MACD, last trade, last quote, and volume. Evaluate 1D, 5D, 20D, 50D, 200D, YTD,
and 1Y trend where available.

Identify trend state, momentum, volatility, volume confirmation, support/resistance, and
invalidating levels.
```

## Output Requirements

- Include technical dashboard table.
- Include support/resistance and momentum table.
- Include endpoint, field, indicator parameter, and timestamp citations.
- End with bullish, neutral, and bearish technical triggers.

## Quality Rules

- Do not treat technical levels as certainty.
- Flag incomplete intraday candles.
- State whether prices are adjusted.
- Separate technical setup from fundamental view.
- Do not present the output as financial advice.
