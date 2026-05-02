# Rumor and Leak Detection

Use this template to surface unconfirmed but circulating claims, including M&A whispers, partnership leaks, layoff rumors, and regulatory chatter.

## Metadata

- **Analysis type:** Information-flow / catalyst-anticipation analysis
- **Goal:** Identify potentially market-moving rumors early enough to size or hedge a position before confirmation.
- **Tools leveraged:** `x_semantic_search`, `x_thread_fetch`, `x_user_search`

## Prompt

```text
Scan X for unconfirmed but circulating claims about {TICKER}.
Step 1: x_semantic_search for "{TICKER} acquisition rumor", "{TICKER} buyout",
"{TICKER} partnership leaked", "{TICKER} layoffs", "{TICKER} FDA",
"{TICKER} contract win", "{TICKER} guidance cut whispered", "{TICKER} CEO leaving".
Step 2: For each claim that surfaces, x_thread_fetch the originating post and trace
how it propagated.
Step 3: x_user_search the originator. Note whether they have a track record of accuracy,
are a known leaker, journalist, or anonymous account.
Output: a rumor log with (a) the specific claim, (b) the originator and their credibility,
(c) the propagation path (who amplified), (d) whether the claim has any corroborating
public evidence, and (e) implied directional impact if true. Mark each rumor as
high / medium / low credibility. Do not state rumors as facts.
```

