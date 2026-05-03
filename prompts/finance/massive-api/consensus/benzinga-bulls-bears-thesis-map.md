# Benzinga Bulls Bears Thesis Map

Use this template for mapping structured analyst bull and bear arguments.

## Metadata

- **Analysis type:** Analyst thesis mapping
- **Goal:** Extract and compare the strongest structured bull and bear arguments for `{TICKER}`.
- **Tools leveraged:** Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Synthesize the consensus debate and identify what evidence would settle it.
- **Harper:** Cross-check high-impact analyst claims with recent web sources.
- **Benjamin:** Pull Benzinga bulls/bears, analyst ratings, consensus, news, and fundamentals.
- **Lucas:** Audit whether arguments are sourced or only analyst opinion.

## Input

Build a Benzinga bulls/bears thesis map for `{TICKER}`.

## Prompt

```text
Use Massive API Benzinga partner data to build a bull/bear thesis map for {TICKER}.
Pull bulls-bears-say, analyst ratings, analyst insights, consensus ratings, news, earnings,
guidance, ratios, and fundamentals. Group the analyst arguments by theme: growth, margins,
valuation, balance sheet, competitive position, capital allocation, catalysts, and risk.

For each theme, connect the analyst claim to Massive data that supports, weakens, or
does not address the claim.
```

## Output Requirements

- Include bull thesis table, bear thesis table, and evidence-quality column.
- Include claims supported by Massive data, claims contradicted by data, and claims not testable.
- Cite endpoints, fields, analysts/firms where available, and timestamp.
- End with open questions for further research.

## Quality Rules

- Do not present analyst claims as facts.
- Flag missing partner data.
- Avoid quoting long analyst text.
- Separate evidence-backed arguments from opinion.
- Do not present the output as financial advice.
