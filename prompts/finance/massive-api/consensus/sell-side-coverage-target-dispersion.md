# Sell-Side Coverage and Target Dispersion

Use this template to aggregate Wall Street analyst views, including ratings, price targets, and recent estimate revisions.

## Analysis Type

Consensus and sentiment analysis.

## Goal

See where the Street stands, whether expectations are rising or falling, and which analysts have been most accurate on the name.

## Input

Analyze `{TICKER}` using the Massive API.

## Prompt

```text
Query the Massive API for all active analyst ratings, price targets, and estimate revisions
on {TICKER} over the last 180 days. Show me: distribution of ratings, mean/median/high/low
target, implied upside vs. current price, and the net direction of EPS and revenue revisions.
Highlight any analyst whose track record on this name (per the API's accuracy data, if
available) is materially better than the consensus.
```

## Output Requirements

- Include ratings distribution.
- Show mean, median, high, and low price targets.
- Calculate implied upside or downside versus current price.
- Summarize EPS and revenue revision direction.
- Identify stronger analyst track records only when Massive API accuracy data supports it.
