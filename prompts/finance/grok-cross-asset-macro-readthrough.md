# Grok Cross-Asset Macro Readthrough

Use this template to connect rates, inflation, labor, FX, futures, crypto, and equity sector impact.

## Metadata

- **Analysis type:** Cross-asset macro readthrough
- **Goal:** Explain how macro data and cross-asset moves affect `{TICKERS}` or `{SECTOR}`.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`, `browse_page`, `x_keyword_search`, `x_semantic_search`

## Grok Orchestration

- **Grok:** Translate macro signals into sector and ticker implications.
- **Harper:** Gather macro headlines, policy commentary, and market narrative from web and X.
- **Benjamin:** Pull Massive economy, indices, futures, forex, crypto, rates, technicals, and stock data.
- **Lucas:** Audit timing, market session status, and whether macro links are evidence-backed.

## Input

Analyze the macro readthrough from `{MACRO_EVENT}` to `{SECTOR_OR_TICKERS}` over `{WINDOW}`.

## Prompt

```text
Run a Grok cross-asset macro readthrough for {MACRO_EVENT} and {SECTOR_OR_TICKERS}.

Use Massive economy endpoints for treasury yields, inflation, inflation expectations, and
labor market indicators where relevant. Add indices, futures, forex, crypto, sector proxies,
stock snapshots, historical bars, and technical indicators. Use web and X tools to capture
policy narrative and market interpretation.

Grok must separate the actual macro data, the cross-asset market response, and the inferred
readthrough to each sector or ticker.
```

## Output Requirements

- Include macro fact table, cross-asset reaction table, sector/ticker impact table, and narrative summary.
- Identify winners, losers, ambiguous beneficiaries, and crowded interpretations.
- Include data timestamps and market session context.
- Cite Massive endpoints, fields, web sources, and X windows.
- End with follow-up data releases and invalidation signals.

## Quality Rules

- Do not claim macro causality without timing and price evidence.
- Separate realized data from expectations and policy interpretation.
- Flag missing futures, FX, or economy coverage.
- Keep second-order effects clearly labeled as inference.
- Do not present the output as financial advice.
