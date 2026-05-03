# Related Ticker Peer Map

Use this template for building a data-backed peer set using Massive related tickers, news, returns, and fundamentals.

## Metadata

- **Analysis type:** Peer mapping
- **Goal:** Build a defensible peer universe for `{TICKER}` before valuation or competitive analysis.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Decide the final peer set and caveats.
- **Harper:** Check business-model similarity and recent competitive context.
- **Benjamin:** Pull related tickers, ticker overview, fundamentals, ratios, price correlations, and news.
- **Lucas:** Audit peer relevance and endpoint limitations.

## Input

Build a related ticker peer map for `{TICKER}`.

## Prompt

```text
Use Massive API data to build a peer map for {TICKER}.
Pull related tickers, ticker overview, news, income statements, ratios, historical bars,
and market snapshots for {TICKER} and candidate peers. Compare business descriptions,
sector, industry, size, growth, margins, valuation, price correlation, and shared news
themes.

Output a peer set suitable for valuation, risk, and narrative benchmarking.
```

## Output Requirements

- Include peer candidate table and final peer set.
- Include inclusion/exclusion rationale.
- Include endpoint and field citations.
- End with peer-set limitations.

## Quality Rules

- Do not accept related tickers blindly.
- Exclude structurally different businesses unless labeled.
- State whether peers are operational, valuation, or sentiment peers.
- Flag missing peer fundamentals.
- Do not present the output as financial advice.
