Perform a Comprehensive Fundamental Ratio Analysis + Historical/Peer Benchmarking for the US public stock with ticker [TICKER].
Use your code_execution tool with the Massive RESTClient as the primary source for the most current fundamentals (TTM and annual/quarterly statements), key ratios, historical financials (5-10 years where available), dividends, and any available peer data. Supplement with web_search or browse_page only when needed for sector averages, additional peer benchmarks, or latest context from reliable sources (e.g., company filings, industry reports).
Focus exclusively on insights useful for value investors (Graham/Buffett style): emphasis on margin of safety, normalized earnings power, financial strength, and long-term compounding potential.
Required output structure (follow exactly):
1. Executive Summary
One-paragraph overview of the company’s current valuation attractiveness, key strengths/weaknesses, and whether it currently offers a compelling margin of safety for value investors.
2. Company Snapshot

Full company name, sector, industry, current share price, market cap, and enterprise value (as of latest data).
One-sentence description of core business.

3. Valuation Ratios (Current + Historical Trends)
Present in a clean markdown table with columns:
Metric | TTM / Latest | 5-Year Average | 5-Year Range (High/Low) | 10-Year Average (if available) | Current vs Historical Assessment
Include at minimum:

Trailing P/E
Forward P/E (if available)
Price-to-Book (P/B)
Price-to-Sales (P/S)
EV/EBITDA
EV/FCF
Free Cash Flow Yield (%)
PEG Ratio (if available)

Add a short commentary on trends and any signs of undervaluation (e.g., P/E or EV/EBITDA well below historical median + strong ROIC).
4. Profitability & Efficiency Metrics
Markdown table + trend analysis (TTM + 5-year view):

Gross Margin, Operating Margin, Net Margin
ROE, ROIC, ROA
Asset Turnover
Any relevant efficiency ratios

Clearly note whether margins and returns are improving, stable, or declining.
5. Growth & Cash-Flow Trends
Table showing:

Revenue growth (1Y, 3Y CAGR, 5Y CAGR)
EPS growth (1Y, 3Y CAGR, 5Y CAGR)
Free Cash Flow growth (1Y, 3Y CAGR, 5Y CAGR)

Commentary on growth quality and consistency.
6. Financial Health & Leverage
Table + assessment:

Current Ratio & Quick Ratio
Debt-to-Equity
Total Debt / EBITDA
Interest Coverage Ratio
Any other solvency metrics (e.g. Altman Z-score if relevant)

Highlight balance-sheet strength or red flags.
7. Peer & Sector Benchmarking

Identify 4–6 closest peers or major competitors in the same industry.
Provide a side-by-side comparison markdown table of the most important value metrics (P/E, EV/EBITDA, P/B, ROIC, FCF Yield, margins, Debt/Equity).
Include industry/sector average where available.
Clearly state whether [TICKER] is trading at a premium or discount to peers on key value metrics.

8. Value Investor Conclusion

Overall verdict: Undervalued / Fairly Valued / Overvalued relative to its own history and peers.
Estimated margin of safety (if any).
Top 3 strengths and top 3 potential risks/red flags for a value investor.
Any other notable observations from the latest financials.

9. Data Sources & Freshness
List the exact sources used (Massive API snapshots, specific web pages, etc.) and the date/time the data was pulled.
Use clean markdown tables throughout. Be objective, data-driven, and quantitative. Flag any limitations in data availability. Do not add generic filler text. Do not present the output as financial advice.
Ticker to analyze: [TICKER]
