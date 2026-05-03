# Options Skew and Term Structure

Use this template for reading options skew, term structure, and volatility demand.

## Metadata

- **Analysis type:** Options volatility structure
- **Goal:** Determine what the options market is pricing for `{TICKER}` across expirations and strikes.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Explain the options market message in plain English.
- **Benjamin:** Pull option chain snapshots, contract overview, quotes, trades, aggregates, and underlying price.
- **Lucas:** Audit contract filters, stale quotes, bid/ask quality, and illiquidity.

## Input

Analyze options skew and term structure for `{TICKER}` over `{EXPIRATION_WINDOW}`.

## Prompt

```text
Use Massive API options endpoints to analyze skew and term structure for {TICKER}.
Pull option chain snapshots, option contract snapshots, contract overview, options quotes,
options trades, option aggregates, and underlying stock snapshot.

Compare implied volatility by expiration, strike, call/put side, moneyness, and liquidity.
Highlight put skew, call skew, event volatility, term structure inversion, and contracts
where spreads or stale quotes make the signal unreliable.
```

## Output Requirements

- Include expiration-level term structure table and strike-level skew table.
- Include liquidity table with bid/ask spread, volume, open interest, and timestamp.
- Cite endpoints, fields, contract filters, and pull time.
- End with what the options market appears to fear or chase.

## Quality Rules

- Do not infer direction from IV alone.
- Exclude or flag illiquid contracts.
- Distinguish volume from open interest.
- State if Greeks or IV are unavailable.
- Do not present the output as financial advice.
