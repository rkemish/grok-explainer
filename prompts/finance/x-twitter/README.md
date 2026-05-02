# X Twitter Investment Research Prompt Library

Use these templates with an LLM agent that has access to X platform tools:

- `x_keyword_search`
- `x_semantic_search`
- `x_user_search`
- `x_thread_fetch`
- `view_x_video`

These prompts complement structured market data by surfacing real-time sentiment, narratives, crowd signal, rumors, and primary-source media reactions that may not appear in fundamentals.

Replace `{TICKER}` with the target symbol, such as `MU`, `NVDA`, or `AAPL`. Where company name matters more than ticker, the agent should resolve the company name first.

## Recommended Workflows

1. **Daily position monitoring:** Run prompts 1, 4, and 8 to catch sentiment shifts, organized bear activity, and rumors.
2. **Pre-earnings prep:** Run prompts 2 and 6 to understand last quarter's reaction and identify accounts worth watching.
3. **New-name diligence:** Run prompts 3, 6, and 7 to map leadership signals, influential accounts, and relative narrative strength.
4. **Event-driven setups:** Run prompts 5, 9, and 10 around product launches, investor days, interviews, activist pitches, or conference appearances.

## Prompt Index

| # | Prompt | Category | Best For | File |
| --- | --- | --- | --- | --- |
| 1 | Real-Time Sentiment Pulse | Sentiment | Establishing the current crowd baseline and price/narrative divergence | [sentiment/real-time-sentiment-pulse.md](sentiment/real-time-sentiment-pulse.md) |
| 2 | Post-Earnings Reaction Tape | Events | Reconstructing the X reaction after the latest earnings report | [events/post-earnings-reaction-tape.md](events/post-earnings-reaction-tape.md) |
| 3 | Executive and Insider Social Footprint | Leadership | Monitoring public executive, board, and insider signals | [leadership/executive-insider-social-footprint.md](leadership/executive-insider-social-footprint.md) |
| 4 | Short-Seller and Bear Thesis Detection | Risk | Surfacing organized bearish narratives and skeptical campaigns | [risk/short-seller-bear-thesis-detection.md](risk/short-seller-bear-thesis-detection.md) |
| 5 | Product Launch and Customer Reception | Products | Reading customer, reviewer, and end-user response to launches | [products/product-launch-customer-reception.md](products/product-launch-customer-reception.md) |
| 6 | FinTwit Influencer Map | Influence | Identifying the highest-signal accounts discussing the name | [influence/fintwit-influencer-map.md](influence/fintwit-influencer-map.md) |
| 7 | Competitor Narrative Benchmarking | Competitive Position | Comparing share of voice, sentiment, and themes against peers | [competitive-position/competitor-narrative-benchmarking.md](competitive-position/competitor-narrative-benchmarking.md) |
| 8 | Rumor and Leak Detection | Catalysts | Tracking unconfirmed claims, leaks, and catalyst chatter | [catalysts/rumor-leak-detection.md](catalysts/rumor-leak-detection.md) |
| 9 | Conference and Event Coverage | Events | Reconstructing live X coverage from investor days and conferences | [events/conference-event-coverage.md](events/conference-event-coverage.md) |
| 10 | Viral Video Analysis | Media | Extracting substance from CEO clips, interviews, activist pitches, and webinars | [media/viral-video-analysis.md](media/viral-video-analysis.md) |

## Operating Reminders

- Paraphrase posts and videos. Do not reproduce posts or transcripts verbatim.
- Attribute claims instead of asserting them as facts.
- Separate signal from engagement-driven noise.
- Weight credibility, track record, and author identity alongside raw engagement.
- Time-bound every search window with `since:` and `until:` filters where possible.
- Cross-check any market-moving claim against filings, company materials, trusted news, or structured data before treating it as actionable.

