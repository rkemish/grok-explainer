# Quick Real-Time AI Stock Snapshot

Use this template for fast investor checks on AI-related stocks.

## Input

Give me a real-time investor briefing on {TICKER} as an AI-related stock.

## Data Sources

### Polygon

Use Polygon for:

- Current price, today’s change, volume, market cap
- Key financial metrics (trailing PE, forward PE, revenue growth)
- Latest options chain highlights (especially near-term calls/puts)

### Web Search

Use `web_search` for the three most recent major news articles about `{TICKER}` and AI developments.

### X Search

Use X search, both keyword and semantic, to gauge:

- Current market sentiment
- Hype level
- Breaking buzz from the last 24-48 hours

## Output Format

Summarize everything in a clear, actionable investor briefing:

- **Snapshot:** Price, daily move, volume, and market cap
- **Fundamentals:** Valuation, growth, and financial context
- **Options Activity:** Notable near-term calls, puts, implied volatility, and unusual activity
- **AI News:** Three most recent major AI-related news items with dates and sources
- **Market Sentiment:** Bullish, bearish, or mixed sentiment from X and news flow
- **Investor Takeaway:** Concise risk/reward view and what to watch next

> Keep the tone concise, factual, and actionable. Distinguish confirmed data from sentiment or speculation.
