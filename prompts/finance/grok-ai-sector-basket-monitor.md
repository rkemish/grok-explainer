# Grok AI Sector Basket Monitor

Use this template for an AI-stock basket dashboard comparing fundamentals, valuation, momentum, options, catalysts, and narrative strength.

## Metadata

- **Analysis type:** Sector basket monitor
- **Goal:** Compare `{TICKERS}` as AI beneficiaries, AI infrastructure plays, AI software names, or AI narrative stocks.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`, `browse_page`, `x_keyword_search`, `x_semantic_search`

## Grok Orchestration

- **Grok:** Classify each ticker and synthesize sector-level conclusions.
- **Harper:** Collect AI news, product launches, customer commentary, and X narrative momentum.
- **Benjamin:** Pull Massive fundamentals, valuation, price action, options, analyst, filings, and news data.
- **Lucas:** Verify that AI claims are sourced and that comparable metrics are aligned.

## Input

Monitor the AI sector basket `{TICKERS}` over `{WINDOW}`.

## Prompt

```text
Build a Grok AI sector basket monitor for {TICKERS}.

Classify each company by AI exposure type: direct compute/infrastructure, cloud/platform,
software productivity, semiconductor supply chain, data/analytics, power/cooling, or
mostly narrative exposure.

Use Massive to compare fundamentals, ratios, price momentum, technical indicators, options
activity, analyst data, filings, and news. Use web and X tools to validate whether AI
narratives are tied to measurable business impact.

Grok must rank the basket by data-backed AI exposure, valuation risk, momentum, sentiment,
and near-term catalyst quality.
```

## Output Requirements

- Include a sector dashboard table with AI exposure type, valuation, growth, margin, momentum, options signal, and narrative signal.
- Include leaders, laggards, crowded names, and possible mispriced names.
- Include the top AI catalysts and top AI thesis risks.
- Cite Massive endpoints, fields, web sources, and X search windows.
- End with a watchlist ranked by priority.

## Quality Rules

- Do not equate AI mentions with AI revenue.
- Separate product claims from financial contribution.
- Flag names where valuation depends heavily on narrative.
- Normalize metrics across subsectors where possible.
- Do not present the output as financial advice.
