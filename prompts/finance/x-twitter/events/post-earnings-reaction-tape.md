# Post-Earnings Reaction Tape

Use this template to capture what FinTwit said in the minutes and hours after the most recent earnings report.

## Metadata

- **Analysis type:** Event-driven sentiment analysis
- **Goal:** Understand how informed market participants reacted to the print, separate from sell-side noise.
- **Tools leveraged:** `x_keyword_search`, `x_thread_fetch`

## Prompt

```text
Reconstruct the X reaction to {TICKER}'s most recent earnings report.
Step 1: Identify the earnings date (the agent already knows this or can be told).
Step 2: x_keyword_search for $({TICKER}) earnings filter:has_engagement since:<earnings-date>
until:<earnings-date + 2d>. Pull top 50 posts by engagement.
Step 3: For the 10 most-engaged posts (likely thread starters), use x_thread_fetch to
retrieve the full conversation, including replies that pushed back.
Output: bullet summary of (a) the dominant bull take, (b) the dominant bear take,
(c) the most contrarian take that gained traction, and (d) any specific number,
guidance interpretation, or KPI that drove the conversation. Paraphrase - do not quote.
```

