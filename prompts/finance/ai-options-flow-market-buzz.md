# AI Stock Options Flow + Market Buzz

Use this template for trader-focused checks on options activity, short-term sentiment, and AI-related market buzz.

## Input

Real-time options and sentiment report for the AI stock {TICKER}.

## Data Sources

### Massive

Use Massive to pull:

- Current stock price, daily change, volume, and implied volatility
- Top 5 most active options contracts today by volume and open interest
- Notable near-term calls and puts, including strike, expiration, volume, open interest, and bid/ask spread
- Any unusual options activity, especially volume far above open interest or clustered buying at specific strikes

### Web Search

Use `web_search` for recent articles mentioning:

- `{TICKER}` AI strategy
- Upcoming catalysts
- Earnings, product launches, analyst notes, or partnership news
- Macro or sector headlines affecting AI stocks

### X Search

Use X search, both keyword and semantic, for posts from the last 24 hours about:

- `{TICKER}` options flow
- Unusual activity
- AI hype or skepticism
- Trader and analyst commentary

## Output Format

Present the report in this structure:

1. **Trader Snapshot:** Current price, daily move, volume, implied volatility, and short-term setup.
2. **Top Options Contracts:** Table of the top 5 contracts with expiration, strike, type, volume, open interest, and interpretation.
3. **Unusual Flow:** Highlight suspicious or meaningful call/put activity and explain why it matters.
4. **Catalyst Check:** Summarize recent AI-related news or upcoming events that could explain the flow.
5. **X Sentiment:** Summarize current trader buzz as bullish, bearish, or mixed.
6. **Verdict:** Give a short bullish, neutral, or bearish read on whether options flow and sentiment agree.

## Quality Rules

- Do not treat high options volume as bullish unless the call/put direction and context support it.
- Separate confirmed options data from social-media speculation.
- Mention liquidity concerns if bid/ask spreads are wide or open interest is thin.
- Keep the tone practical for a short-term trader, not a long-term investor.
- Do not present the output as financial advice.
