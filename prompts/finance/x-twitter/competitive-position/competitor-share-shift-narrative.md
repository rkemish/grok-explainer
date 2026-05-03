# Competitor Share-Shift Narrative

Use this template for tracking whether X suggests market-share shifts between competitors and whether data supports it.

## Metadata

- **Analysis type:** Competitive narrative analysis
- **Goal:** Identify credible share-shift claims among `{TICKERS}`.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`, `x_thread_fetch`, Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Decide whether the share-shift narrative is credible, early, or unsupported.
- **Harper:** Pull customer, channel, analyst, and industry posts.
- **Benjamin:** Pull Massive fundamentals, related tickers, news, price action, and filings.
- **Lucas:** Audit claim quality, source identity, and data limitations.

## Input

Analyze competitor share-shift narratives for `{TICKERS}` over `{WINDOW}`.

## Prompt

```text
Analyze X narratives about share shifts among {TICKERS}.
Use time-bounded searches for competitor names, product names, win, loss, switch, churn,
share gain, share loss, pricing, backlog, channel checks, and customer names where relevant.
Fetch high-signal threads and classify sources.

Cross-check with Massive related tickers, fundamentals, news, filings, price action, and
analyst data where available. Separate anecdote from measurable share shift.
```

## Output Requirements

- Include share-shift claim table with source type, direction, evidence, and credibility.
- Include Massive cross-check and data gaps.
- Include search windows, endpoints, fields, and timestamps.
- End with claims worth monitoring.

## Quality Rules

- Do not infer market share from isolated anecdotes.
- Paraphrase posts.
- Separate customer win/loss claims from revenue impact.
- Flag competitor-specific data limitations.
- Do not present the output as financial advice.
