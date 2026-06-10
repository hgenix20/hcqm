# Changelog

All notable changes to the HCQM project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to semantic versioning principles adapted for research artifacts.

---

## [0.8] — 2026-06-09

Reviewer-revised draft. All external reviewer feedback integrated. Pre-publication review pass complete. This version is complete pending one acknowledgment confirmation (Hernández-Orallo) and an arXiv endorser. v1.0 will follow once those are resolved.

### Added
- `whitepaper/HCQM_v0.8.md` — full reviewed draft (all reviewer revisions integrated; pre-publication review pass applied)
- §2.11.6 Hernández-Orallo and Vold (2019) cognitive-ability catalogue comparison with full gradient-match table (12/14 abilities covered at partial-or-better)
- Appendix I: standalone gradient-match for the Hernández-Orallo and Vold catalogue (parity with Appendices D, E, G, H); Version Notes shifted to Appendix J
- §5.2 reliability-and-autonomy layer — HCQM's AI-facing contribution mapping motivational, metacognitive, and adaptive capacities to long-horizon agent reliability, with a worked failure-pattern example
- Zhou et al. (2026) *Nature* citation (ADeLe evaluation line extension, DOI: 10.1038/s41586-026-10303-2)
- Wray, Kirk, and Laird (2025) added (cognitive design patterns for LLM agents)
- `docs/related-work.md` — structured living document of related literature organized by domain
- `docs/positioning.md` — explicit comparison table and value-claim document vs. adjacent frameworks
- `CONTRIBUTING.md` — contribution guidelines, versioning policy, review standards
- `.github/ISSUE_TEMPLATE/` — five structured issue templates (construct refinement, citation correction, comparative analysis, general issue, config)
- Updated Figure 1 (`whitepaper/HCQM.png`): 33 capabilities including new 1.7 Retrieval Fluency under Domain 1
- Updated Figure 2 (`whitepaper/HCQM-comparison.png`): five-framework coverage comparison adding Hernández-Orallo and Vold (2019) catalogue as fifth column

### Changed
- **Construct count: 32 → 33** — Domain 1 adds 1.7 Retrieval Fluency (Gr), per McGrew review. All count references updated throughout.
- **CHC terminology corrected** throughout to Schneider and McGrew (2018): Gsm → Gwm (Short-Term Working Memory); Glr officially split into Gl (Learning Efficiency) and Gr (Retrieval Fluency)
- **Domain 3 EQ framing**: now attributed to CHC Gei (Schneider & McGrew, 2018, pp. 87–88) as alignment with contemporary CHC, not extension beyond it. Appendix F updated with Gei row.
- **Domain 6 framing**: now corresponds to CHC Gl (Learning Efficiency), not extension beyond Glr
- **Domain 4 relationship to CHC**: extension framing with Carroll (1993) historical note (tentative narrow creativity abilities dropped from contemporary CHC)
- **Domain 5 AQ claim**: unique-coverage observation scoped explicitly to five AI frameworks; CAMML SENNA SEMS overlap acknowledged; not a claim against the human-capability tradition
- **CMC as primary classical comparator** (Laird, Lebiere, & Rosenbloom, 2017) replacing parallel ACT-R + Soar listing; Soar description corrected to module-decomposition level
- **§2.11 differentiation sharpened**: reliability-and-autonomy layer elevated as sharpest AI-facing contribution; AQ demoted to illustration of asymmetry
- **§2.12 synthesis reframed**: contribution 2 now "coverage asymmetry" (not "inclusion of non-cognitive dimensions"); AQ observation non-load-bearing
- **IQ-as-composite grounding** strengthened with McGrew et al. (2023) emergent-property references
- **Working memory definition**: adds "temporarily" and attentional-control clause (Engle, 2002; McGrew et al., 2023)
- **Gf indicator**: "quickly" → "fluently" (McGrew suggestion)
- **Acknowledgments**: Dr. Kevin McGrew (named) + two anonymous reviewers
- **Pre-publication review**: em-dash purge (body prose), US English consistency, AI-tell vocabulary scan, doubled-word check, version-label cleanup (all "v1.0 refinement" references → "future work"), construct-count consistency, reviewer de-anonymization removed from body and references
- Four agent-failure citations verified against primary sources; [VERIFY] flags removed; arXiv IDs added
- Reference list markdown style normalized (uniform *italic* + bare URL throughout)
- `ROADMAP.md` updated to v0.8 state

### Removed
- `docs/deepmind-hcqm-comparison.md` — superseded by the more rigorous Appendix D of the whitepaper
- `docs/reading-list.md` — superseded by `docs/related-work.md`

---

## [0.6] — 2026-05-22

First public release since v0.1. External-review public draft.

v0.2–v0.5 were internal working drafts not publicly released. v0.6 is the first
publicly released draft since v0.1 and is intentionally labeled below v1.0 because
external review has not yet been integrated. v1.0 will follow after reviewer
feedback is triaged and applied.

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

---

## [0.1] — 2026-04-14

Initial public release. Priority anchor for intellectual timestamp.

### Added
- `HCQM-v0.1.md` — original HCQM framework tree (8 domains, 32 constructs)
- `README.md`, `LICENSE` (CC BY 4.0), `CITATION.cff`, `.gitignore`, `CHANGELOG.md`
- Repository made public and tagged `v0.1`
- Zenodo archive (DOI: 10.5281/zenodo.19587600)
