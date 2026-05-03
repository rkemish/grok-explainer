# Macro-Event Narrative Watch

Use this template for tracking how X interprets macro events and whether that interpretation matches market data.

## Metadata

- **Analysis type:** Macro narrative analysis
- **Goal:** Capture the crowd interpretation of `{MACRO_EVENT}` and compare it with Massive macro and market data.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`, Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Separate actual macro facts from narrative spin.
- **Harper:** Search X and web for the dominant interpretations.
- **Benjamin:** Pull Massive economy, indices, futures, FX, crypto, and stock data.
- **Lucas:** Audit release timing, data freshness, and unsupported causal claims.

## Input

Track the X narrative around `{MACRO_EVENT}` affecting `{MARKET_OR_TICKERS}`.

## Prompt

```text
Track the X narrative around {MACRO_EVENT} for {MARKET_OR_TICKERS}.
Use time-bounded x_keyword_search and x_semantic_search for the event name, surprise,
hot, cool, hawkish, dovish, recession, soft landing, inflation, rates, and affected tickers.

Cross-check narratives against Massive treasury yields, inflation, labor, indices, futures,
forex, crypto, snapshots, and price action. Identify what the data actually showed, what
X thinks it showed, and where the two diverge.
```

## Output Requirements

- Include actual macro fact table, X narrative table, and market reaction table.
- Include credibility ratings for accounts and claims.
- Include exact search windows, Massive endpoints, fields, and timestamps.
- End with narratives to monitor.

## Quality Rules

- Do not let partisan or ideological framing substitute for data.
- Paraphrase posts and avoid long quotes.
- Separate release facts from policy interpretation.
- Flag timing mismatches.
- Do not present the output as financial advice.
