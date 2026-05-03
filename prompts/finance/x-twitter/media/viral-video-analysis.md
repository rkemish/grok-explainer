# Viral Video Analysis

Use this template to pull actual content out of viral video posts about a company.

## Metadata

- **Analysis type:** Primary-source media analysis
- **Goal:** Avoid taking a viral video at the framer's word and base the investment view on what was actually said or shown.
- **Tools leveraged:** `x_keyword_search`, `view_x_video`, `x_thread_fetch`

## Prompt

```text
Find and analyze any viral video content related to {TICKER} on X.
Step 1: x_keyword_search $({TICKER}) filter:has_engagement over the last 14 days, filtering
posts that contain a video.
Step 2: Rank by engagement and take the top 5.
Step 3: For each, view_x_video to extract frames and subtitles. Summarize what is
actually said or shown in the video - distinguishing this from the poster's framing
in the tweet text.
Step 4: x_thread_fetch the post to capture how the audience interpreted it (agreement,
pushback, factual corrections).
Output: per video: (a) who is speaking and their affiliation, (b) the substantive claim
or moment, (c) whether the poster's framing matches the actual content, (d) the
audience's reaction, and (e) implications for the {TICKER} thesis. Paraphrase - do not
reproduce video transcripts verbatim.
```

## Source Discipline

- Use time-bound X searches and state the exact search window.
- Paraphrase posts, frames, subtitles, and threads; do not quote them verbatim.
- Attribute claims by source type and include credibility context.
- Do not present the output as financial advice.
