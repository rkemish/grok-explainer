# Grok Earnings Event War Room

Use this template for pre-earnings and post-earnings event analysis using Massive earnings, guidance, analyst data, options implied move, price action, web, and X.

## Metadata

- **Analysis type:** Earnings event analysis
- **Goal:** Frame the setup, expected move, consensus risk, narrative risk, and post-report estimate reset for `{TICKER}`.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`, `browse_page`, `x_keyword_search`, `x_semantic_search`, `x_thread_fetch`, `view_x_video`

## Grok Orchestration

- **Grok:** Synthesize the event setup and separate pre-event expectations from post-event facts.
- **Harper:** Pull recent earnings previews, management comments, X chatter, and post-call reactions.
- **Benjamin:** Use Massive earnings, guidance, options, aggregates, ratios, news, and analyst endpoints.
- **Lucas:** Audit whether the event is pre-report or post-report and whether estimates are current.

## Input

Prepare an earnings event war room for `{TICKER}` around `{EARNINGS_DATE}`.

## Prompt

```text
Build an earnings event war room for {TICKER} around {EARNINGS_DATE}.

If the report has not happened, focus on setup: consensus EPS/revenue, guidance history,
analyst revisions, options-implied move, realized volatility, price trend, crowded narratives,
and key questions for the call.

If the report has happened, focus on reset: actuals versus estimates, guidance changes,
price reaction, options repricing, analyst rating or target changes, management tone, X
reaction, and next catalysts.

Use Massive for structured data and web/X tools for narrative context. Grok must deliver
a single event read with confirmed facts separated from expectations and speculation.
```

## Output Requirements

- Label the report state as pre-earnings, intraday reaction, or post-earnings.
- Include tables for estimates versus actuals, options implied move versus realized move, analyst revisions, and narrative shifts.
- Include a "what would surprise the market" section.
- Include source freshness, endpoint names, and fields for all Massive data.
- End with the next 3-5 watch items.

## Quality Rules

- Do not treat social sentiment as consensus estimates.
- Do not infer call/put direction from volume without bid/ask and open-interest context.
- Flag delayed or unavailable earnings/guidance data.
- Paraphrase X posts and call transcripts.
- Do not present the output as financial advice.
