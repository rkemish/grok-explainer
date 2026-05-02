# Conference and Event Coverage

Use this template to reconstruct what was said at investor days, industry conferences, product events, or similar live events covered on X.

## Metadata

- **Analysis type:** Event reconstruction / primary-source synthesis
- **Goal:** Get the substance of an event you did not attend, including takes that did not make it into the official press release.
- **Tools leveraged:** `x_keyword_search`, `x_thread_fetch`, `view_x_video`

## Prompt

```text
Reconstruct the X coverage of {TICKER}'s most recent investor day, conference appearance,
or major industry event.
Step 1: Confirm the event name, date, and any official hashtag. (User input or prior context.)
Step 2: x_keyword_search the hashtag plus $({TICKER}) since:<event-date> until:<event-date+1d>,
filter:has_engagement.
Step 3: Identify the top 10 thread starters by engagement. x_thread_fetch each.
Step 4: For any video clip posted from the event (especially CEO/CFO Q&A snippets),
view_x_video to extract the actual content rather than relying on the poster's framing.
Output: an event recap structured as: (a) major announcements, (b) most-discussed numbers
or guidance signals, (c) most-discussed Q&A exchange, (d) sell-side reaction tone,
(e) one paragraph on what the press release left out that X surfaced.
```

