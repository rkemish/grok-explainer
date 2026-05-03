# Product Launch and Customer Reception

Use this template to measure how customers, reviewers, and end-users are reacting to a recent product, feature, or service launch.

## Metadata

- **Analysis type:** Voice-of-customer / demand-signal analysis
- **Goal:** Get a leading indicator on demand and product-market fit before it shows up in revenue.
- **Tools leveraged:** `x_keyword_search`, `x_semantic_search`, `view_x_video`

## Prompt

```text
Assess customer reception of {TICKER}'s most recent product launch.
Step 1: Confirm the product name and launch date (ask the user or use prior context).
Step 2: x_keyword_search the product name with filter:has_engagement, restricted to
since:<launch-date>. Pull top 100 by engagement.
Step 3: x_semantic_search for "<product> review", "<product> disappointing",
"<product> game changer", "<product> bug", "<product> vs <competitor>".
Step 4: For any post linking to a product video or unboxing, use view_x_video to extract
frames and subtitles so you can summarize the reviewer's actual takeaway.
Output: a reception scorecard with (a) volume of posts, (b) sentiment split,
(c) top 3 praised aspects, (d) top 3 criticized aspects, (e) any feature/bug
that's becoming a viral talking point, and (f) implied demand signal vs. expectations.
```

## Source Discipline

- Use time-bound X searches and state the exact search window.
- Paraphrase posts, threads, and videos; do not quote them verbatim.
- Attribute claims by source type and include credibility context.
- Do not present the output as financial advice.
