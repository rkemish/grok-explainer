---
name: massive-api-investment-research
description: Use this skill whenever an agent needs to query the Massive market-data REST API (formerly Polygon.io, rebranded October 30 2025 — see https://massive.com/docs/llms.txt) to support equity, options, crypto, forex, futures, or macro investment research. Trigger on any mention of Massive OR Polygon (the previous brand name) — including "polygon-api-client," `POLYGON_API_KEY`, `api.polygon.io`, or any tutorial, Stack Overflow answer, or repo that still uses the old name. Also trigger on requests involving ticker-level fundamentals, OHLC bars, snapshots, technical indicators, SEC filings (10-K/8-K/13-F/Form 3/Form 4), corporate actions, analyst ratings, options chains, short interest, ETF holdings, macro series like inflation and treasury yields, or generic asks like "pull data from Polygon/Massive," "build a query," "fetch fundamentals/quotes/trades," or "give me Python code that hits the API." The skill provides the rebrand-aware base URL and auth setup, URL patterns, the filter operator grammar, a reusable Python client that accepts either MASSIVE_API_KEY or POLYGON_API_KEY, pagination handling, and a use-case → endpoint map for portfolio research workflows.
---

# Massive API (formerly Polygon.io) — Investment Research Agent Guide

This skill teaches an LLM-powered agent how to query the **Massive REST API** (`https://api.massive.com`) to support investment research workflows: fundamentals, valuation, ownership, options, technicals, news, and macro context. The documentation index lives at `https://massive.com/docs/llms.txt`, and the full REST Markdown export lives at `https://massive.com/docs/rest/llms-full.txt`; this guide compresses what the agent needs to operate productively.

> **Rebrand notice.** On **October 30, 2025**, Polygon.io officially became **Massive** (massive.com). Existing API keys, accounts, and integrations continue to work, and `api.polygon.io` remains supported for an extended period while new code should prefer `api.massive.com`. Expect to encounter the old name everywhere: in customer code (`POLYGON_API_KEY`), in PyPI packages (`polygon-api-client`), in legacy URLs (`api.polygon.io`), in GitHub orgs (`github.com/polygon-io`), and in virtually every tutorial, Stack Overflow answer, and blog post written before late 2025. **Treat all "Polygon" references as compatibility-era Massive references.** This skill triggers on either name.

**Use this skill when** the user asks for any data Massive/Polygon can provide — even if they don't say either name explicitly (e.g., "pull MU's last 8 quarters of fundamentals," "get the option chain for AAPL," "what's the 10-yr treasury yield").

---

## 1. Core Concepts

### Base URL — both work
```
https://api.massive.com    ← preferred, current
https://api.polygon.io     ← legacy, still active during the parallel transition period
```
Both domains route to the same backend during the rebrand window. Default to `api.massive.com` for new code. **Don't rewrite working customer code that already points at `api.polygon.io`** — it isn't broken.

### Authentication — keys carry over unchanged
Massive uses **API key authentication**. Your existing Polygon.io key works as-is on the Massive domain; no re-issuance is required.

Pass the key via the `Authorization` header:
```
Authorization: Bearer <KEY>
```
Massive also documents `?apiKey=<KEY>` as a query-string option. Prefer the header in new code, because it keeps secrets out of URLs and logs.

**Environment variable conventions.** Customers will have one of two variable names already set:
- `MASSIVE_API_KEY` — newer convention
- `POLYGON_API_KEY` — what most existing code uses

The Python client below checks both. **Never hardcode the key.**

### SDK package names
- **Official Python SDK:** the current package is `massive` and the import is `from massive import RESTClient`. The legacy `polygon-api-client` package and `from polygon import RESTClient` import may still appear in older customer projects; treat them as compatibility-era code, not the preferred path for new examples.
- **Other languages:** current client libraries live under `github.com/massive-com`, while older links under `github.com/polygon-io` may still redirect or remain available during the transition.

If the customer wants pure REST without the SDK, use the Python client in §2 — it's lighter and has no compatibility ambiguity.

### Two URL styles
Massive uses two endpoint patterns. Recognize which one applies before constructing a query:

1. **Path-parameter style** (older, used by aggregates, snapshots, last trade/quote):
   ```
   GET /v2/aggs/ticker/{ticker}/range/{multiplier}/{timespan}/{from}/{to}
   ```

2. **Query-string + filter-operator style** (newer, used by fundamentals, filings, corporate actions, ratios):
   ```
   GET /stocks/financials/v1/income-statements?tickers=MU&timeframe=quarterly&limit=8
   ```

### Filter operator grammar (query-string style)
For newer query-string endpoints, the endpoint docs list supported modifiers per field. Common modifiers include:

| Suffix      | Meaning                                          |
|-------------|--------------------------------------------------|
| (none)      | exact equality                                   |
| `.any_of`   | comma-separated list — match any                 |
| `.all_of`   | comma-separated list — array field must contain all |
| `.gt`       | greater than                                     |
| `.gte`      | greater than or equal                            |
| `.lt`       | less than                                        |
| `.lte`      | less than or equal                               |

Example: get all quarterly income statements for MU between 2022 and 2024:
```
?tickers=MU&timeframe=quarterly&period_end.gte=2022-01-01&period_end.lte=2024-12-31
```

### Pagination
Responses include `next_url` when more data exists. Always loop on `next_url` to materialize complete datasets. The cursor is opaque — pass it back unchanged with the same auth header.

Heads up: a `next_url` returned during the transition period may point at either `api.massive.com` or `api.polygon.io`. Both work. Don't rewrite the cursor.

### Standard response envelope
```json
{
  "status": "OK",
  "request_id": "...",
  "results": [ ... ],
  "next_url": "https://api.massive.com/...?cursor=..."
}
```
Aggregates additionally return `queryCount`, `resultsCount`, `adjusted`, and `ticker`.

---

## 2. Reusable Python Client (rebrand-aware)

Use this as the foundation for every Massive query. It handles auth, retries, pagination, rate-limit backoff, **and accepts either env var name**.

```python
import os
import time
import requests
from typing import Iterator, Optional

# Default to the new domain. Override via env if a customer is pinning to legacy.
DEFAULT_BASE_URL = os.environ.get("MASSIVE_BASE_URL", "https://api.massive.com")


def _resolve_api_key(explicit: Optional[str]) -> str:
    """Accept either the new or legacy env var name."""
    if explicit:
        return explicit
    for var in ("MASSIVE_API_KEY", "POLYGON_API_KEY"):
        if os.environ.get(var):
            return os.environ[var]
    raise RuntimeError(
        "No API key found. Set MASSIVE_API_KEY (preferred) or POLYGON_API_KEY."
    )


class MassiveClient:
    """Thin wrapper around the Massive REST API (formerly Polygon.io)."""

    def __init__(
        self,
        api_key: Optional[str] = None,
        base_url: str = DEFAULT_BASE_URL,
        timeout: int = 30,
    ):
        self.api_key = _resolve_api_key(api_key)
        self.base_url = base_url.rstrip("/")
        self.timeout = timeout
        self.session = requests.Session()
        self.session.headers.update({
            "Authorization": f"Bearer {self.api_key}",
            "Accept": "application/json",
        })

    def get(self, path: str, params: Optional[dict] = None) -> dict:
        """Single GET. `path` may be a relative path or an absolute next_url
        (which during the transition period may point at api.polygon.io —
        that's fine, both domains work)."""
        url = path if path.startswith("http") else f"{self.base_url}{path}"
        for attempt in range(5):
            r = self.session.get(url, params=params, timeout=self.timeout)
            if r.status_code == 429:                       # rate limited
                time.sleep(2 ** attempt)
                continue
            r.raise_for_status()
            return r.json()
        r.raise_for_status()

    def paginate(self, path: str, params: Optional[dict] = None) -> Iterator[dict]:
        """Yield every result row across all pages."""
        page = self.get(path, params=params)
        for row in page.get("results", []):
            yield row
        while page.get("next_url"):
            page = self.get(page["next_url"])              # cursor is in the URL
            for row in page.get("results", []):
                yield row


# Backward-compat alias for code or examples that still say "Polygon"
PolygonClient = MassiveClient
```

### Usage pattern
```python
mc = MassiveClient()

# Path-style: 8 quarters of daily bars for MU
bars = mc.get("/v2/aggs/ticker/MU/range/1/day/2023-01-01/2024-12-31",
              params={"adjusted": "true", "sort": "asc", "limit": 50000})

# Query-string style with filter operators: last 8 quarters of income statements
rows = list(mc.paginate(
    "/stocks/financials/v1/income-statements",
    params={
        "tickers": "MU",
        "timeframe": "quarterly",
        "sort": "period_end.desc",
        "limit": 8,
    },
))
```

### Official SDK
For new SDK examples, use the maintained Massive Python package:
```python
from massive import RESTClient
client = RESTClient(
    api_key=os.environ.get("MASSIVE_API_KEY") or os.environ["POLYGON_API_KEY"]
)
```

Legacy projects may still use:
```python
from polygon import RESTClient
```
Do not rewrite that import unless the user is intentionally migrating SDK packages.

---

## 3. Use-Case → Endpoint Map

The agent's job is to translate an investment question into one or more endpoints, then assemble a clean answer. Use this table as the lookup. Paths are current as of the latest checked `llms-full.txt` export; re-check the docs when in doubt.

### Fundamentals & valuation
| Question                                | Endpoint                                                        |
|-----------------------------------------|------------------------------------------------------------------|
| Income statement (revenue, EPS, EBITDA) | `/stocks/financials/v1/income-statements`                       |
| Balance sheet (debt, cash, equity)      | `/stocks/financials/v1/balance-sheets`                          |
| Cash flow (FCF, capex)                  | `/stocks/financials/v1/cash-flow-statements`                    |
| Valuation/profitability ratios          | `/stocks/financials/v1/ratios`                                  |
| Free float                              | `/stocks/vX/float`                                              |

### Pricing, technicals & snapshots
| Question                              | Endpoint                                                        |
|---------------------------------------|------------------------------------------------------------------|
| Custom OHLC bars                      | `/v2/aggs/ticker/{ticker}/range/{mult}/{timespan}/{from}/{to}`   |
| Previous-day bar                      | `/v2/aggs/ticker/{ticker}/prev`                                 |
| Daily ticker summary                  | `/v1/open-close/{ticker}/{date}`                                |
| Single-ticker snapshot                | `/v2/snapshot/locale/us/markets/stocks/tickers/{ticker}`        |
| Top movers                            | `/v2/snapshot/locale/us/markets/stocks/{direction}` (gainers/losers) |
| Last trade / last quote               | `/v2/last/trade/{ticker}` · `/v2/last/nbbo/{ticker}`            |
| SMA / EMA / RSI / MACD                | `/v1/indicators/{sma|ema|rsi|macd}/{ticker}`                    |

### Ownership, insiders, short interest
| Question                              | Endpoint                                                        |
|---------------------------------------|------------------------------------------------------------------|
| Institutional holdings (13-F)         | `/stocks/filings/vX/13-F`                                       |
| Insider initial-ownership (Form 3)    | `/stocks/filings/vX/form-3`                                     |
| Insider transactions (Form 4)         | `/stocks/filings/vX/form-4`                                     |
| 10-K narrative (Business, Risk)       | `/stocks/filings/10-K/vX/sections`                              |
| 8-K item text                         | `/stocks/filings/8-K/vX/text`                                   |
| Standardized risk factors             | `/stocks/filings/vX/risk-factors`                               |
| Short interest (bi-weekly FINRA)      | `/stocks/v1/short-interest`                                     |
| Daily short volume                    | `/stocks/v1/short-volume`                                       |

### Corporate actions & events
| Question                              | Endpoint                                                        |
|---------------------------------------|------------------------------------------------------------------|
| Dividends                             | `/stocks/v1/dividends` (`/v3/reference/dividends` is deprecated) |
| Splits                                | `/stocks/v1/splits` (`/v3/reference/splits` is deprecated)      |
| IPOs                                  | `/vX/reference/ipos`                                            |
| Ticker timeline events                | `/vX/reference/tickers/{id}/events`                             |
| Corporate events (earnings/conf/etc.) | `/tmx/v1/corporate-events` (Wall Street Horizon/TMX partner)    |

### Analyst & news (Benzinga partner)
| Question                              | Endpoint                                                        |
|---------------------------------------|------------------------------------------------------------------|
| Individual analyst ratings            | `/benzinga/v1/ratings`                                          |
| Consensus rating + target             | `/benzinga/v1/consensus-ratings/{ticker}`                       |
| Bull/bear case summaries              | `/benzinga/v1/bulls-bears-say`                                  |
| Corporate guidance                    | `/benzinga/v1/guidance`                                         |
| Earnings (history + upcoming)         | `/benzinga/v1/earnings`                                         |
| Real-time Benzinga news               | `/benzinga/v2/news`                                             |
| General Massive news (with sentiment) | `/v2/reference/news`                                            |

### Options
| Question                              | Endpoint                                                        |
|---------------------------------------|------------------------------------------------------------------|
| Full option chain snapshot            | `/v3/snapshot/options/{underlying}`                             |
| Single contract snapshot              | `/v3/snapshot/options/{underlying}/{contract}`                  |
| All contracts (active + expired)      | `/v3/reference/options/contracts`                               |
| Contract OHLC bars                    | `/v2/aggs/ticker/O:{contract}/range/{mult}/{timespan}/{from}/{to}` |

### ETFs (ETF Global partner)
| Question                              | Endpoint                                                        |
|---------------------------------------|------------------------------------------------------------------|
| Holdings / constituents               | `/etf-global/v1/constituents`                                   |
| Fund flows                            | `/etf-global/v1/fund-flows`                                     |
| Sector exposure / profiles            | `/etf-global/v1/profiles`                                       |
| Analytics (risk, performance)         | `/etf-global/v1/analytics`                                      |

### Macro
| Question                              | Endpoint                                                        |
|---------------------------------------|------------------------------------------------------------------|
| Realized inflation (CPI, PCE)         | `/fed/v1/inflation`                                             |
| Inflation expectations                | `/fed/v1/inflation-expectations`                                |
| Labor market (unemployment, JOLTS)    | `/fed/v1/labor-market`                                          |
| Treasury yields (curve)               | `/fed/v1/treasury-yields`                                       |

### Reference
| Question                              | Endpoint                                                        |
|---------------------------------------|------------------------------------------------------------------|
| All tickers (universe)                | `/v3/reference/tickers`                                         |
| Single ticker overview                | `/v3/reference/tickers/{ticker}`                                |
| Related tickers (peer set)            | `/v1/related-companies/{ticker}`                                |
| Ticker types                          | `/v3/reference/tickers/types`                                   |
| Exchanges                             | `/v3/reference/exchanges`                                       |
| Market status / holidays              | `/v1/marketstatus/now` · `/v1/marketstatus/upcoming`            |

---

## 4. Worked Examples

These are the canonical patterns the agent should adapt. Each is self-contained and uses the rebrand-aware client from §2.

### 4.1 Fundamentals snapshot — last 8 quarters
```python
import pandas as pd

mc = MassiveClient()
rows = list(mc.paginate(
    "/stocks/financials/v1/income-statements",
    params={"tickers": "MU", "timeframe": "quarterly",
            "sort": "period_end.desc", "limit": 8},
))
df = pd.DataFrame(rows)[
    ["period_end", "fiscal_year", "fiscal_quarter",
     "revenue", "gross_profit", "operating_income",
     "ebitda", "diluted_earnings_per_share"]
]
df["gross_margin"] = df["gross_profit"] / df["revenue"]
df["op_margin"] = df["operating_income"] / df["revenue"]
df["yoy_revenue"] = df["revenue"].pct_change(periods=-4)  # rows are desc
print(df)
```

### 4.2 Five years of daily bars
```python
bars = mc.get(
    "/v2/aggs/ticker/MU/range/1/day/2020-01-01/2024-12-31",
    params={"adjusted": "true", "sort": "asc", "limit": 50000},
)["results"]

px = pd.DataFrame(bars).rename(columns={
    "t": "ts_ms", "o": "open", "h": "high", "l": "low",
    "c": "close", "v": "volume", "vw": "vwap",
})
px["date"] = pd.to_datetime(px["ts_ms"], unit="ms")
px["ret_1d"] = px["close"].pct_change()
px["vol_30d"] = px["ret_1d"].rolling(30).std() * (252 ** 0.5)
```

### 4.3 Peer set via Related Tickers, then peer multiples
```python
peers = mc.get("/v1/related-companies/MU")["results"]
peer_tickers = [p["ticker"] for p in peers][:5]

ratios = list(mc.paginate(
    "/stocks/financials/v1/ratios",
    params={
        "ticker.any_of": ",".join(["MU"] + peer_tickers),
        "sort": "ticker.asc",
        "limit": 6,
    },
))
```

### 4.4 Insider activity (Form 4) over the last 12 months
```python
from datetime import date, timedelta

cutoff = (date.today() - timedelta(days=365)).isoformat()
form4 = list(mc.paginate(
    "/stocks/filings/vX/form-4",
    params={
        "tickers": "MU",
        "filing_date.gte": cutoff,
        "sort": "filing_date.desc",
        "limit": 1000,
    },
))
```

### 4.5 Options chain — implied move setup
```python
chain = mc.get("/v3/snapshot/options/MU")["results"]
# Filter to next two expiries and 25-delta strikes for skew
front = sorted({c["details"]["expiration_date"] for c in chain})[:2]
near = [c for c in chain if c["details"]["expiration_date"] in front]
```

### 4.6 Analyst consensus
```python
cons = mc.get("/benzinga/v1/consensus-ratings/MU")
ratings = list(mc.paginate(
    "/benzinga/v1/ratings",
    params={"ticker": "MU", "sort": "date.desc", "limit": 200},
))
```

### 4.7 Macro context — treasury curve today
```python
yields = mc.get("/fed/v1/treasury-yields",
                params={"date.gte": "2024-01-01", "sort": "date.desc"})
```

---

## 5. Operating Principles for the Agent

When a customer asks a research question, follow this loop:

1. **Decompose.** Break the question into the underlying data needs (e.g., "is MU cheap?" → fundamentals + ratios + peers + price history + analyst targets).
2. **Map.** For each need, pick the endpoint from §3. Prefer the most specific endpoint over the most general.
3. **Construct.** Build the request using the right URL style (§1) and the filter operator grammar where applicable.
4. **Paginate.** Always use `paginate()` for any list endpoint that could exceed `limit`.
5. **Normalize.** Convert results into pandas DataFrames immediately — most downstream analysis is tabular.
6. **Cite.** When responding to the user, list every endpoint and every key parameter used so the work is reproducible.
7. **Fail loud, fail clear.** If an endpoint returns `status != "OK"` or a 4xx, surface the error verbatim — don't silently fall back to memory or guess.
8. **Never fabricate data.** If Massive doesn't return it, say so. Do not synthesize fundamentals, ratings, or prices from training data.
9. **Don't get tripped up by the rebrand.** "Polygon" and "Massive" are the same product. If the customer pastes Polygon-era code, fix it only if it's actually broken; the API contract is unchanged.

---

## 6. Common Pitfalls

- **Wrong URL style.** Aggregates use path parameters; fundamentals and filings use query-string filters. Mixing them returns 404s.
- **Forgetting `.any_of`** for multi-ticker calls. Plain comma lists may not parse on every endpoint. Use the exact documented field, e.g. `tickers.any_of=A,B,C` for array-valued financial/filing fields and `ticker.any_of=A,B,C` for singular ticker fields.
- **Date formats.** Path-style aggregates accept `YYYY-MM-DD` or millisecond Unix timestamps. Filter-operator endpoints require strict `YYYY-MM-DD`.
- **Adjusted vs. unadjusted.** Default for aggregates is `adjusted=true`. For backtests on absolute price levels, set `adjusted=false` deliberately.
- **Time zones.** Stock & options aggregates are ET, futures are CT, crypto is UTC. Don't compare timestamps blindly across asset classes.
- **`limit` defaults.** Most endpoints default to 100 (filings/fundamentals) or 5000 (aggregates). Always set `limit` explicitly when completeness matters and rely on `paginate()` for the rest.
- **Partner endpoints may require entitlement.** Benzinga, ETF Global, and Wall Street Horizon (TMX corporate events) live behind partner add-ons. A 403 on these means the customer's plan doesn't include them — surface that clearly.
- **OHLC field shorthand.** Aggregates use single-letter keys: `o, h, l, c, v, vw, t, n`. Rename them on ingest to keep downstream code readable.
- **Rebrand-specific gotchas:**
  - A `next_url` cursor mid-pagination may point at `api.polygon.io`. Don't rewrite it — both domains route to the same backend.
  - The customer's CI/CD or `.env` file likely still has `POLYGON_API_KEY`. The Python client in §2 reads either name; don't ask the customer to rename their secrets.
  - Tutorials, blog posts, and Stack Overflow answers will reference "Polygon" for the foreseeable future. They're still valid — just mentally substitute "Massive."
  - Legacy Python code may still import `RESTClient` from `polygon`. That can be valid compatibility-era code, but new examples should use `from massive import RESTClient`.

---

## 7. When the Catalog Isn't Enough

If the agent isn't sure an endpoint exists or which parameters it accepts:

1. Re-fetch `https://massive.com/docs/llms.txt` for the documentation index or `https://massive.com/docs/rest/llms-full.txt` for the full REST export. (`https://polygon.io/docs/...` may also resolve during the transition; prefer the massive.com URL.)
2. Open the specific endpoint page (each entry in `llms.txt` links to a `.md` doc with full parameters and a sample response).
3. If still ambiguous, make a small probing request with `limit=1` to inspect the response shape before building the full query.

Never invent an endpoint. If Massive doesn't document it, it doesn't exist.

---

## 8. Output Standards for Research Deliverables

When responding to the customer:

- Lead with the answer in plain English. Tables and code come after.
- Show every endpoint and every key parameter used (so the customer can audit or rerun).
- Quantify every claim with a number from the API. Round sensibly: prices to 2dp, ratios to 1dp, percentages to 1dp.
- Flag anything missing or stale (e.g., "13-F data is current through Q3 filings; Q4 not yet reported").
- Never quote sources verbatim beyond a short phrase — paraphrase analyst views and news in your own words.
- For multi-step research (memos, scenario models), structure the output as: thesis → evidence → risks → tracking signals.
- If the customer pastes Polygon-era code or docs, just use them. Don't lecture them about the rebrand unless they ask.
