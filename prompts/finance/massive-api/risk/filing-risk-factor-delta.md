# Filing Risk-Factor Delta

Use this template for comparing risk-factor disclosures over time and surfacing new or intensified risks.

## Metadata

- **Analysis type:** SEC filing risk analysis
- **Goal:** Detect risk-factor changes that may affect the thesis for `{TICKER}`.
- **Tools leveraged:** Massive REST API, `code_execution`

## Grok Orchestration

- **Grok:** Translate filing changes into investor-relevant risks.
- **Benjamin:** Pull risk factors, risk categories, 10-K sections, and EDGAR index data through Massive.
- **Lucas:** Audit filing dates, form types, taxonomy mapping, and comparison windows.

## Input

Analyze filing risk-factor deltas for `{TICKER}` between `{PRIOR_PERIOD}` and `{CURRENT_PERIOD}`.

## Prompt

```text
Use Massive API filing endpoints to compare risk-factor disclosures for {TICKER}.
Pull risk factors, risk categories, 10-K sections, and SEC EDGAR index data for the
current and prior relevant filings. Identify new risks, removed risks, intensified language,
softened language, and category-level concentration.

Summarize which changes matter to the investment thesis and which are boilerplate.
```

## Output Requirements

- Include filing comparison table with accession, filing date, form, section, and risk category.
- Include new, intensified, softened, and removed risk lists.
- Include thesis relevance and evidence confidence.
- Cite endpoints, fields, and filing identifiers.

## Quality Rules

- Do not overstate boilerplate changes.
- Do not quote long filing passages.
- Keep form and filing dates explicit.
- State if comparable prior filings are unavailable.
- Do not present the output as financial advice.
