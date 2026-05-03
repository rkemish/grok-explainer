# X Twitter Investment Research Prompt Library

Use these templates with Grok and its agent team when an investment workflow needs X platform tools:

- `x_keyword_search`
- `x_semantic_search`
- `x_user_search`
- `x_thread_fetch`
- `view_x_video`

These prompts complement Massive structured market data by surfacing real-time sentiment, narratives, crowd signal, rumors, source credibility, and primary-source media reactions that may not appear in fundamentals.

Replace `{TICKER}` with the target symbol, such as `MU`, `NVDA`, or `AAPL`. Where company name matters more than ticker, resolve the company name first.

## Recommended Workflows

1. **Daily position monitoring:** Run prompts 1, 2, 7, 8, 11, and 20.
2. **Pre-earnings prep:** Run prompts 4, 5, 9, 10, and pair with Massive earnings prompts.
3. **New-name diligence:** Run prompts 6, 14, 15, 16, 17, 21, and 22.
4. **Event-driven setups:** Run prompts 5, 10, 12, 13, 18, and 19 around product launches, investor days, incidents, or viral claims.
5. **Risk escalation checks:** Run prompts 7, 8, 13, 18, and 21 when rumors, short reports, outages, or viral charts appear.

## Prompt Index

| # | Prompt | Category | Best For | File |
| --- | --- | --- | --- | --- |
| 1 | Real-Time Sentiment Pulse | Sentiment | Establishing the current crowd baseline and price/narrative divergence | [sentiment/real-time-sentiment-pulse.md](sentiment/real-time-sentiment-pulse.md) |
| 2 | Market-Wide Risk Appetite Pulse | Sentiment | Reading risk-on or risk-off crowd mood and checking it against market data | [sentiment/market-wide-risk-appetite-pulse.md](sentiment/market-wide-risk-appetite-pulse.md) |
| 3 | Options-Flow Social Confirmation | Sentiment | Verifying X options-flow claims against structured options data | [sentiment/options-flow-social-confirmation.md](sentiment/options-flow-social-confirmation.md) |
| 4 | Post-Earnings Reaction Tape | Events | Reconstructing the X reaction after the latest earnings report | [events/post-earnings-reaction-tape.md](events/post-earnings-reaction-tape.md) |
| 5 | Earnings Whisper Versus Consensus Gap | Events | Comparing social earnings expectations with consensus, guidance, and options data | [events/earnings-whisper-vs-consensus-gap.md](events/earnings-whisper-vs-consensus-gap.md) |
| 6 | Macro-Event Narrative Watch | Events | Tracking how X interprets macro events and whether market data agrees | [events/macro-event-narrative-watch.md](events/macro-event-narrative-watch.md) |
| 7 | Analyst Day Investor Day Live Tape | Events | Reconstructing live X reaction to company presentations and investor events | [events/analyst-day-investor-day-live-tape.md](events/analyst-day-investor-day-live-tape.md) |
| 8 | Conference and Event Coverage | Events | Reconstructing live X coverage from investor days and conferences | [events/conference-event-coverage.md](events/conference-event-coverage.md) |
| 9 | Executive and Insider Social Footprint | Leadership | Monitoring public executive, board, and insider signals | [leadership/executive-insider-social-footprint.md](leadership/executive-insider-social-footprint.md) |
| 10 | Management Credibility Tracker | Leadership | Comparing executive claims with later outcomes and investor trust | [leadership/management-credibility-tracker.md](leadership/management-credibility-tracker.md) |
| 11 | Short-Seller and Bear Thesis Detection | Risk | Surfacing organized bearish narratives and skeptical campaigns | [risk/short-seller-bear-thesis-detection.md](risk/short-seller-bear-thesis-detection.md) |
| 12 | Activist or Short-Campaign Escalation Monitor | Risk | Tracking whether criticism is escalating into a credible campaign | [risk/activist-short-campaign-escalation-monitor.md](risk/activist-short-campaign-escalation-monitor.md) |
| 13 | Product Launch and Customer Reception | Products | Reading customer, reviewer, and end-user response to launches | [products/product-launch-customer-reception.md](products/product-launch-customer-reception.md) |
| 14 | Customer Spending Anecdote Map | Products | Mapping customer demand anecdotes and checking them against data | [products/customer-spending-anecdote-map.md](products/customer-spending-anecdote-map.md) |
| 15 | Product Outage or Incident Tracker | Products | Tracking outages, security incidents, recalls, quality issues, or operational failures | [products/product-outage-incident-tracker.md](products/product-outage-incident-tracker.md) |
| 16 | FinTwit Influencer Map | Influence | Identifying the highest-signal accounts discussing the name | [influence/fintwit-influencer-map.md](influence/fintwit-influencer-map.md) |
| 17 | Sector Influencer Consensus Shift | Influence | Detecting when high-signal accounts change stance on a sector or basket | [influence/sector-influencer-consensus-shift.md](influence/sector-influencer-consensus-shift.md) |
| 18 | Competitor Narrative Benchmarking | Competitive Position | Comparing share of voice, sentiment, and themes against peers | [competitive-position/competitor-narrative-benchmarking.md](competitive-position/competitor-narrative-benchmarking.md) |
| 19 | Competitor Share-Shift Narrative | Competitive Position | Checking whether X claims imply real market-share movement | [competitive-position/competitor-share-shift-narrative.md](competitive-position/competitor-share-shift-narrative.md) |
| 20 | Rumor and Leak Detection | Catalysts | Tracking unconfirmed claims, leaks, and catalyst chatter | [catalysts/rumor-leak-detection.md](catalysts/rumor-leak-detection.md) |
| 21 | Viral Video Analysis | Media | Extracting substance from CEO clips, interviews, activist pitches, and webinars | [media/viral-video-analysis.md](media/viral-video-analysis.md) |
| 22 | Viral Chart or Claim Fact-Check | Media | Verifying viral charts, screenshots, and market claims with source data | [media/viral-chart-claim-fact-check.md](media/viral-chart-claim-fact-check.md) |

## Operating Reminders

- Paraphrase posts, threads, and videos. Do not reproduce posts or transcripts verbatim.
- Attribute claims instead of asserting them as facts.
- Separate signal from engagement-driven noise.
- Weight credibility, track record, source identity, and conflicts alongside raw engagement.
- Time-bound every search window with `since:` and `until:` filters where possible.
- Cross-check any market-moving claim against filings, company materials, trusted news, Massive data, or other structured sources before treating it as actionable.
- These prompts support investment research workflows and should not be used as financial advice.
