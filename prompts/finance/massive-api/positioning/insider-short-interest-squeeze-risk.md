# Insider Activity and Short-Interest Squeeze Risk

Use this template for combining insider transactions, short interest, short volume, float, and price action.

## Metadata

- **Analysis type:** Positioning and squeeze-risk analysis
- **Goal:** Detect whether `{TICKER}` has insider-confirmation, insider-risk, or squeeze-risk characteristics.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Synthesize insider and short-positioning signals.
- **Benjamin:** Pull Form 3, Form 4, short interest, short volume, float, snapshots, and price history.
- **Lucas:** Audit transaction coding, reporting dates, and float assumptions.

## Input

Analyze insider activity and squeeze risk for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Use Massive API data to evaluate insider activity and short-interest squeeze risk for
{TICKER}. Pull Form 3, Form 4, short interest, short volume, float, stock snapshot,
historical bars, last trade, and relevant news.

Classify insider transactions by purchase, sale, option exercise, award, automatic plan,
or unclear. Compute short interest as a percentage of float where available, days to cover,
short-volume trend, price momentum, and liquidity conditions.
```

## Output Requirements

- Include insider transaction table and short-positioning table.
- Include squeeze-risk rating: low, watch, elevated, high, or data insufficient.
- Include endpoint, field, date, and formula citations.
- End with triggers that would increase or reduce squeeze risk.

## Quality Rules

- Do not treat all insider sales as bearish.
- Do not call a squeeze without float, short interest, volume, and price context.
- Flag delayed FINRA data.
- Separate insider signal from short-interest signal.
- Do not present the output as financial advice.
