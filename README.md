# Grok Explainer

Markdown prompt templates, reference notes, and a Codex-compatible skill for multi-agent, real-time investment research workflows.

The repository is organized around two complementary research tracks:

- **Structured market data** via Massive API, formerly Polygon.io.
- **Social and narrative signal** via X/Twitter search, thread, user, and video tools.

It also includes a primer that documents the intended multi-agent sandbox workflow and tool-selection model.

## Repository Structure

```text
.
├── README.md
├── SKILL.md
├── docs/
│   └── agent-system-primer.md
└── prompts/
    └── finance/
        ├── ai-options-flow-market-buzz.md
        ├── deep-ai-stock-due-diligence.md
        ├── multi-stock-ai-sector-pulse.md
        ├── quick-ai-stock-snapshot.md
        ├── Value Analysis.md
        ├── massive-api/
        │   ├── README.md
        │   ├── catalysts/
        │   ├── competitive-position/
        │   ├── consensus/
        │   ├── derivatives/
        │   ├── earnings/
        │   ├── fundamentals/
        │   ├── positioning/
        │   ├── risk/
        │   ├── thesis/
        │   └── valuation/
        └── x-twitter/
            ├── README.md
            ├── catalysts/
            ├── competitive-position/
            ├── events/
            ├── influence/
            ├── leadership/
            ├── media/
            ├── products/
            ├── risk/
            └── sentiment/
```

## Quick Start

1. Pick the template that matches the research task.
2. Replace placeholders such as `{TICKER}`, `{TICKER1}`, `{TICKER2}`, and `{TICKER3}`.
3. Run the prompt with an agent that has the relevant live tools enabled.
4. Cross-check market-moving claims against primary filings, company materials, trusted news, or structured data before treating the output as actionable.

## Main Agent Prompt

Use this as the main persona, role, and tone prompt for an agent working with this repository:

```text
You are Grok Explainer, a real-time investment research analyst for public-market analysis.

Your role is to turn live market data, company fundamentals, filings, options activity, news, and social sentiment into clear, source-grounded investor briefings. You are especially useful for AI-related stocks, single-name due diligence, options-flow checks, valuation work, and narrative/sentiment analysis.

Persona:
- Direct, analytical, and skeptical.
- Practical for investors and traders, not promotional.
- Comfortable with uncertainty and explicit about data gaps.
- Focused on risk/reward, catalysts, positioning, valuation, and what would change the thesis.

Tone:
- Concise, factual, and actionable.
- Balanced rather than bullish or bearish by default.
- Plain-English explanations backed by quantitative evidence.
- No generic filler, hype, or unsupported predictions.
- Separate confirmed facts from speculation, sentiment, rumors, and engagement-driven noise.

Research Discipline:
- Use live tools whenever market prices, news, estimates, options data, or social sentiment may have changed.
- Prefer Massive API for structured market data, fundamentals, options, filings, ownership, ratios, and corporate actions.
- Treat Polygon.io references as legacy Massive API references unless the task is specifically about migration.
- Use X/Twitter tools for sentiment, narrative shifts, rumors, influential accounts, post-earnings reaction, product reception, and viral media.
- Attribute claims to sources, endpoints, fields, dates, and freshness where possible.
- Do not infer certainty from social engagement, high options volume, or unsourced claims.
- Cross-check market-moving claims against filings, company materials, trusted news, or structured data.
- State limitations clearly when a tool, endpoint, field, or source cannot support the requested conclusion.

Output Style:
- Lead with the answer or executive view.
- Use tables for comparable metrics, options contracts, scenarios, peers, or sentiment buckets.
- Include concise takeaways that explain what the numbers actually mean.
- End with what to watch next: catalysts, risks, invalidation signals, technical levels, or data points.
- Never present the output as financial advice.
```

## Main Prompt Templates

| Template | Best For | File |
| --- | --- | --- |
| Quick Real-Time AI Stock Snapshot | Fast investor checks on a single AI-related stock | [quick-ai-stock-snapshot.md](prompts/finance/quick-ai-stock-snapshot.md) |
| Deep AI Stock Due Diligence Brief | Fuller investor review of one AI-related stock | [deep-ai-stock-due-diligence.md](prompts/finance/deep-ai-stock-due-diligence.md) |
| AI Stock Options Flow + Market Buzz | Trader-focused options activity and short-term sentiment | [ai-options-flow-market-buzz.md](prompts/finance/ai-options-flow-market-buzz.md) |
| Multi-Stock AI Sector Pulse | Comparing multiple AI-related stocks by momentum, news, and sentiment | [multi-stock-ai-sector-pulse.md](prompts/finance/multi-stock-ai-sector-pulse.md) |
| Value Analysis | Comprehensive value-investor ratio analysis with historical and peer benchmarking | [Value Analysis.md](<prompts/finance/Value Analysis.md>) |

## Prompt Libraries

| Library | Contents | File |
| --- | --- | --- |
| Massive API Investment Research Library | Ten prompts for fundamentals, valuation, earnings, consensus, ownership, risk, options, catalysts, competitive position, and thesis synthesis | [massive-api/README.md](prompts/finance/massive-api/README.md) |
| X Twitter Investment Research Library | Ten prompts for sentiment, earnings reaction, leadership signals, bear theses, product reception, influencer maps, narrative benchmarking, rumors, events, and viral video analysis | [x-twitter/README.md](prompts/finance/x-twitter/README.md) |

## Skill Entry Point

[SKILL.md](SKILL.md) is a Codex skill for Massive API investment research. It covers:

- The Massive API rebrand from Polygon.io and compatibility with legacy `POLYGON_API_KEY`, `api.polygon.io`, and `polygon-api-client` references.
- Preferred authentication and base URL conventions.
- Pagination, filter operator syntax, and endpoint selection.
- A reusable Python client pattern for investment research queries.
- Endpoint maps for fundamentals, valuation, pricing, options, filings, ownership, news, corporate actions, crypto, forex, futures, and macro data.

Use this skill when an agent needs to query Massive or legacy Polygon endpoints for market data.

## Reference Docs

| Document | Purpose |
| --- | --- |
| [Agent System Primer](docs/agent-system-primer.md) | Overview of the sandbox, agent roles, code execution flow, tool decision algorithm, tool inventory, and Mermaid diagrams |

## Tool Assumptions

- The Massive API prompts assume access to Massive REST API endpoints and documentation.
- Legacy Polygon.io names may still appear in code, packages, URLs, and environment variables. Treat them as compatibility-era Massive references unless the task is explicitly about migration.
- The X/Twitter prompts assume access to keyword search, semantic search, user search, thread fetch, and video inspection tools.
- The broader finance templates assume access to live market data, current news, and social sentiment.
- Market data, consensus estimates, news, and social narratives can change quickly. Use live tools for any investor-facing answer.

## Research Discipline

- Attribute claims to data sources instead of asserting unsupported facts.
- Preserve relevant endpoint names, time windows, and data freshness in final outputs.
- State API gaps explicitly when a field or endpoint does not support the requested analysis.
- Separate confirmed data from rumors, sentiment, and engagement-driven noise.
- Do not treat these templates as financial advice.
