# Multiples Dislocation

Use this template for finding valuation dislocations versus history, peers, and fundamentals.

## Metadata

- **Analysis type:** Relative valuation analysis
- **Goal:** Determine whether `{TICKER}` trades at a justified or unjustified multiple gap.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Decide whether the multiple spread is attractive, justified, or a trap.
- **Benjamin:** Pull Massive ratios, related tickers, fundamentals, historical prices, and peer data where available.
- **Lucas:** Audit peer selection, period consistency, and unavailable fields.

## Input

Analyze valuation dislocation for `{TICKER}` versus `{PEERS}`.

## Prompt

```text
Use Massive API data to analyze whether {TICKER} has a valuation dislocation versus
its own history and {PEERS}. Pull ratios, income statements, cash flows, balance sheets,
related tickers, ticker overview, and historical bars.

Compare P/E, EV/EBITDA, EV/FCF, P/S, P/B, FCF yield, ROIC, growth, leverage, and margin
profile. Explain whether the discount or premium is justified by quality, growth, risk,
or sentiment.
```

## Output Requirements

- Include historical multiple table and peer comparison table.
- Include premium/discount calculations.
- Include quality-adjusted interpretation.
- Cite Massive endpoints, fields, and peer selection method.

## Quality Rules

- Do not compare unlike business models without caveats.
- State when peer data is unavailable or incomplete.
- Separate cheap from low-quality.
- Use median and range, not only point estimates.
- Do not present the output as financial advice.
