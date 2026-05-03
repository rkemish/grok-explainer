# Revenue Quality and Accruals

Use this template for testing whether reported growth is supported by cash conversion, working capital, and recurring business quality.

## Metadata

- **Analysis type:** Fundamental quality review
- **Goal:** Identify whether `{TICKER}` revenue and earnings quality are improving, deteriorating, or masking risk.
- **Tools leveraged:** `code_execution`, Massive REST API, `chatroom_send`

## Grok Orchestration

- **Grok:** Synthesize the quality verdict and explain what matters for investors.
- **Benjamin:** Pull income statements, cash flow statements, balance sheets, ratios, and historical bars through Massive.
- **Lucas:** Verify endpoint coverage, field definitions, periods, and missing data.

## Input

Analyze revenue quality and accruals for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Use Massive API data to evaluate revenue quality and accrual risk for {TICKER}.
Pull quarterly and annual income statements, cash flow statements, balance sheets, and
ratios. Compute revenue growth, operating income growth, net income growth, CFO growth,
FCF growth, receivables growth, inventory growth, deferred revenue if available, accruals
as a percentage of assets, and CFO/net income conversion.

Flag periods where accounting earnings grew faster than cash flow or where working capital
absorbed unusually large cash. Cite every endpoint and field used.
```

## Output Requirements

- Include quarterly and annual quality tables.
- Include accrual, cash conversion, and working-capital red flags.
- End with a verdict: clean, watch, deteriorating, or data insufficient.
- Cite Massive endpoints, fields, periods, and pull timestamp.

## Quality Rules

- Do not assume unavailable fields.
- State when restatements, filing lags, or missing periods affect confidence.
- Separate accounting signal from stock-price interpretation.
- Use consistent fiscal periods.
- Do not present the output as financial advice.
