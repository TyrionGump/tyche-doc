# Domain Models

> **Status:** draft — illustrative sketches; language not finalized.

Internal, provider-independent types. Provider responses are normalized into these before anything else uses them, so the rest of the system never depends on a specific API's JSON shape.

The sketches below use Java `record` syntax purely for illustration:

```java
record DailyPrice(
    String symbol,
    LocalDate date,
    BigDecimal open,
    BigDecimal high,
    BigDecimal low,
    BigDecimal close,
    BigDecimal volume
) {}

record TtmFundamentals(
    String symbol,
    LocalDate periodEnd,
    BigDecimal dilutedEps,
    BigDecimal revenue,
    BigDecimal netIncome,
    BigDecimal freeCashFlow
) {}

record Valuation(
    String symbol,
    BigDecimal latestPrice,
    BigDecimal peTtm,
    BigDecimal psTtm,
    BigDecimal pfcfTtm
) {}
```

## Notes

- Use `BigDecimal` (or an equivalent exact type) for monetary values to avoid floating-point error.
- Prefer **diluted** EPS for valuation (more conservative). See [Valuation & metrics](../research/valuation-and-metrics.md).
- Keep these models free of provider-specific fields; mapping happens in the [provider adapters](data-providers.md).
