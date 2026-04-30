# Grok Explainer

A small collection of Markdown prompt templates and reference notes for multi-agent, real-time AI stock analysis workflows.

## Repository Structure

```text
.
├── README.md
├── docs/
│   └── agent-system-primer.md
└── prompts/
    └── finance/
        ├── ai-options-flow-market-buzz.md
        ├── deep-ai-stock-due-diligence.md
        ├── multi-stock-ai-sector-pulse.md
        └── quick-ai-stock-snapshot.md
```

## Documents

- [Agent System Primer](docs/agent-system-primer.md): Overview of the sandbox, agent roles, tool decision algorithm, tool inventory, and Mermaid diagrams.

## Finance Prompt Templates

| Template | Best For | File |
| --- | --- | --- |
| Quick Real-Time AI Stock Snapshot | Fast investor checks on a single AI-related stock | [quick-ai-stock-snapshot.md](prompts/finance/quick-ai-stock-snapshot.md) |
| Deep AI Stock Due Diligence Brief | Fuller investor review of one AI-related stock | [deep-ai-stock-due-diligence.md](prompts/finance/deep-ai-stock-due-diligence.md) |
| AI Stock Options Flow + Market Buzz | Trader-focused options activity and short-term sentiment | [ai-options-flow-market-buzz.md](prompts/finance/ai-options-flow-market-buzz.md) |
| Multi-Stock AI Sector Pulse | Comparing multiple AI-related stocks by momentum, news, and sentiment | [multi-stock-ai-sector-pulse.md](prompts/finance/multi-stock-ai-sector-pulse.md) |

## How to Use

1. Pick the template that matches the task.
2. Replace placeholders such as `{TICKER}`, `{TICKER1}`, `{TICKER2}`, and `{TICKER3}`.
3. Run the prompt with tools that can fetch live market data, current news, and social sentiment.

## Notes

- The finance templates assume access to Polygon, web search, and X search.
- The primer explains the intended multi-agent workflow and tool-selection logic.
- Market data and sentiment can change quickly, so use live tools for any investor-facing answer.
