# Customer Spending Anecdote Map

Use this template for mapping customer anecdotes on X and checking whether they align with data-backed demand signals.

## Metadata

- **Analysis type:** Customer anecdote analysis
- **Goal:** Identify whether customer posts suggest demand strength, weakness, churn, or pricing pressure for `{TICKER}`.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`, `x_user_search`, Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Synthesize anecdotal demand signal and confidence.
- **Harper:** Gather customer, buyer, reseller, developer, and end-user posts.
- **Benjamin:** Pull Massive fundamentals, news, merchant data where relevant, and price action.
- **Lucas:** Audit sample bias, source identity, and unsupported extrapolation.

## Input

Map customer spending anecdotes for `{TICKER}` or `{PRODUCT}` over `{WINDOW}`.

## Prompt

```text
Map X customer spending anecdotes for {TICKER_OR_PRODUCT}.
Use time-bounded keyword and semantic searches for product names, pricing, renewal, churn,
upgrade, downgrade, demand, backorder, discount, waitlist, cancellation, and customer
experience terms. Use user search to classify accounts as customers, employees, resellers,
developers, influencers, or unknown.

Cross-check with Massive fundamentals, news, and alternative merchant data where available.
```

## Output Requirements

- Include anecdote table with source type, claim, direction, credibility, and relevance.
- Include demand signal summary and sample-bias caveats.
- Include Massive data cross-check and endpoints used.
- Include exact X search windows.

## Quality Rules

- Do not extrapolate revenue from anecdotes alone.
- Paraphrase posts.
- Weight verified customers higher than anonymous accounts.
- Separate product satisfaction from spending behavior.
- Do not present the output as financial advice.
