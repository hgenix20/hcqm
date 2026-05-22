# HCQM: Human Capability Quotient Map

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19587600.svg)](https://doi.org/10.5281/zenodo.19587600)
![Version](https://img.shields.io/badge/version-v0.6--external--review-blue)

**An integrated hierarchical taxonomy of human capabilities — designed for both human development assessment and synthetic cognitive architecture.**

---

## What this is

HCQM (Human Capability Quotient Map) is a research project developing a unified, hierarchical taxonomy that integrates existing capability research from cognitive science, psychology, and intelligence research into a single framework spanning eight domains: General Cognitive, Executive/Self-Regulatory, Emotional & Social, Creative & Innovation, Motivational & Adaptive, Learning & Knowledge, Digital & Technological, and Systems & Strategic.

The framework is intended for two complementary purposes:

1. **Human development** — systematic, multi-dimensional capability assessment to support targeted growth planning.
2. **Synthetic cognitive architecture** — a prescriptive engineering blueprint for building AI systems grounded in the full range of human capability dimensions, not just cognitive ability.

## Why it exists

Existing intelligence and capability frameworks are fragmented. Classical cognitive taxonomies (CHC theory, ACT-R, SOAR) focus on cognitive ability and executive function. Specialized quotient frameworks (EQ, SQ, CQ, AQ, DQ, Grit) exist independently and are rarely integrated. Modern LLM-era cognitive architectures (CoALA, DeepMind's cognitive taxonomy) ground themselves in cognitive science but generally omit motivational, emotional, social, cultural, and adversity-related dimensions.

HCQM addresses this gap by proposing a single hierarchical taxonomy that brings these dimensions together and positions them as both assessable human capabilities and buildable architectural components for AI systems.

## Current status

**Current public version: v0.6 (external-review draft, 2026-05-22)**

v0.6 is the first publicly released draft since v0.1. It contains the full scholarly framework paper — 8 domains, 32 constructs, comparative analyses against four contemporary AI capability frameworks (CoALA, DeepMind 2026, Hendrycks 2025, OECD 2025), 62 verified references, and a three-stage evaluation protocol sketch. v0.2–v0.5 were internal working drafts.

**v0.6 DOI:** *(pending Zenodo archival — will be updated)*
**v0.1 DOI (priority anchor):** [10.5281/zenodo.19587600](https://doi.org/10.5281/zenodo.19587600)

v1.0 will follow after external reviewer feedback is integrated (~mid-June 2026). See `whitepaper/HCQM_v0.6.md` for the full paper.

## Roadmap

- **v0.6 — external-review draft (current):** Full framework paper released for external review. Comparative analyses against CoALA, DeepMind, Hendrycks, and OECD frameworks complete.
- **v1.0 — post-review release (~mid-June 2026):** Integrates external reviewer feedback. First stable public release.
- **v1.1 — subcomponent refinements (Q3 2026):** Episodic/procedural memory as explicit constructs, cognitive resource allocation subcomponent, hallucination/retrieval precision, capability-to-instrument mapping table.
- **Architecture whitepaper (planned, Q3–Q4 2026):** HCQM as a prescriptive capacity-layer specification for synthetic cognitive architectures, with module decomposition and integration model.
- **Reference implementation (planned, 2027):** First working module demonstrating HCQM-grounded architecture principles.
- **v2.0 — empirical validation (2027+):** Full instrument battery with psychometric validation, predictive validity studies, cross-cultural validation.

See `ROADMAP.md` for full detail.

## Repository structure

- `whitepaper/HCQM_v0.6.md` — current public version of the framework paper (v0.6 external-review draft)
- `HCQM.md` — original v0.1 working draft (retained as priority anchor)
- `docs/thesis.md` — research thesis and positioning against adjacent frameworks
- `docs/deepmind-comparison.md` — gradient-match analysis vs. DeepMind cognitive taxonomy
- `docs/related-work.md` — literature review notes
- `CHANGELOG.md` — version history
- `CITATION.cff` — citation metadata
- `LICENSE` — CC BY 4.0

## Author

**Kameron M. Green**
ORCID: [0009-0002-8350-3641](https://orcid.org/0009-0002-8350-3641)
Independent researcher working at the intersection of human capability taxonomy and AI cognitive architecture. MS in Computer Science (AI concentration), University of Nebraska at Omaha.

## Citing this work

If you reference HCQM in your work, please cite it using the metadata in `CITATION.cff` or:

**Citing v0.6 (current public draft):**
> Green, K. M. (2026). *HCQM: A Hierarchical Capability Map for Assessing and Developing Human and Synthetic Intelligence* (v0.6). Zenodo. *(DOI pending — see CITATION.cff for update)*

**Citing v0.1 (priority anchor):**
> Green, K. M. (2026). *HCQM: Human Capability Quotient Map* (v0.1.1). Zenodo. https://doi.org/10.5281/zenodo.19587600

BibTeX (v0.1 priority anchor):

    @software{green_hcqm_2026,
      author       = {Green, Kameron M.},
      title        = {HCQM: Human Capability Quotient Map},
      version      = {0.1.1},
      year         = {2026},
      publisher    = {Zenodo},
      doi          = {10.5281/zenodo.19587600},
      url          = {https://doi.org/10.5281/zenodo.19587600}
    }

## License

This work is licensed under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). You are free to share and adapt the material with appropriate attribution.

## Engagement

This is an active research project. Issues, discussions, and feedback are welcome. The author is particularly interested in:

- Pointers to relevant prior work in capability taxonomy and cognitive architecture
- Critique of the HCQM structure from researchers in cognitive science, psychology, or AI
- Discussion of positioning against adjacent work (DeepMind cognitive taxonomy, CoALA, classical cognitive architectures)

---

*HCQM is a synthesis framework. It does not claim to invent the underlying capabilities; it draws on extensive prior research and integrates it into a hierarchical structure with prescriptive applications. Full attribution to source literature will appear in HCQM v1.0.*
