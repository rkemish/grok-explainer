# Ownership, Insider Activity, and Short Interest

Use this template to track who is buying and selling the stock across institutions, insiders, activists, and short sellers.

## Analysis Type

Ownership and positioning analysis.

## Goal

Detect smart-money accumulation, insider conviction, or crowded shorts before they show up clearly in the price.

## Input

Analyze `{TICKER}` using the Massive API.

## Prompt

```text
From the Massive API, retrieve for {TICKER}: top 20 institutional holders with QoQ position
changes, all Form 4 insider transactions in the last 12 months, short interest history and
days-to-cover, and any recent 13D/13G filings. Tell me whether smart money and insiders are
accumulating or distributing, and flag anything unusual (cluster buys, new activist, spike
in shorts).
```

## Output Requirements

- List the top 20 institutional holders and QoQ position changes.
- Include all Form 4 insider transactions from the last 12 months.
- Show short interest history and days-to-cover.
- Include recent 13D and 13G filings.
- Flag cluster buys, activist activity, and short-interest spikes.

## Source Discipline

- Cite every Massive endpoint and field used, including filing date, report period, holder, transaction, short-interest, short-volume, float, and timestamp fields.
- State unavailable fields explicitly instead of substituting assumptions.
- Do not present the output as financial advice.
