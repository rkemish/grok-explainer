# Price Action and Risk Profile

Use this template to profile the stock's volatility, beta, drawdowns, and macro sensitivities from historical price data.

## Analysis Type

Quantitative risk and technical analysis.

## Goal

Understand how the stock actually behaves so it can be sized correctly in a portfolio.

## Input

Analyze `{TICKER}` using the Massive API.

## Prompt

```text
Use the Massive API to pull daily OHLCV for {TICKER} for the last 5 years. Compute: realized
volatility (30/90/365d), beta vs. SPY and vs. sector ETF, max drawdown and recovery time,
correlation to top 5 macro factors the API exposes (rates, USD, oil, etc.), and current
position relative to 50/200-day moving averages. Output a one-paragraph risk character sketch.
```

## Output Requirements

- Use five years of daily OHLCV data.
- Compute realized volatility for 30, 90, and 365 days.
- Compute beta versus SPY and the relevant sector ETF.
- Include maximum drawdown and recovery time.
- Show correlation to the top five exposed macro factors.
- End with a one-paragraph risk profile.
