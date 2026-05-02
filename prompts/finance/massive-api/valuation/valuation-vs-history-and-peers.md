# Valuation vs. History and Peers

Use this template to compare today's valuation multiples to the company's own history and to its closest competitors.

## Analysis Type

Relative valuation - multiples-based analysis.

## Goal

Determine whether the stock looks cheap, fair, or expensive in context rather than in isolation.

## Input

Analyze `{TICKER}` using the Massive API.

## Prompt

```text
Using the Massive API, compute current and 5-year-average P/E, EV/EBITDA, EV/Sales, P/B,
and FCF yield for {TICKER}. Then pull the same metrics for its 5 closest peers (resolve peers
via the API's classification/sector endpoint, not memory). Present a percentile-rank table
showing where {TICKER} sits today vs. its own history and vs. peers. Call out any multiple
that is >1 standard deviation from norm.
```

## Output Requirements

- Resolve peers through Massive API classification or sector data.
- Compare current valuation against 5-year averages.
- Include peer percentile ranks.
- Flag multiples more than one standard deviation from normal.
- Cite endpoint and field names used for peer selection and valuation metrics.
