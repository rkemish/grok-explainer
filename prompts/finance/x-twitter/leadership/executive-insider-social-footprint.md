# Executive and Insider Social Footprint

Use this template to map the social-media presence of a company's executives, board members, and large insiders.

## Metadata

- **Analysis type:** Insider qualitative monitoring
- **Goal:** Detect tone, distraction, controversy, or strategic hints from leadership before they show up in earnings calls or filings.
- **Tools leveraged:** `x_user_search`, `x_thread_fetch`, `x_keyword_search`

## Prompt

```text
Build a social-footprint map for {TICKER}'s leadership.
Step 1: x_user_search the CEO, CFO, and any other named executive officers, plus any
board members known to be active on X. For each, capture handle, follower count,
verification status, and posting frequency (last 90 days).
Step 2: For each active executive account, x_keyword_search their recent posts mentioning
the company, the industry, or competitors. Use x_thread_fetch on any post that drew >100
replies to see how the audience reacted.
Output: a one-paragraph profile per executive covering tone (promotional / candid /
controversial), what they post about, and any signal worth flagging (industry views,
hints at strategy, public disputes, distraction). Note explicitly if any executive
is silent or has gone dark recently.
```

