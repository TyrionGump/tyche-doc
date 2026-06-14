# Vision & Goals

> **Status:** draft — early planning.

## Purpose

Tyche Lens is a **personal learning project**. Its primary goal is to practice software engineering (APIs, data modeling, caching, backend/frontend design) while learning basic investing and market-data concepts. Producing a useful personal dashboard is a secondary, motivating outcome.

## Goals

- Display US stock latest price and historical price charts.
- Show company fundamentals and financial statements.
- Compute valuation metrics (PE, PS, P/FCF) transparently, from price and TTM fundamentals.
- Provide a customizable dashboard and a watchlist with side-by-side compare.
- Practice clean architecture: replaceable data-provider adapters, internal domain models kept separate from provider JSON, and compute-on-request with short-lived caching.
- Prefer free or low-cost data sources.

## Non-goals

- ❌ Not a trading or order-execution system.
- ❌ Not a high-frequency / real-time tick system. Delayed and end-of-day data are acceptable.
- ❌ Not a financial-advisory product — **no buy/sell/hold recommendations**.
- ❌ Not a data warehouse — avoid storing large historical datasets where compute-on-request will do.

## Audience & author context

Built by a software engineer who is an **investing beginner**. Documentation should explain financial concepts plainly and flag data caveats (real-time vs delayed, raw vs adjusted, official filing vs analyst estimate, look-ahead bias).

## Guiding principles

- Prefer simple, boring, maintainable solutions over premature optimization.
- Be explicit about data provenance, staleness, and provider limitations.
- Keep provider-specific details at the edges; keep the core in clean internal models.

_See also: [System design](../architecture/system-design.md) · [Roadmap](../roadmap.md)._
