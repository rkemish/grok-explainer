# Analyst Revision Momentum

Use this template for measuring whether analyst sentiment and estimates are improving or deteriorating.

## Metadata

- **Analysis type:** Sell-side revision analysis
- **Goal:** Track rating, target, earnings, and guidance momentum for `{TICKER}`.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Explain whether revisions support or undermine the thesis.
- **Benjamin:** Pull Benzinga analyst ratings, consensus ratings, guidance, earnings, and price data through Massive.
- **Lucas:** Audit partner-data freshness and unavailable fields.

## Input

Analyze analyst revision momentum for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Use Massive API partner and market data to measure analyst revision momentum for {TICKER}.
Pull analyst ratings, analyst insights if available, consensus ratings, guidance, earnings,
news, and price history. Classify each action as upgrade, downgrade, target increase,
target cut, initiation, reiteration, or guidance-related change.

Summarize whether revisions are broadening, fading, concentrated in one firm, or mixed.
```

## Output Requirements

- Include analyst action table with date, firm, action, target, rating, and source endpoint.
- Include consensus trend and target dispersion.
- Include price reaction around major revisions.
- Cite endpoints, fields, and timestamp.

## Quality Rules

- Do not treat target prices as intrinsic value.
- Separate rating action from estimate action.
- Flag partner-data gaps.
- Note whether revisions are stale or recent.
- Do not present the output as financial advice.
