# Grok Single-Name War Room

Use this template for a full single-stock investment committee workflow that combines Massive fundamentals, valuation, options, filings, news, and X.

## Metadata

- **Analysis type:** Single-name investment war room
- **Goal:** Decide whether `{TICKER}` is attractive, overextended, structurally impaired, or only tradable around catalysts.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`, `browse_page`, `x_keyword_search`, `x_semantic_search`, `x_thread_fetch`, `chatroom_send`

## Grok Orchestration

- **Grok:** Chair the investment committee and deliver the final risk/reward view.
- **Harper:** Gather recent news, management commentary, credible web sources, and X narratives.
- **Benjamin:** Pull Massive fundamentals, ratios, price action, options, filings, ownership, short interest, and analyst data.
- **Lucas:** Check endpoint-field coverage, freshness, conflicting data, and missing evidence.

## Input

Analyze `{TICKER}` over `{HORIZON}` for `{INVESTOR_STYLE}`.

## Prompt

```text
Run a full Grok single-name war room on {TICKER}.

Benjamin: query Massive for ticker overview, single-ticker snapshot, historical bars,
income statements, balance sheets, cash flows, ratios, options chain snapshots, short
interest, short volume, Form 4 activity, 13-F filings, 10-K sections, 8-K text, news,
Benzinga ratings, consensus ratings, guidance, and earnings.

Harper: use web_search, browse_page, and X tools to capture recent news, management
statements, customer or product narratives, investor sentiment, bear cases, and rumors.

Lucas: audit whether every major claim maps to an endpoint, source, field, or clearly
labeled inference.

Grok: produce an investment committee memo with a clear stance, thesis, risks, catalysts,
and what would change the view.
```

## Output Requirements

- Include sections for executive view, business snapshot, fundamentals, valuation, price action, options, ownership, filings, news, X sentiment, bull/base/bear cases, and decision.
- Include tables for key metrics, valuation, options, catalysts, and risk register.
- Show Massive endpoints and fields used in a data appendix.
- Include source freshness for market data, financial statements, news, and X searches.
- End with monitoring triggers and thesis invalidation signals.

## Quality Rules

- Do not make a guaranteed prediction.
- Distinguish valuation risk, execution risk, sentiment risk, and liquidity risk.
- Treat rumors and X narratives as leads until verified.
- State unavailable fields or paywalled partner data explicitly.
- Do not present the output as financial advice.
