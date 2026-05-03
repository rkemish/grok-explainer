# Shareholder Yield and Payout Durability

Use this template for testing whether dividends and buybacks are sustainable.

## Metadata

- **Analysis type:** Shareholder return analysis
- **Goal:** Evaluate dividend, buyback, leverage, and cash-flow durability for `{TICKER}`.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Explain the payout quality and risk.
- **Benjamin:** Pull dividends, splits, cash flows, balance sheets, ratios, shares, and price history.
- **Lucas:** Audit payout calculations and missing buyback data.

## Input

Analyze shareholder yield and payout durability for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Use Massive API data to evaluate shareholder yield for {TICKER}.
Pull dividends, splits, ticker overview, cash flow statements, balance sheets, income
statements, ratios, and historical bars. Compute dividend yield, dividend growth, payout
ratio, FCF payout ratio, net debt trend, share-count change, buyback yield proxy, and
total shareholder yield where fields support it.

Assess whether payouts are covered by durable cash flow or funded by leverage or shrinking
investment.
```

## Output Requirements

- Include tables for dividends, coverage, share count, debt, and cash flow.
- Include payout durability rating: strong, adequate, stretched, unsafe, or data insufficient.
- Cite endpoints, fields, and formula assumptions.
- End with red flags to monitor.

## Quality Rules

- Do not infer buybacks only from EPS growth.
- Flag special dividends and split-adjustment issues.
- Distinguish dividend yield from total shareholder yield.
- State missing fields explicitly.
- Do not present the output as financial advice.
