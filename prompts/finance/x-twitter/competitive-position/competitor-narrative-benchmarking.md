# Competitor Narrative Benchmarking

Use this template to compare the X conversation around a company against its closest peers.

## Metadata

- **Analysis type:** Competitive / relative-positioning analysis
- **Goal:** See whether `{TICKER}` is gaining or losing mindshare versus companies it competes with for capital and customers.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`

## Prompt

```text
Benchmark {TICKER}'s X narrative against its 3-5 closest peers (the user will provide
the peer set, or the agent can use sector logic to propose one).
Step 1: For each ticker in {{TICKER}, peer_1, peer_2, ...}, x_keyword_search the cashtag
with filter:has_engagement over the last 30 days. Capture: total post volume, total
engagement, unique authors.
Step 2: x_semantic_search "<company-name> winning" and "<company-name> losing" for each.
Tally bullish vs. bearish posts.
Output: a 4-column comparison table (volume, engagement, sentiment %, top recurring theme),
plus a short paragraph naming who is winning the narrative and why. Flag any peer where
sentiment is moving sharply in either direction relative to {TICKER}.
```

## Source Discipline

- Use time-bound X searches and state the exact search window.
- Paraphrase posts and themes; do not quote them verbatim.
- Attribute claims by source type and include credibility context.
- Do not present the output as financial advice.
