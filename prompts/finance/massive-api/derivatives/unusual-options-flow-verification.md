# Unusual Options Flow Verification

Use this template for verifying whether reported unusual options flow is actually unusual, liquid, and directional.

## Metadata

- **Analysis type:** Options flow verification
- **Goal:** Validate or reject an unusual-options claim for `{TICKER}`.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`, `x_keyword_search`

## Grok Orchestration

- **Grok:** Decide whether the flow is meaningful or noise.
- **Harper:** Find the claim source across web or X and capture the stated interpretation.
- **Benjamin:** Pull Massive options trades, quotes, chain snapshots, contract snapshots, aggregates, and underlying stock data.
- **Lucas:** Audit timestamps, bid/ask direction, liquidity, and data gaps.

## Input

Verify unusual options flow for `{TICKER}` around `{CLAIM_OR_WINDOW}`.

## Prompt

```text
Use Massive API data to verify unusual options flow for {TICKER}.
Identify the contracts mentioned in {CLAIM_OR_WINDOW}, then pull contract overview,
trades, quotes, option snapshots, aggregates, and underlying stock snapshots. Compare
contract volume versus open interest, recent volume history, bid/ask spread, trade price
relative to bid/ask, expiration, strike, moneyness, and underlying price move.

Decide whether the claim is supported, partially supported, unsupported, or unverifiable.
```

## Output Requirements

- Include claim summary and source.
- Include contract verification table.
- Include directional confidence and liquidity caveats.
- Cite Massive endpoints, fields, timestamps, and search windows.

## Quality Rules

- Do not assume call buying is bullish without trade context.
- Flag sweeps, spreads, rolls, and hedges when uncertain.
- Do not quote social posts verbatim.
- State when data cannot prove buyer/seller initiation.
- Do not present the output as financial advice.
