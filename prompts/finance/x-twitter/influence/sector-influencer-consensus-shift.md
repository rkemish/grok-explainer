# Sector Influencer Consensus Shift

Use this template for tracking whether influential accounts in a sector are changing consensus narrative.

## Metadata

- **Analysis type:** Influencer narrative shift
- **Goal:** Detect when high-signal sector accounts become more bullish, bearish, or divided on `{SECTOR_OR_TICKERS}`.
- **Tools leveraged:** `x_user_search`, `x_keyword_search`, `x_semantic_search`, `x_thread_fetch`, Massive REST API

## Grok Orchestration

- **Grok:** Synthesize whether influencer consensus is changing and whether the change matters.
- **Harper:** Identify sector accounts, posts, threads, and narrative changes.
- **Benjamin:** Cross-check with Massive price action, fundamentals, news, and analyst data.
- **Lucas:** Audit account credibility, engagement bias, and search coverage.

## Input

Track sector influencer consensus for `{SECTOR_OR_TICKERS}` over `{WINDOW}`.

## Prompt

```text
Track sector influencer consensus for {SECTOR_OR_TICKERS}.
Use x_user_search to identify high-signal accounts, then time-bounded keyword and semantic
searches for their posts about the sector, tickers, catalysts, valuation, risks, and
earnings. Fetch important threads and classify each account's stance as bullish, bearish,
neutral, or changing.

Cross-check narrative shifts with Massive news, price action, fundamentals, analyst data,
and options where relevant.
```

## Output Requirements

- Include influencer map with account type, credibility, stance, and recent change.
- Include narrative consensus shift and Massive confirmation or contradiction.
- Include search windows, endpoints, fields, and timestamps.
- End with accounts and themes to monitor.

## Quality Rules

- Do not treat follower count as credibility.
- Paraphrase posts and threads.
- Separate influencer consensus from market consensus.
- Flag promotional or conflicted accounts.
- Do not present the output as financial advice.
