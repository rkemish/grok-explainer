# Earnings Whisper Versus Consensus Gap

Use this template for comparing X earnings expectations with structured consensus, guidance, and options data.

## Metadata

- **Analysis type:** Earnings expectation gap
- **Goal:** Identify whether X expectations for `{TICKER}` are higher, lower, or different from consensus.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`, Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Explain whether the crowd is positioned for a surprise.
- **Harper:** Gather X whispers, high-engagement earnings posts, and credible previews.
- **Benjamin:** Pull Massive earnings, guidance, analyst, consensus, options, and price data.
- **Lucas:** Audit whether social claims are sourced and time-bounded.

## Input

Compare earnings whisper versus consensus for `{TICKER}` before `{EARNINGS_DATE}`.

## Prompt

```text
Compare X earnings whispers versus structured consensus for {TICKER}.
Use time-bounded X searches for {TICKER} earnings, whisper, beat, miss, guide, channel
checks, demand, margin, EPS, revenue, and options. Pull top engaged posts and semantic
matches from the last {WINDOW}.

Cross-check with Massive earnings, guidance, analyst ratings, consensus ratings, options
implied move, historical bars, and news. Identify gaps between social expectations and
structured estimates.
```

## Output Requirements

- Include consensus/guidance table and X expectation table.
- Include whisper gap: above consensus, below consensus, different metric focus, or no clear gap.
- Include source credibility and search windows.
- Cite Massive endpoints, fields, and timestamps.

## Quality Rules

- Do not treat anonymous whispers as estimates.
- Paraphrase posts and claims.
- Flag unsupported channel checks.
- Separate expectation gap from likely outcome.
- Do not present the output as financial advice.
