# Viral Chart or Claim Fact-Check

Use this template for fact-checking viral market charts, screenshots, and financial claims on X.

## Metadata

- **Analysis type:** Viral claim verification
- **Goal:** Determine whether a viral chart or claim about `{TICKER_OR_MARKET}` is accurate, misleading, or false.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`, `x_thread_fetch`, `view_x_video`, Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Deliver the final fact-check and investor relevance.
- **Harper:** Find the original claim, spread pattern, and rebuttals.
- **Benjamin:** Pull Massive data needed to reproduce or refute the chart.
- **Lucas:** Audit methodology, time window, survivorship bias, and missing context.

## Input

Fact-check a viral chart or claim about `{TICKER_OR_MARKET}` from `{CLAIM_SOURCE_OR_LINK}`.

## Prompt

```text
Fact-check the viral X chart or claim about {TICKER_OR_MARKET}.
Use X tools to find the original post, reposted variants, rebuttals, and related threads.
If video or screenshot context matters, inspect it. Paraphrase the claim and identify the
implied investment conclusion.

Use Massive data to reproduce the relevant price, volume, fundamentals, options, filings,
macro, or cross-asset data. Decide whether the claim is accurate, misleading, unsupported,
or false.
```

## Output Requirements

- Include claim summary, data needed, reproduction check, verdict, and investor relevance.
- Include source credibility, spread pattern, and rebuttals.
- Include X windows, Massive endpoints, fields, formulas, and timestamps.
- End with corrected interpretation.

## Quality Rules

- Do not amplify false claims without context.
- Paraphrase posts and chart labels.
- Use time-bound X searches and state the exact search window.
- Check time window and denominator choices.
- Flag screenshots without source data.
- Do not present the output as financial advice.
