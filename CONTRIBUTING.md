# Contributing & Ways of Working

This is a solo learning project, but it is run with a light, deliberate process on purpose — practicing project design and management is one of its goals. This document describes how the project is organized and how changes are made.

## Repository layout

- `overview/` — vision, goals, glossary
- `product/` — requirements and UI design directions
- `architecture/` — system design, domain models, data-provider interfaces
- `research/` — provider comparisons and valuation notes
- `decisions/` — Architecture Decision Records (ADRs)
- `roadmap.md` — phases / milestones · `CHANGELOG.md` — notable changes

## Documentation conventions

- Plain GitHub-flavored Markdown; **relative links** between docs (works on GitHub and in Obsidian).
- Each substantive doc opens with a one-line `> **Status:**` note (draft / stable).
- Requirements carry stable IDs (`FR-n`, `NFR-n`) so issues, ADRs, and commits can reference them.
- Keep volatile or provider-specific facts in `research/`, and mark them as subject to change.

## Decisions (ADRs)

- Record any significant or hard-to-reverse choice as an ADR in `decisions/`.
- Copy [`decisions/_template.md`](decisions/_template.md), increment the number, and add a row to [`decisions/README.md`](decisions/README.md).
- Do not rewrite an accepted ADR — supersede it with a new one.

## Planning & tracking

- **GitHub Issues** — one per task / bug / idea; label by area (`overview`, `product`, `architecture`, `research`).
- **Milestones** — map to the phases in [`roadmap.md`](roadmap.md).
- **Project board** (optional) — Todo / In progress / Done.
- The roadmap captures high-level intent; Issues and Milestones are the live tracking.

## Branching & commits

- Work on short-lived branches; open a PR into `main` (even solo — it creates a reviewable record).
- Write clear, imperative commit messages; reference requirement or issue IDs where relevant (e.g. `FR-14`, `#12`).

## Definition of Done

- The change is consistent with the relevant requirements and ADRs.
- Internal links resolve and status notes are updated.
- `CHANGELOG.md` is updated under **[Unreleased]** for notable changes.
