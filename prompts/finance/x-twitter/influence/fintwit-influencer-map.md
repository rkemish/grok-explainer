# FinTwit Influencer Map

Use this template to identify high-signal accounts currently discussing a stock.

## Metadata

- **Analysis type:** Information-source mapping / influencer analysis
- **Goal:** Build a watchlist of accounts whose posts on this name are worth tracking continuously.
- **Tools leveraged:** `x_user_search`, `x_keyword_search`, `x_thread_fetch`

## Prompt

```text
Build a FinTwit influencer map for {TICKER}.
Step 1: x_keyword_search $({TICKER}) filter:has_engagement over the last 30 days.
Step 2: Aggregate authors and rank by combined engagement (likes + reposts + replies)
on their {TICKER} posts. Take the top 25.
Step 3: x_user_search each top author to get bio, follower count, and self-description
(buy-side / sell-side / retail / journalist / company employee).
Step 4: x_thread_fetch their most-engaged {TICKER} post to see the substance and the
quality of pushback.
Output: a ranked table of accounts with handle, follower count, role/affiliation,
their current stance on {TICKER} (bull/bear/neutral), and a 1-sentence note on the
quality of their analysis. Flag accounts worth adding to a permanent monitor list.
```

## Source Discipline

- Use time-bound X searches and state the exact search window.
- Paraphrase posts and threads; do not quote them verbatim.
- Attribute claims by source type and include credibility context.
- Do not present the output as financial advice.
