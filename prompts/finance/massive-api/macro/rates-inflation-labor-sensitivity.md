# Rates Inflation Labor Sensitivity

Use this template for measuring how rates, inflation, and labor data may affect a company or sector.

## Metadata

- **Analysis type:** Macro sensitivity analysis
- **Goal:** Connect Massive economy data to `{TICKER}` or `{SECTOR}` exposure.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Translate macro data into thesis implications.
- **Harper:** Gather policy commentary and trusted macro context.
- **Benjamin:** Pull treasury yields, inflation, inflation expectations, labor data, stock/index bars, and technicals.
- **Lucas:** Audit release dates, time alignment, and inferred relationships.

## Input

Analyze rates, inflation, and labor sensitivity for `{TICKER_OR_SECTOR}` over `{WINDOW}`.

## Prompt

```text
Use Massive economy and market data to analyze macro sensitivity for {TICKER_OR_SECTOR}.
Pull treasury yields, inflation, inflation expectations, labor market data, stock or sector
proxy bars, indices, futures if relevant, and technical indicators.

Compare asset returns and volatility around major macro releases and explain whether the
company or sector appears rate-sensitive, inflation-sensitive, labor-sensitive, or unclear.
```

## Output Requirements

- Include macro data table and asset reaction table.
- Include sensitivity classification and evidence confidence.
- Include endpoint, field, release date, and timestamp citations.
- End with upcoming macro watch items.

## Quality Rules

- Do not claim causality without timing evidence.
- Separate macro data from market interpretation.
- Flag missing release timestamps.
- State when sensitivity is ambiguous.
- Do not present the output as financial advice.
