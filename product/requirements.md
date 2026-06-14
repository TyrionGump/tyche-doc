# Requirements

> **Status:** draft — provisional scope. Tracked work lives in GitHub Issues / Milestones (see [CONTRIBUTING](../CONTRIBUTING.md)); high-level sequence is in [roadmap.md](../roadmap.md).

Requirements carry stable IDs so they can be referenced from issues, ADRs, and commits. `FR` = functional, `NFR` = non-functional. Each has a status: `proposed` / `accepted` / `done` / `dropped`.

## Functional requirements

### Dashboard
- **FR-1** — Customizable widget grid (user-arranged) with a configuration ("tweaks") panel. _proposed_
- **FR-2** — Top stat row: portfolio value, day change, totals. _proposed_
- **FR-3** — Primary price chart for a focused symbol. _proposed_
- **FR-4** — Embedded watchlist preview and allocation breakdown. _proposed_
- **FR-5** — News / latest-headlines panel. _proposed_

### Watchlist
- **FR-6** — Card "board" view and a compact matrix / table view. _proposed_
- **FR-7** — Multi-select compare across symbols. _proposed_
- **FR-8** — User-pickable stat columns. _proposed_

### Company page
- **FR-9** — Header with latest price and key identifiers. _proposed_
- **FR-10** — Tabbed sections with stat tiles for headline metrics. _proposed_
- **FR-11** — Price chart and small fundamentals charts. _proposed_
- **FR-12** — Financial-statements table across multiple periods. _proposed_
- **FR-13** — Customizable "blocks" layout and symbol search. _proposed_

### Valuation (cross-cutting)
- **FR-14** — Compute PE, PS, P/FCF from latest price + TTM fundamentals. See [valuation & metrics](../research/valuation-and-metrics.md). _proposed_
- **FR-15** — Label data provenance and staleness (real-time / delayed / EOD). _proposed_

## Non-functional requirements

- **NFR-1 — Cost** — prefer free / low-cost data tiers; run within free-tier limits where practical. _accepted_
- **NFR-2 — Storage** — avoid storing large historical datasets; compute-on-request with short-lived cache. See [ADR 0001](../decisions/0001-compute-on-request-and-short-cache.md). _accepted_
- **NFR-3 — Data freshness** — delayed / EOD data is acceptable; freshness expectations documented per data type. See [system design](../architecture/system-design.md). _accepted_
- **NFR-4 — Correctness** — valuation math transparent and reproducible; avoid look-ahead bias; prefer official, diluted figures. _accepted_
- **NFR-5 — Reliability** — degrade gracefully on provider errors / rate limits; use fallbacks where available. _proposed_
- **NFR-6 — Maintainability** — provider-specific code isolated behind adapters; UI depends only on internal models. See [data providers](../architecture/data-providers.md). _accepted_
- **NFR-7 — Replaceability** — data providers swappable without changing core logic. _accepted_
- **NFR-8 — Secrets** — API keys kept out of the repository and the client; never commit secrets. _accepted_

_The visual treatment for these features is explored in [UI design directions](ui-design-directions.md)._
