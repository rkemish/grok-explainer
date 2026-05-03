# Merchant Spending Readthrough

Use this template for using alternative consumer-spending data to infer demand trends where Massive coverage supports it.

## Metadata

- **Analysis type:** Alternative data readthrough
- **Goal:** Connect merchant spending trends to `{TICKER}`, `{MERCHANT}`, or `{SECTOR}`.
- **Tools leveraged:** Massive REST API, `web_search`, `code_execution`

## Grok Orchestration

- **Grok:** Translate spending signal into a cautious thesis readthrough.
- **Harper:** Cross-check merchant relationships, public disclosures, and sector context.
- **Benjamin:** Pull merchant aggregates, merchant hierarchy, stock fundamentals, news, and price data.
- **Lucas:** Audit mapping quality, geography, coverage, and partner-data caveats.

## Input

Analyze merchant spending readthrough for `{TICKER_OR_MERCHANT}` over `{WINDOW}`.

## Prompt

```text
Use Massive alternative data endpoints to analyze merchant spending readthrough for
{TICKER_OR_MERCHANT}. Pull merchant hierarchy, merchant aggregates, stock fundamentals,
news, snapshots, and historical bars where relevant. Use web search to verify merchant
to public-company mappings.

Assess whether spending trends support, contradict, or do not meaningfully inform the
investment thesis.
```

## Output Requirements

- Include merchant mapping table and spending trend table.
- Include geography, coverage, and data-lag caveats.
- Cite endpoints, fields, dates, web sources, and mapping evidence.
- End with confidence level and next checks.

## Quality Rules

- Do not overgeneralize European panel data to global company revenue.
- State mapping uncertainty clearly.
- Separate spending signal from margin or profit signal.
- Flag partner-data access gaps.
- Do not present the output as financial advice.
