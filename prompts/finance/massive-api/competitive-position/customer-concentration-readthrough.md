# Customer Concentration Readthrough

Use this template for mapping customer, supplier, and end-market dependencies from filings, news, and peer data.

## Metadata

- **Analysis type:** Customer and supply-chain readthrough
- **Goal:** Identify whether `{TICKER}` has customer concentration or supply-chain exposure that affects the thesis.
- **Tools leveraged:** Massive REST API, `web_search`, `code_execution`

## Grok Orchestration

- **Grok:** Synthesize dependency risk and competitive implications.
- **Harper:** Search web sources for customer, supplier, and end-market developments.
- **Benjamin:** Pull 10-K sections, risk factors, related tickers, news, fundamentals, and price data.
- **Lucas:** Audit whether relationships are disclosed, inferred, or rumored.

## Input

Analyze customer concentration and supply-chain readthrough for `{TICKER}`.

## Prompt

```text
Use Massive API filings, news, and market data to analyze customer concentration and
supply-chain readthrough for {TICKER}. Pull 10-K sections, risk factors, related tickers,
Massive news, fundamentals, and historical bars. Use web search only to cross-check
named customer, supplier, and end-market claims.

Classify each relationship as disclosed, likely but not disclosed, rumored, or unsupported.
```

## Output Requirements

- Include relationship map table with source, evidence type, dependency risk, and thesis impact.
- Include peer and end-market readthrough.
- Include endpoint, field, filing, and web-source citations.
- End with follow-up diligence questions.

## Quality Rules

- Do not present inferred relationships as disclosed facts.
- Separate customer concentration from customer quality.
- Flag stale filing language.
- Avoid unsupported supply-chain speculation.
- Do not present the output as financial advice.
