# 10-K Moat Language

Use this template for extracting competitive advantage claims and risk language from 10-K sections.

## Metadata

- **Analysis type:** Filing-based competitive analysis
- **Goal:** Identify whether `{TICKER}` claims durable advantage, dependency, or commoditization risk.
- **Tools leveraged:** Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Translate filing language into moat assessment.
- **Harper:** Cross-check claims with recent news and company materials.
- **Benjamin:** Pull 10-K sections, risk factors, risk categories, related tickers, and fundamentals.
- **Lucas:** Audit filing dates, section coverage, and unsupported inference.

## Input

Analyze 10-K moat language for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Use Massive API filing endpoints to analyze moat language for {TICKER}.
Pull 10-K Business and Risk Factors sections, standardized risk factors, risk categories,
related tickers, and fundamentals. Extract themes around competitive advantage, customer
dependency, supplier dependency, pricing power, IP, regulation, cyclicality, and substitute
risk.

Compare current language with prior filings where available and identify material changes.
```

## Output Requirements

- Include moat claim table and risk language table.
- Include changed language versus prior filing.
- Include thesis relevance and evidence confidence.
- Cite endpoints, fields, accession numbers, and filing dates.

## Quality Rules

- Do not quote long filing passages.
- Separate company claims from verified evidence.
- Flag boilerplate and legal language.
- State if prior filings are unavailable.
- Do not present the output as financial advice.
