# Pre-Earnings Setup

Use this template for preparing a structured pre-earnings setup from estimates, guidance, price action, options, and narrative.

## Metadata

- **Analysis type:** Pre-earnings setup
- **Goal:** Identify expectations, implied move, skew, and likely debate points before `{TICKER}` reports.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`, `x_keyword_search`, `x_semantic_search`

## Grok Orchestration

- **Grok:** Synthesize the pre-event setup and key surprise risks.
- **Harper:** Gather recent previews, management commentary, and X sentiment.
- **Benjamin:** Pull Massive earnings, guidance, analyst, options, price, technical, and fundamentals data.
- **Lucas:** Verify dates, stale estimates, endpoint coverage, and caveats.

## Input

Prepare a pre-earnings setup for `{TICKER}` reporting on `{EARNINGS_DATE}`.

## Prompt

```text
Use Massive API data and Grok tools to prepare a pre-earnings setup for {TICKER}.
Pull upcoming earnings, historical earnings, corporate guidance, consensus ratings,
analyst ratings, options chain snapshot, historical bars, technical indicators, ratios,
and news. Add web and X checks for market expectations and crowded narratives.

Compare consensus, guidance, recent revisions, implied move, historical moves, and key
questions likely to drive the stock after the report.
```

## Output Requirements

- Include estimate/guidance table, options-implied move table, historical reaction table, and narrative checklist.
- Include upside and downside surprise conditions.
- Cite Massive endpoints, fields, web sources, and X search windows.
- End with a pre-report watchlist.

## Quality Rules

- Do not treat X chatter as estimate data.
- Flag delayed or unavailable partner data.
- Separate expected move from directional view.
- State whether the report date is confirmed.
- Do not present the output as financial advice.
