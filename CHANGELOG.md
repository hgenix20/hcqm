# Changelog

All notable changes to the HCQM project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to semantic versioning principles adapted for research artifacts.

---

## [0.6] — 2026-05-22

First public release since v0.1. External-review public draft.

v0.2–v0.5 were internal working drafts not publicly released. v0.6 is the first
publicly released draft since v0.1 and is intentionally labeled below v1.0 because
external review has not yet been integrated. v1.0 will follow after reviewer
feedback is triaged and applied (~mid-June 2026).

### Added
- HCQM whitepaper v0.6 (`whitepaper/HCQM_v0.6.md`) — full scholarly framework paper
  integrating 8 capability domains, 32 constructs, ~120 subcomponents, ~130 behavioral
  indicators, with per-domain theoretical grounding and dual-use (human + synthetic) framing
- Comparative analyses against four contemporary AI capability frameworks:
  CoALA (Sumers et al., 2024), DeepMind (Burnell et al., 2026),
  Hendrycks et al. (2025), OECD (2025) — Appendices D, E, G, H
- Figure 1: HCQM schematic across all 8 domains and 32 constructs (§3.1)
- Figure 2: cross-framework coverage comparison schematic (§2.11.7)
- §6.7 three-stage evaluation protocol sketch
- Appendices A–I: full hierarchical tree, indicator catalog, source mapping,
  gradient-match tables, CHC broad-ability mapping, version notes
- 62 references, all DOIs independently verified
- DeepMind vs HCQM comparative analysis (docs/deepmind-comparison.md)
- Literature review reading list organized by domain (docs/reading-list.md)
- Research thesis and positioning document (docs/thesis.md)

### Changed
- Construct count corrected to 32 (was inconsistently listed as 31 in v0.1)
- "Prescriptive" language scoped to "partially prescriptive at the capacity layer only"
- Adversity Quotient unique-coverage claim extended from 2-framework to
  4-framework intersection (DeepMind, CoALA, Hendrycks, OECD)
- All citations verified against primary sources; DOIs confirmed

---

## [0.1] — 2026-04-14

### Added
- Initial public release of HCQM working draft
- Eight-domain hierarchical capability taxonomy:
  1. General Cognitive Intelligence
  2. Executive / Self-Regulatory Intelligence
  3. Emotional & Social Intelligence
  4. Creative & Innovation Intelligence
  5. Motivational & Adaptive Intelligence
  6. Learning & Knowledge Intelligence
  7. Digital & Technological Intelligence
  8. Systems & Strategic Intelligence
- Subcomponents and indicators for each quotient within each domain
- Project README with thesis, roadmap, and positioning
- CC BY 4.0 license for framework documents
- Citation metadata (CITATION.cff)

### Status
- Pre-scholarly working draft
- Literature review in progress for v1.0
- Architecture whitepaper planned as follow-up publication

---

## Versioning notes

- **v0.x** — pre-scholarly working drafts, published for transparency
- **v1.0** — first formally scholared release with full literature review and citations
- **v1.x** — revisions based on community feedback
- **v2.x** — major structural updates (e.g., new domains, significant re-integration)
