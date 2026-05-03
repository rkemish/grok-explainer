# Grok Catalyst to Trade Plan

Use this template to convert a catalyst into bull, base, and bear scenarios with invalidation signals and position-risk framing.

## Metadata

- **Analysis type:** Catalyst-driven trade planning
- **Goal:** Translate `{CATALYST}` for `{TICKER}` into actionable scenario analysis without overstating certainty.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`, `x_keyword_search`, `x_semantic_search`, `chatroom_send`

## Grok Orchestration

- **Grok:** Build the final scenario framework and risk controls.
- **Harper:** Gather catalyst context, comparable past events, news, and X expectations.
- **Benjamin:** Pull Massive price history, options implied move, realized volatility, analyst data, corporate events, and fundamentals.
- **Lucas:** Audit whether each scenario uses measurable confirmation or invalidation signals.

## Input

Build a catalyst-to-trade plan for `{TICKER}` around `{CATALYST}` over `{HORIZON}`.

## Prompt

```text
Convert {CATALYST} for {TICKER} into a Grok catalyst-to-trade plan.

Use Massive to measure historical reaction to similar events where possible, current price
trend, realized volatility, options-implied move, skew, liquidity, analyst expectations,
corporate events, and relevant fundamentals. Use web and X tools to measure market
expectations and narrative crowding.

Create bull, base, and bear scenarios with explicit triggers, price or valuation logic,
probability weighting, downside controls, and data points that would invalidate each case.
```

## Output Requirements

- Include catalyst summary, market expectation, scenario table, options read, sentiment read, and risk controls.
- Include expected move versus historical move where Massive data supports it.
- Include "do nothing" conditions when evidence is weak.
- Cite endpoints, fields, web sources, and X search windows.
- End with monitoring checklist and invalidation triggers.

## Quality Rules

- Do not convert every catalyst into a trade.
- State when the setup is too crowded, illiquid, or unsupported.
- Separate probability-weighted analysis from prediction.
- Do not quote X posts verbatim.
- Do not present the output as financial advice.
