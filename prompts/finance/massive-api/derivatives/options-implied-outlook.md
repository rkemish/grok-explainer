# Options-Implied Outlook

Use this template to read the options market for implied volatility, direction, and earnings expectations.

## Analysis Type

Derivatives and market-implied analysis.

## Goal

Use the options market as a forward-looking signal to confirm or challenge the equity thesis.

## Input

Analyze `{TICKER}` using the Massive API.

## Prompt

```text
From the Massive API options endpoints, get {TICKER}'s current IV term structure, IV rank
and percentile, 25-delta put/call skew, open-interest concentration by strike for the next
two expirations, and the options-implied move for the next earnings date. Translate this
into plain English: what is the options market pricing in vs. the stock's recent realized
behavior?
```

## Output Requirements

- Include IV term structure.
- Show IV rank and percentile.
- Include 25-delta put/call skew.
- Show open-interest concentration by strike for the next two expirations.
- Calculate options-implied move for the next earnings date.
- Compare implied behavior against recent realized behavior.
