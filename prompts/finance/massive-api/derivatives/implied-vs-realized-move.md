# Implied Versus Realized Move

Use this template for comparing options-implied moves with historical and realized volatility.

## Metadata

- **Analysis type:** Event volatility comparison
- **Goal:** Determine whether `{TICKER}` options are pricing a rich, fair, or cheap expected move.
- **Tools leveraged:** `code_execution`, Massive REST API

## Grok Orchestration

- **Grok:** Summarize whether implied move looks rich, fair, or cheap.
- **Benjamin:** Pull options snapshots, contracts, quotes, historical stock bars, technical indicators, and prior event moves.
- **Lucas:** Audit event dates, calculations, and stale option quotes.

## Input

Compare implied versus realized move for `{TICKER}` around `{EVENT_OR_WINDOW}`.

## Prompt

```text
Use Massive API data to compare implied and realized moves for {TICKER}.
Pull the option chain snapshot, relevant contract snapshots, option quotes, stock snapshot,
historical bars, and technical indicators. Estimate current implied move from the nearest
liquid straddle or available IV fields. Compare with 1D, 5D, 20D, and prior event realized
moves.

Classify whether options price a rich, fair, or cheap move and show uncertainty.
```

## Output Requirements

- Include implied move calculation and contract selection.
- Include realized volatility and prior-event move table.
- Include liquidity and data-quality caveats.
- Cite endpoints, fields, dates, and formulas.

## Quality Rules

- Do not use illiquid options without caveats.
- State whether implied move is approximate.
- Do not turn volatility richness into a directional call.
- Keep event windows explicit.
- Do not present the output as financial advice.
