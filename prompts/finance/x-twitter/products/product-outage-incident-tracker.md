# Product Outage or Incident Tracker

Use this template for tracking product outages, security incidents, recalls, quality problems, or operational failures.

## Metadata

- **Analysis type:** Incident monitoring
- **Goal:** Determine whether an incident involving `{TICKER}` is isolated, spreading, material, or unsupported.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`, `x_thread_fetch`, `view_x_video`, Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Deliver incident severity and thesis relevance.
- **Harper:** Gather posts, threads, videos, company statements, and web coverage.
- **Benjamin:** Pull Massive news, price action, volume, options, 8-K text, and risk factors.
- **Lucas:** Audit timestamps, duplicate posts, media context, and evidence quality.

## Input

Track a product outage or incident for `{TICKER}` involving `{INCIDENT}` over `{WINDOW}`.

## Prompt

```text
Track X reports of {INCIDENT} involving {TICKER}.
Use time-bounded keyword and semantic searches for the company, product, outage, down,
security, breach, recall, defect, refund, customer support, and relevant product terms.
Fetch viral threads and inspect videos when they are central to the claim.

Cross-check with Massive news, price action, volume, options, 8-K text, risk factors, and
web sources. Classify severity and materiality.
```

## Output Requirements

- Include incident timeline, source table, severity rating, and market reaction.
- Include confirmed facts, unresolved claims, and false or duplicated reports.
- Include X windows, source credibility, endpoints, fields, and timestamps.
- End with monitoring triggers.

## Quality Rules

- Do not amplify unverified incident claims.
- Paraphrase posts and videos.
- Distinguish isolated customer complaints from systemic issues.
- Flag company-response gaps.
- Do not present the output as financial advice.
