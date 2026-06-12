# HCQM Roadmap

**Author:** Kameron M. Green
**Last updated:** 2026-06-12
**Status:** Living document
**Repository:** https://github.com/hgenix20/hcqm
**Zenodo DOI (v0.1):** 10.5281/zenodo.19587600
**Zenodo DOI (v0.6):** 10.5281/zenodo.20345943
**Publication path:** Whitepaper for v0.8/v1.0 (framework specification); peer-reviewed journal papers as follow-on empirical work in v2.0+.

---

## Current state (v1.0, 2026-06-12)

HCQM v1.0 is the publication release. All external reviewer feedback has been integrated. Acknowledgments confirmed: Dr. Kevin McGrew (Institute for Applied Psychometrics, named) + two anonymous reviewers. This is the clean arXiv-ready copy (internal scaffolding removed from v0.8).

v0.8 contains:

- 8 top-level domains, **33** constituent capabilities, ~120 subcomponents, ~130 behavioral indicators
- Per-domain theoretical grounding, human application, and synthetic-system application notes
- Comparative analyses against **five** contemporary AI capability frameworks: CoALA (Sumers et al., 2024), DeepMind 2026 (Burnell et al., 2026), Hendrycks et al. (2025), OECD (2025), and the Hernández-Orallo and Vold (2019) cognitive-ability catalogue (Tolan et al., 2021; Zhou et al., 2026)
- New §5.2 reliability-and-autonomy layer — HCQM's AI-facing contribution mapping motivational, metacognitive, and adaptive capacities to long-horizon agent reliability
- Full evaluation protocol sketch in §6.7 (three-stage structure; developmental capability-profiling framing)
- Figure 1: HCQM schematic across all 8 domains and 33 capabilities
- Figure 2: five-framework coverage comparison (CoALA, DeepMind, Hendrycks, OECD, ADeLe)
- Appendices A–I: full hierarchical tree, indicator catalog, source mapping, CHC broad-ability mapping, four gradient-match comparison tables, standalone ADeLe catalogue comparison
- 70+ references, all DOIs independently verified
- CHC terminology corrected to Schneider and McGrew (2018): Gsm → Gwm, Glr → Gl + Gr, Gei added
- Domain 3 EQ attributed to CHC Gei (alignment, not extension)
- Full pre-publication review pass: em-dashes removed, US English consistency, claim audit, version-label cleanup

---

## Version history

| Version | Date | Status | Notes |
|---|---|---|---|
| v0.1 | 2026-04-14 | Frozen — priority anchor | Zenodo DOI: 10.5281/zenodo.19587600 |
| v0.2–v0.5 | 2026-04–05 | Superseded | Internal working drafts |
| v0.6 | 2026-05-22 | Superseded | External-review public draft; Zenodo DOI: 10.5281/zenodo.20345943 |
| v0.7 | 2026-06-01 | Vault working draft | Reviewer revisions integrated (Laird, McGrew, Hernández-Orallo); not released to GitHub |
| v0.8 | 2026-06-09 | Superseded | All reviewer revisions; pre-publication review; 5th framework; retained for reference |
| **v1.0** | **2026-06-12** | **Current public release** | Clean publication copy; acknowledgments confirmed; internal scaffolding removed |

---

## v0.8 release (2026-06-09)

| Item | Status |
|---|---|
| HCQM_v0.8.md created in vault | Complete |
| All reviewer revisions integrated (McGrew, Laird, Hernández-Orallo) | Complete |
| Full pre-publication review and claim audit | Complete |
| Construct count corrected throughout: 32 → 33 | Complete |
| ADeLe catalogue comparison added (§2.11.6 + Appendix I) | Complete |
| Reliability-and-autonomy layer added (§5.2) | Complete |
| Four agent-failure citations verified (arXiv IDs confirmed) | Complete |
| Figure 1 regenerated (33 capabilities) | Complete |
| Figure 2 regenerated (5-framework comparison) | Complete |
| Reference list normalized; Zhou et al. (2026) *Nature* added | Complete |
| HCQM_v0.8.md synced to GitHub repo | Pending |
| CHANGELOG / CITATION.cff / README updated for v0.8 | Pending |
| GitHub tag `v0.8` pushed | Pending |
| Zenodo archive | Pending |
| v0.8 DOI propagated to CITATION.cff + ORCID | Pending |

