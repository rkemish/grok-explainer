# 8-K Material Event Triage

Use this template for rapidly triaging whether an 8-K filing changes the investment thesis.

## Metadata

- **Analysis type:** Material event triage
- **Goal:** Classify `{TICKER}` 8-K events by materiality, thesis impact, and follow-up needs.
- **Tools leveraged:** Massive REST API, `web_search`, `code_execution`

## Grok Orchestration

- **Grok:** Deliver the materiality verdict.
- **Harper:** Cross-check company release, news coverage, and market reaction.
- **Benjamin:** Pull 8-K text, EDGAR index, price bars, snapshot, and related news from Massive.
- **Lucas:** Audit item numbers, filing time, source freshness, and unsupported interpretation.

## Input

Triage recent 8-K filings for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Use Massive API filing and market data to triage recent 8-K events for {TICKER}.
Pull SEC EDGAR index, 8-K text, stock snapshots, historical bars around filing times,
and Massive news. Use web search for company releases or trusted coverage when needed.

Classify each event as thesis-changing, material but expected, operational update,
administrative, or unclear. Explain price reaction and next diligence steps.
```

## Output Requirements

- Include 8-K event table with date, item, summary, market reaction, materiality, and source.
- Include thesis impact and follow-up questions.
- Cite endpoints, fields, filing identifiers, and timestamps.
- End with urgent versus non-urgent actions.

## Quality Rules

- Do not treat every 8-K as material.
- Avoid long filing quotes.
- Separate filing facts from interpretation.
- Flag missing item text or delayed market data.
- Do not present the output as financial advice.
