# System Design

> **Status:** draft — direction, not final.

## Core principle: compute-on-request

Avoid storing large historical datasets. Instead, fetch what is needed when a user opens a symbol, normalize it into internal models, compute metrics on the fly, and cache results briefly. See [ADR 0001](../decisions/0001-compute-on-request-and-short-cache.md).

Typical request flow:

1. User opens a symbol (or watchlist).
2. A service requests data from the relevant **provider adapter** (price / fundamentals / filing).
3. The provider response is normalized into [internal domain models](domain-models.md).
4. Valuation metrics are computed on request.
5. The result is returned to the UI and cached for a short, data-appropriate period.

## Layering

- **Providers** — adapters over external APIs. See [Data providers](data-providers.md).
- **Domain models** — internal, provider-independent types. See [Domain models](domain-models.md).
- **Services** — orchestration and computation, e.g. `PriceService`, `FundamentalService`, `ValuationService`.
- **UI** — depends only on domain models / service results, never on provider-specific JSON.

> **Design rule:** the UI must never depend directly on provider-specific fields. Convert provider responses into internal models first.

## Caching strategy

Short-lived / rolling cache, tuned per data type:

| Data | Suggested cache |
|---|---|
| Latest quote | 5–30 seconds |
| Daily price data | 6–24 hours |
| Financial statements | 1–7 days |
| Company profile | 7–30 days |
| Computed valuation | ~1 day |

**Worth persisting:** watchlist symbols, symbol → CIK mapping, provider raw-response cache, latest-price rolling cache, recently computed valuations.

**Not worth persisting (initially):** all historical OHLCV, all SEC company facts, every valuation snapshot, every daily PE forever.

## Open questions

- Language / stack not finalized (the model sketches use Java records — see [Domain models](domain-models.md)).
- Where the cache lives (in-memory vs. a lightweight store).
