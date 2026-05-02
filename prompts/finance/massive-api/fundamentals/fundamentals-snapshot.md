# Fundamentals Snapshot

Use this template to pull a company's core financial statements and turn them into a clean, comparable table with growth rates and red flags.

## Analysis Type

Fundamental analysis - financial statement review.

## Goal

Quickly understand whether the underlying business is growing, profitable, and financially healthy before going deeper.

## Input

Analyze `{TICKER}` using the Massive API.

## Prompt

```text
Pull the latest 8 quarters and 5 years of fundamentals for {TICKER} via the Massive API.
Build a table covering revenue, gross margin, operating margin, FCF, net debt, ROIC, and
shares outstanding. Compute YoY and QoQ growth, flag any inflection points (>20% deltas),
and end with a 5-bullet "what the numbers actually say" summary. Cite the API endpoints used.
```

## Output Requirements

- Include quarterly and annual financial tables.
- Show YoY and QoQ growth where applicable.
- Flag inflection points greater than 20%.
- End with exactly five plain-English takeaways.
- Cite the Massive API endpoints used.
