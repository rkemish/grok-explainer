# Market-Wide Risk Appetite Pulse

Use this template for reading current market-wide risk appetite from X narratives and cross-checking it against structured market data.

## Metadata

- **Analysis type:** Market sentiment snapshot
- **Goal:** Determine whether X is signaling risk-on, risk-off, crowded optimism, or panic for `{MARKET_OR_SECTOR}`.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`, Massive REST API, `code_execution`

## Grok Orchestration

- **Grok:** Synthesize crowd mood and structured market confirmation.
- **Harper:** Pull high-engagement and semantic X posts across market, sector, and asset keywords.
- **Benjamin:** Cross-check with Massive top movers, snapshots, indices, crypto, forex, and futures data.
- **Lucas:** Audit search windows, source credibility, and whether social claims match market data.

## Input

Build a market-wide risk appetite pulse for `{MARKET_OR_SECTOR}` over `{WINDOW}`.

## Prompt

```text
Build a market-wide X risk appetite pulse for {MARKET_OR_SECTOR}.
Use x_keyword_search and x_semantic_search with time-bounded searches for risk-on,
risk-off, panic, squeeze, rotation, crash, melt-up, AI stocks, rates, crypto, and the
relevant sector terms. Pull high-engagement posts and semantically relevant posts.

Cross-check the narrative with Massive snapshots, top movers, indices, crypto, forex,
futures, and news where available. Paraphrase all posts and classify credibility.
```

## Output Requirements

- Include sentiment bucket table: risk-on, risk-off, mixed, panic, complacent, or noisy.
- Include top narratives, source types, engagement, and credibility.
- Include Massive confirmation or contradiction.
- Include exact X search windows and Massive endpoints used.

## Quality Rules

- Paraphrase posts; do not quote them verbatim.
- Do not treat engagement as truth.
- Time-bound every X search.
- Attribute claims by source type and credibility.
- Do not present the output as financial advice.
