# Analyst Day Investor Day Live Tape

Use this template for reconstructing live X reaction to analyst days, investor days, product events, and company presentations.

## Metadata

- **Analysis type:** Event tape reconstruction
- **Goal:** Capture what changed during `{EVENT}` for `{TICKER}` and whether the market reaction was justified.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`, `x_thread_fetch`, `view_x_video`, Massive REST API

## Grok Orchestration

- **Grok:** Synthesize event substance, narrative reaction, and price reaction.
- **Harper:** Pull live X posts, threads, clips, and credible attendee commentary.
- **Benjamin:** Pull Massive intraday bars, snapshots, options, news, and related ticker moves.
- **Lucas:** Audit event timing, post chronology, and media-source credibility.

## Input

Reconstruct the live tape for `{TICKER}` during `{EVENT}` on `{DATE}`.

## Prompt

```text
Reconstruct the X live tape for {TICKER} during {EVENT}.
Use time-bounded x_keyword_search and x_semantic_search around the event window for the
company name, ticker, event name, management names, product names, guide, target, margin,
AI, and investor day. Use x_thread_fetch for high-engagement threads and view_x_video for
important clips.

Cross-check with Massive intraday price action, news, options, and related ticker moves.
Paraphrase posts and classify what was new versus already known.
```

## Output Requirements

- Include event timeline, top narrative shifts, price reaction, and evidence table.
- Include top bullish and bearish takes, paraphrased.
- Include source credibility, search windows, endpoints, and timestamps.
- End with follow-up questions from the event.

## Quality Rules

- Do not quote posts or video transcripts verbatim.
- Separate live reaction from confirmed company guidance.
- Flag clips without full context.
- Time-align posts and price action.
- Do not present the output as financial advice.
