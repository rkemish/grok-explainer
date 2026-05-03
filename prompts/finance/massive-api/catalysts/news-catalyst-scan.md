# News and Catalyst Scan

Use this template to sweep recent news, filings, and events, then organize them by theme and list what is coming next.

## Analysis Type

Event and catalyst analysis.

## Goal

Identify what has been moving the stock recently and what could move it in the near future.

## Input

Analyze `{TICKER}` using the Massive API.

## Prompt

```text
Pull every news item, SEC filing, and corporate event for {TICKER} from the Massive API for
the last 90 days. Cluster by theme (product, regulatory, M&A, management, macro). For each
cluster, summarize in 2-3 sentences in your own words and rate materiality (low/med/high).
Then list the next 4 known forward catalysts (earnings, investor day, product launch,
regulatory decisions) with dates from the API's calendar endpoint.
```

## Output Requirements

- Cover the last 90 days.
- Cluster items by product, regulatory, M&A, management, macro, or another justified theme.
- Summarize each cluster in two to three sentences.
- Rate materiality as low, medium, or high.
- List the next four known forward catalysts with dates from the Massive API calendar endpoint.

## Source Discipline

- Cite every Massive endpoint and field used, including headline, publisher, timestamp, sentiment, ticker, event date, and data freshness fields.
- State unavailable fields explicitly instead of substituting assumptions.
- Do not present the output as financial advice.
