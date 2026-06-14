# Roadmap

> **Status:** stub — to be fleshed out. Phases are indicative, not committed.

## Phase 0 — Foundations
- Decide language / stack.
- Define [domain models](architecture/domain-models.md) and [provider interfaces](architecture/data-providers.md).
- Wire one provider (FMP) end-to-end for a single symbol.

## Phase 1 — MVP
- Company page: latest price + basic fundamentals + computed PE.
- Watchlist (symbols + a few stat columns).
- Short-lived caching per [system design](architecture/system-design.md).

## Phase 2 — Breadth
- Historical price charts; add PS and P/FCF.
- Finnhub fallback for quotes / profile / news.
- Pick a [UI direction](product/ui-design-directions.md) and build the dashboard.

## Later / maybe
- SEC EDGAR as official fundamentals source.
- Intraday experiments (Twelve Data / Alpha Vantage).
- Macro data (FRED).

_Nothing here is a commitment; this is a learning project and scope will shift._
