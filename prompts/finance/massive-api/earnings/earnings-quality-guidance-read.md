# Earnings Quality and Guidance Read

Use this template to review the last four earnings reports, including beats and misses, guidance changes, market reaction, and management tone.

## Analysis Type

Earnings analysis - quantitative results plus qualitative tone.

## Goal

Judge whether management is consistently delivering and whether sentiment is improving or deteriorating.

## Input

Analyze `{TICKER}` using the Massive API.

## Prompt

```text
Fetch the last 4 earnings releases, transcripts, and consensus estimates for {TICKER} from
the Massive API. For each quarter: report beat/miss on revenue and EPS, change in forward
guidance, and the 1-day and 5-day post-print price reaction. Then run sentiment analysis on
management's prepared remarks vs. Q&A and tell me whether tone is improving, deteriorating,
or stable. Quote no more than one short phrase per call.
```

## Output Requirements

- Cover the last four earnings periods.
- Show revenue and EPS beat or miss versus consensus.
- Summarize forward guidance changes.
- Include 1-day and 5-day post-earnings price reaction.
- Compare prepared remarks tone against Q&A tone.
- Quote no more than one short phrase per earnings call.

## Source Discipline

- Cite every Massive endpoint and field used, including actuals, estimates, guidance, analyst action, price, timestamp, and data freshness fields.
- State unavailable fields explicitly instead of substituting assumptions.
- Do not present the output as financial advice.
