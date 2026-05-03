# Capital Allocation and ROIC

Use this template for assessing whether management reinvests capital at attractive returns.

## Metadata

- **Analysis type:** Capital allocation analysis
- **Goal:** Evaluate ROIC, buybacks, dividends, leverage, capex, and reinvestment discipline for `{TICKER}`.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Convert the numbers into a capital allocation verdict.
- **Benjamin:** Pull fundamentals, ratios, dividends, splits, shares outstanding, and price history.
- **Lucas:** Verify formulas, endpoint coverage, and unavailable data.

## Input

Analyze capital allocation and ROIC for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Use Massive API data to evaluate capital allocation for {TICKER}.
Pull income statements, balance sheets, cash flow statements, ratios, dividends, splits,
and ticker overview. Compute ROIC, ROE, ROA, FCF after dividends, capex intensity,
net debt trend, share-count change, dividend growth, payout ratio, and buyback yield
where fields support it.

Assess whether capital allocation creates value, preserves value, destroys value, or
cannot be judged from available data. Cite every endpoint and field used.
```

## Output Requirements

- Include tables for returns, cash deployment, balance sheet, and shareholder returns.
- Include a capital allocation scorecard.
- Include data gaps and formula assumptions.
- End with management actions to monitor.

## Quality Rules

- Do not infer buybacks without share-count or cash-flow evidence.
- Do not mix annual and quarterly periods without labeling them.
- Flag one-time balance-sheet distortions.
- Cite endpoints and fields.
- Do not present the output as financial advice.
