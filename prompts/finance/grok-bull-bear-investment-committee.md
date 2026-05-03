# Grok Bull Bear Investment Committee

Use this template for a structured investment debate where Benjamin builds the data case, Harper builds the narrative case, Lucas audits tools, and Grok decides.

## Metadata

- **Analysis type:** Bull/bear investment committee
- **Goal:** Force a balanced decision on `{TICKER}` by separating data, narrative, risk, and uncertainty.
- **Tools leveraged:** `code_execution`, Massive REST API, `web_search`, `browse_page`, `x_keyword_search`, `x_semantic_search`, `chatroom_send`

## Grok Orchestration

- **Grok:** Moderate the debate, remove weak claims, and issue the final committee decision.
- **Harper:** Present the best bull and bear narratives from news, web sources, and X.
- **Benjamin:** Present the best bull and bear evidence from Massive fundamentals, valuation, price action, options, filings, ownership, and analyst data.
- **Lucas:** Challenge unsupported claims, missing endpoints, stale data, and hallucination risk.

## Input

Run a bull/bear investment committee on `{TICKER}` for `{HORIZON}`.

## Prompt

```text
Run a Grok bull/bear investment committee for {TICKER}.

Benjamin must build the strongest data-backed bull case and bear case using Massive API
endpoints and computed metrics. Harper must build the strongest narrative bull case and
bear case using web and X tools. Lucas must audit both sides for source quality, stale data,
missing endpoint coverage, and unsupported inference.

Grok must synthesize the debate into a final stance: bullish, bearish, mixed, or no-edge.
The final stance must explain what evidence matters most and what would change the decision.
```

## Output Requirements

- Include a committee summary, bull case, bear case, adjudication table, final stance, and monitoring plan.
- Include separate rows for data strength, narrative strength, valuation, catalysts, risks, and uncertainty.
- Include endpoint and source citations for each major claim.
- Include "claims rejected" when evidence is weak.
- End with decision triggers and no-edge conditions.

## Quality Rules

- Do not let one side win by volume of claims.
- Prioritize evidence quality over narrative confidence.
- State when the correct answer is no-edge.
- Paraphrase X posts and label speculation.
- Do not present the output as financial advice.
