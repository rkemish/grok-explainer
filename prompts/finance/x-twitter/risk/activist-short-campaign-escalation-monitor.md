# Activist or Short-Campaign Escalation Monitor

Use this template for tracking whether criticism of a company is escalating into an organized activist or short campaign.

## Metadata

- **Analysis type:** Campaign escalation monitor
- **Goal:** Detect credible activist, short-seller, or organized bear activity around `{TICKER}`.
- **Tools leveraged:** `x_semantic_search`, `x_keyword_search`, `x_thread_fetch`, `x_user_search`, Massive REST API, `web_search`

## Grok Orchestration

- **Grok:** Judge escalation level and thesis relevance.
- **Harper:** Track accounts, threads, source documents, and web corroboration.
- **Benjamin:** Pull Massive short interest, short volume, filings, news, price action, and ownership data.
- **Lucas:** Audit allegations, source credibility, and unsupported claims.

## Input

Monitor activist or short-campaign escalation for `{TICKER}` over `{WINDOW}`.

## Prompt

```text
Monitor X for activist or short-campaign escalation around {TICKER}.
Use time-bounded semantic and keyword searches for fraud, accounting, activist, short
report, board, governance, insider selling, customer churn, guidance cut, and known firm
names. Fetch threads for viral posts and use user search to profile key accounts.

Cross-check allegations against Massive filings, risk factors, 8-K text, short interest,
short volume, insider data, price action, and news.
```

## Output Requirements

- Include allegation table with source type, evidence cited, credibility, and Massive cross-check.
- Include escalation stage: noise, early campaign, credible campaign, or thesis-threatening.
- Include X windows, account credibility, endpoints, fields, and timestamps.
- End with verification steps.

## Quality Rules

- Paraphrase allegations; do not amplify them verbatim.
- Do not assume coordination without evidence.
- Separate source credibility from allegation severity.
- Flag legal or evidentiary uncertainty.
- Do not present the output as financial advice.