---

## v1.0 milestones

v1.0 is gated on two items:

1. **Acknowledgment confirmation** from Hernández-Orallo (anonymous in v0.8 pending his response)
2. **arXiv endorser secured** (UNO faculty pathway + outreach to Hernández-Orallo and Laird)

| Item | Status |
|---|---|
| External review — McGrew | Complete (9 items applied to v0.7/v0.8) |
| External review — Laird | Complete (CMC framing, metacognition note) |
| External review — Hernández-Orallo | Complete (catalogue added; terminology corrected); acknowledgment TBD |
| Hernández-Orallo acknowledgment preference | Pending reply |
| arXiv endorser secured | Pending (Hernández-Orallo + Laird asked; UNO follow-up needed) |
| Update acknowledgments per Orallo reply | Pending |
| Final GitHub + Zenodo + arXiv submission | Pending above two items |

---

## v1.1 priorities (target: Q3 2026)

### Construct refinements

- Add **episodic memory** and **procedural memory** as explicit constructs (Domain 6 or Domain 1). Source: CoALA comparison (Appendix E); Hendrycks Long-Term Memory Storage decomposition (Appendix G).
- Add **cognitive resource allocation / reasoning budget control** as a subcomponent of 2.1 Metacognitive Intelligence. Source: CoALA §6.
- Add **modality bridging / embodied grounding** to address perception-to-symbol translation. Source: CoALA grounding actions; OECD inclusion of vision and manipulation (Appendix H).
- Add **hallucination / retrieval precision** as a subcomponent of 7.2 Information Literacy. Source: Hendrycks MR sub-faculty.
- Add **alexithymia** as a reverse-scored subcomponent of 3.1 Emotional Intelligence.
- Resolve the overlap between 1.6 Working Memory and 2.2 Cognitive Control indicators.
- Consider whether **morality/ethics** warrants a standalone construct or Domain 9.
- Reconsider whether **Memory, Perception, and Attention** should be promoted to standalone domains (§6.4).
- Annotate each capability with both **static capacity** and **dynamic process** facets.
- Substantive CAMML / Snow aptitude-complex integration in Domain 5 (McGrew soft suggestion).

### Evaluation protocol development

- Complete the capability-to-instrument mapping table for all 33 constructs (Stage 1 of §6.7 protocol).
- Pilot synthetic-administration adaptations on Domain 1 first, using Hendrycks battery adaptations.
- Develop radar-plot reporting template with at least one fully populated human + synthetic example.
- Construct preliminary self-report and informant-report instrument for pilot psychometric evaluation.

### Companion architecture document

- Begin specification of an HCQM-aligned cognitive architecture (per §6.6 and §6.9 item 7).

---

## v2.0 horizon (2027+)

- Full HCQM-aligned instrument battery with psychometric validation.
- Empirical study testing incremental predictive validity over individual source instruments.
- Cross-cultural validation (Domain 3.3 Cultural Intelligence; Domain 5 Motivational & Adaptive).
- Architecture case studies translating HCQM domains into concrete AI system specifications.
- Alignment studies with the DeepMind cognitive framework via the DeepMind/Kaggle hackathon benchmarks.

---

## Open dependencies

- arXiv endorser (required for arXiv submission; cs.AI; UNO + Hernández-Orallo + Laird pathway)
- Hernández-Orallo acknowledgment preference reply
- Personal domain for HCQM project landing page
- USPTO search and naming lock-in
- Vault-repo split decision

---

## Versioning policy

Versioned files are never overwritten; each new version is a new file. Priority claims anchor to v0.1 (Zenodo DOI: 10.5281/zenodo.19587600) regardless of which paper version is current.
