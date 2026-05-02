# Investment Thesis Synthesis with Scenarios

Use this template to combine research into a bull, base, and bear scenario model with target prices, probabilities, and tracking signals.

## Analysis Type

Scenario analysis and investment thesis synthesis.

## Goal

Produce a portfolio-ready recommendation with a clear expected return and pre-defined signals to monitor.

## Input

Analyze `{TICKER}` using the Massive API.

## Prompt

```text
Using only data retrievable from the Massive API, build a bull / base / bear case for
{TICKER} over a 12-month horizon. For each case, specify: revenue and margin assumptions,
exit multiple, target price, probability weighting, and the 2-3 API-trackable signals that
would confirm or invalidate the case (e.g., specific KPI thresholds, guidance revisions,
ownership shifts). Finish with a probability-weighted expected return and a recommendation
sized for a portfolio context. Show every endpoint and field you used.
```

## Output Requirements

- Use only data retrievable from the Massive API.
- Build bull, base, and bear cases over a 12-month horizon.
- Include revenue assumptions, margin assumptions, exit multiple, target price, and probability for each case.
- Define two to three API-trackable confirmation or invalidation signals for each case.
- Finish with probability-weighted expected return.
- Include a portfolio-sizing recommendation.
- Show every endpoint and field used.
