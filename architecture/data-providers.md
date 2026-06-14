# Data Providers

> **Status:** draft.

External data comes through **replaceable adapters** behind internal interfaces, so providers can be swapped without touching the rest of the app. See the provider research in [API providers](../research/api-providers.md).

## Roles

| Role | Responsibility | Candidate providers |
|---|---|---|
| Latest price | Last / near-real-time quote | Alpaca, Finnhub |
| Daily / historical price | EOD bars | FMP, Stooq (CSV backup) |
| Intraday price (experimental) | 1m / 5m bars | Twelve Data, Alpha Vantage |
| Fundamentals | Statements, EPS, ratios | FMP, SEC EDGAR (official) |
| Filings | Official filings / XBRL facts | SEC EDGAR |
| Macro (optional) | CPI, GDP, rates | FRED |

## Interface sketch

```java
public interface PriceDataProvider {
    Optional<Quote> getLatestQuote(String symbol);

    List<PriceBar> getHistoricalBars(
        String symbol,
        BarInterval interval,
        LocalDate startDate,
        LocalDate endDate
    );
}
```

Concrete adapters implement this per source, e.g. `FmpPriceDataProvider`, `FinnhubPriceDataProvider`, `StooqCsvPriceProvider`.

## Naming honesty

Name adapters for what they really are. Stooq exposes downloadable CSV URLs, **not** a committed API — so `StooqCsvPriceProvider` is more honest than `StooqApiClient`. See [API providers → Stooq](../research/api-providers.md#stooq).

## Design rules

- One interface per role; many implementations.
- Adapters map provider JSON → [domain models](domain-models.md); callers see only domain models.
- Treat free tiers' rate limits and delays as first-class constraints, and document them per provider.
