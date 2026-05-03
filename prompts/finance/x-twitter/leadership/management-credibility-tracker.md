# Management Credibility Tracker

Use this template for monitoring whether management communication is consistent with later outcomes and market expectations.

## Metadata

- **Analysis type:** Management credibility analysis
- **Goal:** Assess whether executives for `{TICKER}` are gaining or losing credibility with investors.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`, `x_user_search`, `x_thread_fetch`, Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Synthesize credibility signal and thesis impact.
- **Harper:** Gather executive posts, interviews, clips, investor reactions, and web sources.
- **Benjamin:** Pull Massive earnings, guidance, analyst actions, filings, news, and price reactions.
- **Lucas:** Audit attribution, timing, and claim versus outcome matching.

## Input

Track management credibility for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Track management credibility for {TICKER} using X, web, and Massive data.
Search X for executive names, company handle, guidance, credibility, trust, sandbag,
overpromise, underdeliver, transparency, and conference/interview terms. Fetch important
threads and classify account credibility.

Cross-check management claims with Massive earnings, guidance, analyst actions, filings,
news, and price reactions. Identify promises, outcomes, misses, and improved disclosure.
```

## Output Requirements

- Include management claim versus outcome table.
- Include investor trust narrative and credibility rating.
- Include X windows, web sources, Massive endpoints, fields, and timestamps.
- End with credibility watch items.

## Quality Rules

- Do not judge credibility from sentiment alone.
- Paraphrase posts and executive comments.
- Use time-bound X searches and state the exact search window.
- Time-align claims and outcomes.
- Flag unverifiable claims.
- Do not present the output as financial advice.
