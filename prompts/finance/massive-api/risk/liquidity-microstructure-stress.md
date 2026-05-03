# Liquidity and Microstructure Stress

Use this template for evaluating whether trading conditions create execution or risk-management problems.

## Metadata

- **Analysis type:** Liquidity and microstructure risk
- **Goal:** Identify abnormal spreads, quote depth, volume, and trading stress for `{TICKER}`.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Summarize liquidity risk and practical implications.
- **Benjamin:** Pull stock quotes, trades, snapshots, aggregates, market status, condition codes, and options liquidity where relevant.
- **Lucas:** Audit market session, quote staleness, and condition-code interpretation.

## Input

Analyze liquidity and microstructure stress for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Use Massive API market data to evaluate liquidity and microstructure stress for {TICKER}.
Pull stock snapshot, last quote, last trade, historical quotes, trades, aggregates, market
status, exchanges, condition codes, and options chain snapshots if options are relevant.

Measure bid/ask spread, quote size, trade size, volume versus average, gap risk, abnormal
prints, halt/session context, and options spread quality.
```

## Output Requirements

- Include liquidity scorecard and stress-event table.
- Include spread, volume, quote, and trade metrics.
- Cite endpoints, fields, timestamps, and market-session state.
- End with execution-risk warnings and data caveats.

## Quality Rules

- Do not compare premarket liquidity to regular-session averages without labeling.
- Flag stale quotes and odd-lot or condition-code issues.
- Separate stock liquidity from options liquidity.
- State when tick-level data is unavailable.
- Do not present the output as financial advice.
