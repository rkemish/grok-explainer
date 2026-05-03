# Options-Flow Social Confirmation

Use this template for checking whether X options-flow narratives match Massive options data.

## Metadata

- **Analysis type:** Options narrative verification
- **Goal:** Validate whether social claims about `{TICKER}` options flow are supported by structured options data.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`, Massive REST API, `code_execution`

## Grok Orchestration

- **Grok:** Decide whether the social flow narrative is confirmed, overstated, or unsupported.
- **Harper:** Find X flow claims, screenshots, and trader commentary.
- **Benjamin:** Pull Massive options trades, quotes, chain snapshots, contract snapshots, and underlying price.
- **Lucas:** Audit contract identifiers, timestamps, liquidity, and buyer/seller uncertainty.

## Input

Verify social options-flow claims for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Use X tools and Massive options data to verify social options-flow claims for {TICKER}.
Search X for {TICKER} options, calls, puts, sweep, unusual flow, whale, lotto, IV, skew,
and expiration terms during {WINDOW}. Extract claimed contracts and paraphrase the thesis.

Then use Massive options endpoints to verify volume, open interest, bid/ask spread, trade
price, quote context, underlying price, and whether the claim is likely directional,
hedged, rolled, or unverifiable.
```

## Output Requirements

- Include social claim table and Massive verification table.
- Include confidence rating for each flow claim.
- Include exact X windows, source credibility, endpoints, fields, and timestamps.
- End with confirmed signals and rejected claims.

## Quality Rules

- Do not assume screenshots are complete data.
- Do not infer buyer initiation without quote context.
- Paraphrase X posts and identify source type.
- Use time-bound X searches and state the exact search window.
- Flag illiquid contracts.
- Do not present the output as financial advice.
