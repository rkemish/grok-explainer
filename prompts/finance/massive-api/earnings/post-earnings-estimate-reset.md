# Post-Earnings Estimate Reset

Use this template for analyzing whether an earnings report changed the forward estimate path.

## Metadata

- **Analysis type:** Post-earnings reset analysis
- **Goal:** Determine whether `{TICKER}` had a real estimate reset, a sentiment reset, or only a price reaction.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`, `x_keyword_search`, `x_semantic_search`

## Grok Orchestration

- **Grok:** Deliver the reset verdict and next catalysts.
- **Harper:** Gather earnings headlines, management comments, analyst notes, and X reaction.
- **Benjamin:** Pull Massive earnings, guidance, analyst ratings, consensus, price, options, news, and fundamentals.
- **Lucas:** Audit actual versus estimate fields and post-report timing.

## Input

Analyze the post-earnings reset for `{TICKER}` after `{EARNINGS_DATE}`.

## Prompt

```text
Use Massive API data and Grok tools to analyze the post-earnings reset for {TICKER}.
Pull earnings actuals, estimates, guidance, analyst rating changes, consensus ratings,
price reaction, options data, news, and updated fundamentals where available.

Compare actuals versus expectations, guidance versus prior guide, stock move versus
implied move, and narrative reaction versus analyst action. Decide whether the report
created an upgrade cycle, downgrade cycle, temporary squeeze, or no fundamental reset.
```

## Output Requirements

- Include tables for actuals versus estimates, guidance changes, analyst changes, and implied versus realized move.
- Include management-tone and X-reaction summaries with attribution.
- Cite endpoints, fields, timestamps, web sources, and X windows.
- End with what would confirm or invalidate the reset.

## Quality Rules

- Do not assume estimate revisions before they appear in data.
- Distinguish price reaction from fundamentals.
- Flag missing post-report data or stale consensus.
- Paraphrase social posts and articles.
- Do not present the output as financial advice.
