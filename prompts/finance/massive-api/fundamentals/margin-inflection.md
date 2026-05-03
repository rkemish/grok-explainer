# Margin Inflection

Use this template for detecting gross, operating, net, and free-cash-flow margin inflections.

## Metadata

- **Analysis type:** Margin trend analysis
- **Goal:** Determine whether `{TICKER}` is gaining or losing operating leverage.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Explain the margin inflection and portfolio relevance.
- **Benjamin:** Pull statements and ratios, compute trends, and identify inflection periods.
- **Lucas:** Audit period alignment and field availability.

## Input

Analyze margin inflection for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Using Massive API fundamentals, evaluate margin inflection for {TICKER}.
Pull income statements, cash flow statements, balance sheets, and ratios for the latest
8 quarters and 5 fiscal years. Compute gross margin, operating margin, net margin, FCF
margin, operating leverage, revenue growth, expense growth, and sequential change.

Identify where margins improved or deteriorated by more than 200 bps and explain whether
the move appears structural, cyclical, one-time, or data insufficient.
```

## Output Requirements

- Include a margin trend table and inflection table.
- Include likely drivers and evidence quality.
- Include endpoint and field citations.
- End with the top 5 margin watch items.

## Quality Rules

- Do not call a one-quarter move structural without supporting history.
- Flag unavailable margin components.
- Separate reported margin from adjusted claims unless sourced.
- Use fiscal dates, not vague period labels.
- Do not present the output as financial advice.
