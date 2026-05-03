# Corporate Events Calendar

Use this template for building a forward-looking corporate event calendar and catalyst map.

## Metadata

- **Analysis type:** Catalyst calendar
- **Goal:** Identify upcoming events that may move `{TICKER}` or `{TICKERS}`.
- **Tools leveraged:** Massive REST API, `web_search`, `x_keyword_search`

## Grok Orchestration

- **Grok:** Rank catalysts by likely thesis impact.
- **Harper:** Cross-check events with company calendars, web sources, and X chatter.
- **Benjamin:** Pull Massive corporate events, earnings, guidance, dividends, splits, IPOs, ticker events, and news.
- **Lucas:** Audit event dates, source conflicts, and partner-data gaps.

## Input

Build a corporate events calendar for `{TICKERS}` over `{WINDOW}`.

## Prompt

```text
Use Massive API corporate action, partner, and news endpoints to build a catalyst calendar
for {TICKERS}. Pull TMX corporate events, Benzinga earnings, guidance, dividends, splits,
IPOs, ticker events, Massive news, and market snapshots.

Add web and X checks for events that may not appear in structured data. Rank each catalyst
by certainty, likely market impact, and what data would confirm it.
```

## Output Requirements

- Include event calendar table with date, ticker, event type, source, certainty, and expected relevance.
- Include highest-impact catalyst list.
- Include source conflicts or missing data.
- Cite endpoints, fields, timestamps, web sources, and X windows.

## Quality Rules

- Do not treat rumored events as scheduled.
- Separate confirmed dates from expected windows.
- Flag partner-data limitations.
- State time zone when relevant.
- Do not present the output as financial advice.
