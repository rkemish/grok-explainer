# Short-Seller and Bear Thesis Detection

Use this template to hunt for organized bear narratives, short-seller reports, viral skeptical threads, or coordinated criticism.

## Metadata

- **Analysis type:** Risk / contrarian-signal detection
- **Goal:** Surface short-seller campaigns or accumulating skepticism before it becomes a price catalyst.
- **Tools leveraged:** `x_semantic_search`, `x_thread_fetch`, `x_user_search`

## Prompt

```text
Scan X for organized bearish activity on {TICKER}.
Step 1: x_semantic_search for "{TICKER} fraud", "{TICKER} accounting concerns",
"{TICKER} short report", "{TICKER} channel stuffing", "{TICKER} insider selling",
"{TICKER} customer churn", "{TICKER} guidance cut". Pull the top 30 results per query.
Step 2: For any post that has gone viral (>500 reposts or >200 replies),
x_thread_fetch to capture the full argument and the rebuttals.
Step 3: x_user_search the authors. Flag any account that is a known short-selling firm
(Hindenburg, Muddy Waters, Spruce Point, etc.) or a high-follower skeptic.
Output: a bear-case dossier listing: (a) specific allegations, (b) named accounts driving
them, (c) supporting evidence cited, (d) the company's or the bulls' rebuttal, and
(e) a credibility rating (high/medium/low) per claim. Paraphrase - never quote allegations.
```

## Source Discipline

- Use time-bound X searches and state the exact search window.
- Paraphrase allegations and threads; do not quote them verbatim.
- Attribute claims by source type and include credibility context.
- Do not present the output as financial advice.
