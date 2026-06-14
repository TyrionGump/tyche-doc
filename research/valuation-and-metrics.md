# Valuation & Metrics

> **Status:** draft. Educational notes — not investment advice.

Tyche Lens computes valuation metrics locally from latest price and TTM fundamentals, so the inputs and assumptions are transparent.

## PE (Price-to-Earnings)

```text
PE = Price / EPS
```

Example: price `200`, TTM diluted EPS `6.5` → `PE = 200 / 6.5 ≈ 30.77`.

Because price moves continuously but EPS updates only on quarterly / annual results, the practical "current" PE is:

```text
Current PE = Latest Price / TTM Diluted EPS
```

So: price updates frequently, EPS updates quarterly, and PE changes whenever price changes.

## Other ratios

- **PS** = Price / Sales per share, or Market Cap / Revenue.
- **P/FCF** = Price / Free Cash Flow per share, or Market Cap / FCF.

## Caveats

- Prefer **TTM PE** over **forward PE** — forward PE relies on analyst estimates, not official filings.
- Prefer **diluted EPS** over basic EPS (more conservative).
- If EPS is negative, PE is usually not meaningful — show `N/A`.
- Avoid **look-ahead bias** in historical metrics: never use EPS that had not yet been reported at the historical date.
- Be explicit about data provenance: official filing vs provider-cleaned vs analyst estimate.

_Terms: see [Glossary](../overview/glossary.md). Data sources: see [API providers](api-providers.md)._
