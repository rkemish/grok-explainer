# Supply Chain, Customers, and Competitive Position

Use this template to map the company's business relationships and cross-check them against disclosed risks.

## Analysis Type

Qualitative and competitive moat analysis.

## Goal

Assess durability of the business: how concentrated, how defensible, and how exposed it is.

## Input

Analyze `{TICKER}` using the Massive API.

## Prompt

```text
Using the Massive API's relationship/graph data for {TICKER}, map: top disclosed customers
and suppliers (with revenue concentration if available), direct competitors, and any
recently disclosed partnership or contract changes. Cross-reference with the last 10-K/10-Q
risk factors via the filings endpoint. Conclude with the 3 biggest structural risks and
3 biggest moats you can defend with API-sourced evidence.
```

## Output Requirements

- Map disclosed customers and suppliers.
- Include revenue concentration when available.
- Identify direct competitors using API-sourced relationship or classification data.
- Include recent partnership or contract changes.
- Cross-reference claims against the latest 10-K or 10-Q risk factors.
- End with three structural risks and three defensible moats.

## Source Discipline

- Cite every Massive endpoint and field used, including filing section, risk factor, news, related ticker, timestamp, and data freshness fields.
- State unavailable fields explicitly instead of substituting assumptions.
- Do not present the output as financial advice.
