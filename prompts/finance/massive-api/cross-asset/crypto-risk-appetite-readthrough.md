# Crypto Risk-Appetite Readthrough

Use this template for using crypto market behavior as a risk-appetite signal for equities or sectors.

## Metadata

- **Analysis type:** Cross-asset risk appetite
- **Goal:** Determine whether crypto price action supports or contradicts risk-on narratives for `{TICKERS_OR_SECTOR}`.
- **Tools leveraged:** `code_execution`, Massive REST API, `x_keyword_search`, `x_semantic_search`

## Grok Orchestration

- **Grok:** Explain cross-asset readthrough and confidence.
- **Harper:** Check X narratives connecting crypto, liquidity, AI, and growth stocks.
- **Benjamin:** Pull crypto snapshots, crypto bars, stock/index bars, technicals, and market movers.
- **Lucas:** Audit correlation windows and avoid unsupported causality.

## Input

Analyze crypto risk-appetite readthrough for `{TICKERS_OR_SECTOR}` over `{WINDOW}`.

## Prompt

```text
Use Massive API crypto and equity data to analyze whether crypto markets are signaling
risk appetite for {TICKERS_OR_SECTOR}. Pull crypto snapshots, crypto aggregates, crypto
top movers, equity snapshots, stock/index bars, technical indicators, and relevant news.
Use X tools to capture current cross-asset narratives.

Compare crypto leadership, volatility, correlation, and timing versus equity price action.
```

## Output Requirements

- Include crypto dashboard and equity readthrough table.
- Include correlation or co-movement analysis where data supports it.
- Include narrative confirmation or contradiction from X.
- Cite endpoints, fields, timestamps, and X search windows.

## Quality Rules

- Do not imply crypto causes equity moves without evidence.
- State when correlation is unstable.
- Separate liquidity narrative from measured data.
- Flag unsupported social claims.
- Do not present the output as financial advice.
