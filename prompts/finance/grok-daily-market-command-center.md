# Grok Daily Market Command Center

Use this template for a cross-market daily briefing that combines Massive market data, macro context, news, X sentiment, and multi-agent synthesis.

## Metadata

- **Analysis type:** Daily market command center
- **Goal:** Identify the most important cross-asset moves, catalysts, and narrative shifts before the trading day or after the close.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`, `browse_page`, `x_keyword_search`, `x_semantic_search`, `chatroom_send`

## Grok Orchestration

- **Grok:** Coordinate the workflow, reconcile contradictions, and deliver the final briefing.
- **Harper:** Pull current market news, central bank headlines, sector stories, and high-signal X narratives.
- **Benjamin:** Use `code_execution` and Massive to collect snapshots, movers, macro data, technicals, and cross-asset returns.
- **Lucas:** Audit tool coverage, freshness, endpoint choices, and whether any claims need caveats.

## Input

Build a daily market command center for `{DATE}` covering `{REGION_OR_MARKET}`, with special attention to `{WATCHLIST}`.

## Prompt

```text
Run a Grok-led daily market command center for {DATE}.

Benjamin: use Massive API endpoints for market status, stock snapshots, top movers,
indices, treasury yields, inflation/labor data if relevant, crypto snapshots, forex,
futures snapshots, and technical indicators. Compute 1D, 5D, MTD, and YTD moves where
available for {WATCHLIST}.

Harper: use web_search and X tools to identify the top macro headlines, company-specific
catalysts, sector narratives, and any viral claims affecting the same assets.

Lucas: verify every data source, endpoint, timestamp, and tool gap. Flag stale data,
unsupported claims, and any market closure or delayed-data issue.

Grok: synthesize into a concise market command center that separates confirmed market data
from narrative, rumor, and interpretation.
```

## Output Requirements

- Start with a 5-bullet executive tape read.
- Include a cross-asset table for equities, rates, FX, crypto, and futures where available.
- Include a top movers table with ticker, move, Massive endpoint, catalyst, and confidence.
- Include a narrative heat map: bullish, bearish, mixed, and unverified themes.
- End with what to watch next: data releases, earnings, technical levels, and invalidation signals.
- Cite Massive endpoints, fields, timestamps, web sources, and X search windows.

## Quality Rules

- Do not infer causality from price action alone.
- Separate confirmed data from social-media interpretation.
- Note market holidays, closed markets, delayed feeds, or unavailable endpoints.
- Paraphrase X posts and attribute narratives by account type, not as facts.
- Do not present the briefing as financial advice.
