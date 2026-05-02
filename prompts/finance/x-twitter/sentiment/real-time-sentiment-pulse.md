# Real-Time Sentiment Pulse

Use this template to build a current-state sentiment snapshot for a company across X.

## Metadata

- **Analysis type:** Sentiment analysis - cross-sectional snapshot
- **Goal:** Establish a baseline of crowd sentiment before going deeper, and detect divergence between price action and narrative.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`

## Prompt

```text
Build a real-time sentiment pulse for {TICKER} on X.
Step 1: Use x_keyword_search with the cashtag $({TICKER}) and filter:has_engagement,
restricted to the last 7 days (since: today minus 7d). Pull the top 100 posts by engagement.
Step 2: Use x_semantic_search with queries like "{TICKER} bullish thesis", "{TICKER} bearish",
"{TICKER} disappointed", "{TICKER} bought more" to capture posts that don't use the cashtag.
Classify every post as bullish / bearish / neutral and tally volume per bucket.
Output: a table with sentiment %, total post volume, top 5 bullish takes (paraphrased,
no quotes), top 5 bearish takes (paraphrased), and any apparent divergence from the
stock's recent price move.
```

