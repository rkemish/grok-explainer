# Massive News Sentiment Validator

Use this template for validating whether news sentiment aligns with price action, fundamentals, and social narratives.

## Metadata

- **Analysis type:** News sentiment validation
- **Goal:** Determine whether Massive news sentiment for `{TICKER}` is actionable, noisy, or contradicted by other data.
- **Tools leveraged:** Massive REST API, `web_search`, `x_keyword_search`, `x_semantic_search`

## Grok Orchestration

- **Grok:** Synthesize news, market reaction, and narrative evidence.
- **Harper:** Cross-check headlines with web and X.
- **Benjamin:** Pull Massive news, snapshots, historical bars, fundamentals, and analyst data.
- **Lucas:** Audit sentiment fields, publication times, and source quality.

## Input

Validate news sentiment for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Use Massive API news and market data to validate news sentiment for {TICKER}.
Pull Massive stock news with sentiment, Benzinga news if available, stock snapshot,
historical bars, analyst ratings, earnings, guidance, and relevant fundamentals. Use web
and X tools to check whether the same narrative is confirmed or distorted.

Compare sentiment labels, headline substance, price reaction, volume, and source credibility.
```

## Output Requirements

- Include news table with timestamp, source, sentiment, topic, price reaction, and credibility.
- Include sentiment versus price divergence.
- Include confirmed, disputed, and unverified claims.
- Cite endpoints, fields, web sources, and X search windows.

## Quality Rules

- Do not rely on sentiment labels without reading substance.
- Do not reproduce articles or posts verbatim.
- Separate market-moving news from low-signal reposts.
- Flag stale or duplicated news.
- Do not present the output as financial advice.
