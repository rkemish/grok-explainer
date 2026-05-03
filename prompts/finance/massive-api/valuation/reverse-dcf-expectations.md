# Reverse DCF Expectations

Use this template for backing into the growth and margin expectations implied by the current market price.

## Metadata

- **Analysis type:** Reverse valuation analysis
- **Goal:** Estimate what `{TICKER}` must deliver to justify its current valuation.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Summarize whether implied expectations are reasonable or stretched.
- **Benjamin:** Pull Massive price, market cap, enterprise value inputs where available, fundamentals, ratios, and historical growth.
- **Lucas:** Audit assumptions, missing fields, and sensitivity logic.

## Input

Build a reverse DCF expectations check for `{TICKER}` over `{HORIZON}`.

## Prompt

```text
Use Massive API data to build a reverse DCF-style expectations check for {TICKER}.
Pull current snapshot, ticker overview, income statements, cash flow statements, balance
sheets, ratios, and historical bars. Estimate normalized revenue, FCF margin, net cash
or debt, share count, and recent growth.

Back into the revenue growth, margin, and terminal multiple assumptions needed to justify
the current price. Run conservative, base, and aggressive cases and show the sensitivity.
```

## Output Requirements

- Include current valuation inputs and source fields.
- Include a sensitivity table for growth, margin, discount rate, and terminal multiple.
- Include implied expectations versus historical delivery.
- Cite endpoints, fields, formulas, and data timestamp.

## Quality Rules

- Label all model assumptions clearly.
- Do not treat reverse DCF output as intrinsic value certainty.
- Use Massive data where possible and state manual assumptions.
- Flag missing enterprise value or share-count inputs.
- Do not present the output as financial advice.
