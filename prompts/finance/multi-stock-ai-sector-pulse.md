# Multi-Stock AI Sector Pulse

Use this template to compare several AI-related stocks on momentum, news flow, and current market sentiment.

## Input

Real-time AI sector pulse on these stocks: {TICKER1}, {TICKER2}, {TICKER3}.

## Data Sources

### Massive

For each ticker, use Massive to pull:

- Current price
- Percentage change today
- Volume and relative volume if available
- 1-week, 1-month, and year-to-date performance
- Market cap and basic valuation context if available

### Web Search

Use `web_search` to find one to three recent AI-related headlines per stock, focusing on:

- Product launches
- Partnerships
- Earnings commentary
- Analyst upgrades or downgrades
- Infrastructure, chips, cloud, software, or automation catalysts

### X Search

Use X semantic search for the last 48 hours to summarize:

- Investor sentiment for each ticker
- Whether the AI narrative is accelerating, fading, or stable
- Notable viral posts, trader narratives, or breaking buzz

## Output Format

Present the comparison in this structure:

1. **Sector Pulse Summary:** One-paragraph overview of the group.
2. **Comparison Table:** Include ticker, current price, daily change, 1-week performance, top AI headline, and sentiment read.
3. **Momentum Ranking:** Rank the tickers from strongest to weakest based on price momentum, volume, AI news quality, and sentiment.
4. **Best Setup:** Identify the ticker with the strongest current momentum plus sentiment.
5. **Most Overhyped:** Identify any ticker where sentiment appears stronger than fundamentals or news.
6. **Key Watch Items:** List the main catalyst or risk to watch for each ticker.
7. **Final Takeaway:** Give a concise comparison-focused conclusion.

## Quality Rules

- Rank using evidence, not popularity alone.
- Distinguish price momentum from news quality and social sentiment.
- Call out conflicting signals, such as strong price action but weak news flow.
- Keep the analysis comparative and concise.
- Do not present the output as financial advice.
