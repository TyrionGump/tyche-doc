# Tyche Lens — Documentation

Personal investment-information and US-equity market-data tool. **Tyche Lens is a learning project** — a way to practice software engineering while learning investing and market-data concepts. It is **not** a trading system, a high-frequency trading platform, or a financial-advisory product, and it gives no buy/sell/hold advice.

> **Status:** early planning / exploration. Everything here is provisional and will change.

## What it does (intended)

- Show US stock latest/last price and historical price charts.
- Show company fundamentals (revenue, net income, EPS, free cash flow, statements).
- Compute valuation metrics — PE, PS, P/FCF — from latest price and TTM fundamentals.
- Offer a customizable dashboard and a watchlist with compare.
- Pull data through replaceable **provider adapters**, computing results **on request** with short-lived caching instead of storing large historical datasets.

## Documentation map

| Area | Contents |
|---|---|
| [Overview](overview/) | [Vision & goals](overview/vision-and-goals.md) · [Glossary](overview/glossary.md) |
| [Product](product/) | [Requirements](product/requirements.md) · [UI design directions](product/ui-design-directions.md) |
| [Architecture](architecture/) | [System design](architecture/system-design.md) · [Domain models](architecture/domain-models.md) · [Data providers](architecture/data-providers.md) |
| [Research](research/) | [API providers](research/api-providers.md) · [Valuation & metrics](research/valuation-and-metrics.md) |
| [Decisions](decisions/) | Architecture Decision Records (ADRs) |
| [Roadmap](roadmap.md) | Phases / milestones |

## Project process

Run with a light, deliberate process — partly as a project-management practice ground:

- [CONTRIBUTING.md](CONTRIBUTING.md) — conventions, decision process, planning & tracking, definition of done
- [CHANGELOG.md](CHANGELOG.md) — notable changes over time
- [Decisions (ADRs)](decisions/) — significant choices and their rationale

## About the name

**Tyche** — the Greek goddess of fortune and chance — reflects the role of uncertainty in investing. **Lens** reflects the goal of *observing and understanding* the market rather than pretending to predict it.

## Repository notes

- These docs are edited in [Obsidian](https://obsidian.md) but written as plain **GitHub-flavored Markdown** with relative links, so they render anywhere.

## License

Documentation in this repository is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE).
© 2026 tyriongump. You are free to share and adapt the material with attribution.
