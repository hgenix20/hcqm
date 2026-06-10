# Contributing to HCQM

**Maintainer:** Kameron M. Green (ORCID: 0009-0002-8350-3641)
**Repository:** https://github.com/hgenix20/hcqm
**License:** CC BY 4.0 (documentation and framework content) / MIT (any code)

Thank you for your interest in HCQM. This document defines how external contributions are received, reviewed, and integrated. HCQM is currently maintained by a single author; the workflows below describe the intended process even when contribution volume is low.

---

## What you can contribute

| Contribution type | Where it goes | Review timeline |
|---|---|---|
| **Construct refinement** (proposed new subcomponent, indicator, or capability) | GitHub Issue using "Construct Refinement" template | Acknowledged within 14 days |
| **Citation correction or addition** | GitHub Issue using "Citation Correction" template | Acknowledged within 14 days |
| **Comparative analysis** (proposing a comparison with a framework not yet covered in Appendices D/E/G/H) | GitHub Issue using "Comparative Analysis" template | Acknowledged within 14 days |
| **General feedback or discussion** | GitHub Discussions | No SLA; best-effort |
| **Typo or formatting fix** | Pull Request directly | Reviewed on next maintenance pass |
| **Substantive whitepaper revision** | GitHub Issue first; PR only after issue discussion | Coordination required |

---

## Before you contribute

Please review the following before opening an issue or PR:

1. **`docs/positioning.md`** — clarifies what HCQM is and is not, including the layer of the stack it addresses (capacity, not architecture or evaluation).
2. **`docs/related-work.md`** — lists prior literatures HCQM draws on. New construct proposals should cite peer-reviewed prior work rather than novel coinages.
3. **`ROADMAP.md`** — current version status and target milestones. Some contributions may already be planned for a future version.
4. **The current whitepaper** (in this repo as `docs/HCQM_vN.N.md`, with the latest version being the source of truth). New constructs already on the v1.1 roadmap (e.g., episodic memory, alexithymia, hallucination precision) do not need re-proposal; comments on their planned framing are welcome.

---

## Versioning policy

- **Versioned files are never overwritten.** A revision becomes a new version file (e.g., `HCQM_v0.5.md` → `HCQM_v1.0.md`).
- **Priority claims anchor to v0.1** (Zenodo DOI 10.5281/zenodo.19587600) regardless of which version is current for reading purposes.
- **Subcomponents and indicators are stable within a version.** A proposed addition or change is tracked for the next minor or major version, not retrofitted.

---

## Standards for construct proposals

A proposed new construct, subcomponent, or indicator should include:

1. **Definition.** One or two sentences. Match the academic register of the existing HCQM tree (see `02-hcqm/HCQM-v0.1.md` or whitepaper Appendix A).
2. **Theoretical grounding.** At least one peer-reviewed citation. If the construct is from applied or non-peer-reviewed work (e.g., consulting-firm instruments), state this explicitly and acknowledge the validation asymmetry.
3. **Location proposal.** Suggested HCQM domain and capability where the new element fits. If you are proposing a new top-level domain, justify why it cannot be absorbed into an existing domain.
4. **Overlap analysis.** Identify any HCQM capabilities or subcomponents that the proposed addition overlaps with, and propose how the overlap should be handled (collapse, distinguish at a finer level, or retain as intentional redundancy).
5. **Behavioral indicators.** At minimum three observable behavioral indicators using the HCQM indicator style.
6. **Synthetic-system application notes.** How would this construct manifest in or be measured against an AI system?

---

## Standards for citation work

- All citations must be verifiable against primary sources. Indirect or AI-generated citations are not acceptable.
- Use APA 7 style for new entries, matching the existing References section.
- DOIs are required for journal articles; arXiv IDs are acceptable for preprints; book entries should include publisher and year.
- If you are correcting an existing citation, include both the current (incorrect) entry and the proposed correction, with a source link verifying the correction.

---

## Review process

1. **Issue created** → maintainer triages within 14 days, applies labels (`construct-proposal`, `citation`, `comparative-analysis`, `roadmap-v1.1`, `roadmap-v2.0`, `clarification`, `won't-fix`, etc.).
2. **Discussion in issue thread.** Maintainer or external participants respond. Most discussions stay within the issue; substantive proposals may move to a `branch-XX-{slug}` file in `00-meta/claude/` for tracking (this is an internal-workflow detail).
3. **Decision recorded in issue thread.** One of: accepted-for-next-version, accepted-deferred, declined-with-reason, or moved-to-discussions for further input.
4. **Implementation.** Accepted changes are tracked in `ROADMAP.md` and applied at the next version revision.
5. **Acknowledgment.** Accepted external contributions are acknowledged in the affected version's CHANGELOG entry and, where substantial, in the whitepaper's acknowledgments section.

---

## Code of conduct

HCQM is a research framework, not a product. Discussion should be substantive, citable, and oriented toward improving the framework. The following are out of scope:

- Personal disputes
- Promotional content for commercial products or services
- Discussion of the AI-vs-human-cognition debate as a political or ideological matter (HCQM is methodologically neutral on this question; see whitepaper §6.6)
- Requests to remove existing critique or limitation statements; HCQM is committed to honest reporting of its own weaknesses

---

## License terms

- All framework content (whitepaper, taxonomy, indicators, comparative analyses, documentation) is licensed under **CC BY 4.0**. Attribution required: Kameron M. Green, HCQM, Zenodo DOI 10.5281/zenodo.19587600, with link to https://github.com/hgenix20/hcqm.
- Any code contributed to the repository is licensed under **MIT**.
- Contributions are accepted under the same licenses. By opening an issue or pull request, you agree your contribution is licensed accordingly.

---

## Contact

For questions outside the issue tracker:

- **Author:** Kameron M. Green
- **Email:** kameron.m.green@outlook.com
- **ORCID:** 0009-0002-8350-3641

Response times are best-effort; HCQM is currently maintained alongside other work.
