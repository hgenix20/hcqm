# HCQM: Human Capability Quotient Map

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19587600.svg)](https://doi.org/10.5281/zenodo.19587600)
![Version](https://img.shields.io/badge/version-v0.8-blue)

**An integrated hierarchical taxonomy of human capabilities — designed for both human development assessment and synthetic cognitive architecture.**

---

## What this is

HCQM (Human Capability Quotient Map) is a research framework that integrates existing capability research from cognitive science, psychology, and intelligence studies into a single hierarchical taxonomy spanning eight domains and 33 constituent capabilities: General Cognitive, Executive/Self-Regulatory, Emotional & Social, Creative & Innovation, Motivational & Adaptive, Learning & Knowledge, Digital & Technological, and Systems & Strategic.

The framework is intended for two complementary purposes:

1. **Human development** — systematic, multi-dimensional capability assessment to support targeted growth planning across cognitive, emotional, motivational, and systems-thinking dimensions.
2. **Synthetic cognitive architecture** — a partial capacity-layer specification for AI systems, identifying the capability surface a generally intelligent agent must cover, with particular attention to the motivational, metacognitive, and adaptive capacities that govern long-horizon agent reliability.

HCQM does not claim to discover new capabilities. Its contribution is the integration of existing, peer-reviewed capability traditions into a single hierarchical structure, and the application of that structure as a dual-use specification target.

## Why it exists

Existing capability frameworks are fragmented. Classical cognitive taxonomies (CHC theory, ACT-R, Soar, the Common Model of Cognition) cover cognitive ability and executive function. Specialized frameworks (EQ, CQ, AQ, DQ, Grit, systems thinking) exist independently. Contemporary AI-evaluation frameworks (the Hernández-Orallo and Vold (2019) catalogue, CoALA, DeepMind 2026, Hendrycks 2025, OECD 2025) focus primarily on cognitive ability and largely omit motivational, emotional, cultural, and adversity-related dimensions.

HCQM addresses this gap by proposing a single hierarchical taxonomy that integrates these traditions and identifies the coverage asymmetry between the human-capability tradition and contemporary AI frameworks — particularly the motivational, adaptive, and metacognitive capacities that govern autonomous agent reliability over long horizons.

## Current status

**Current public version: v0.8 (reviewer-revised draft, 2026-06-09)**

v0.8 integrates all external reviewer feedback and is the pre-arXiv release. It supersedes v0.6 for reading. v1.0 will follow after one pending acknowledgment confirmation and arXiv endorsement are secured.

**v0.1 DOI (priority anchor):** [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19587600.svg)](https://doi.org/10.5281/zenodo.19587600)
**v0.6 DOI:** [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20345943.svg)](https://doi.org/10.5281/zenodo.20345943)
**v0.8 DOI:** [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20632044.svg)](https://doi.org/10.5281/zenodo.20632044)

See `whitepaper/HCQM_v0.8.md` for the full paper.

## Repository structure

```
whitepaper/
  HCQM_v0.8.md          current version (reviewer-revised draft)
  HCQM_v0.6.md          prior public release (retained for archive)
  HCQM.png              Figure 1 — HCQM schematic (8 domains, 33 capabilities)
  HCQM-comparison.png   Figure 2 — five-framework coverage comparison
HCQM-v0.1.md            original v0.1 framework tree (priority anchor)
docs/
  thesis.md             research thesis and positioning document
  related-work.md       structured literature review by domain
  positioning.md        explicit comparison vs. adjacent frameworks
ROADMAP.md              versioning plan and milestone tracking
CONTRIBUTING.md         contribution guidelines
CHANGELOG.md            version history
CITATION.cff            citation metadata
LICENSE                 CC BY 4.0
```

## Roadmap

- **v0.8 — reviewer-revised draft (current):** All external reviewer feedback integrated. Five-framework comparative analyses (CoALA, DeepMind, Hendrycks, OECD, ADeLe). 33 constructs. CHC terminology updated to Schneider and McGrew (2018). Pre-arXiv release.
- **v1.0 — arXiv release (target: mid-2026):** Pending one acknowledgment confirmation and arXiv endorser. No substantive content changes planned.
- **v1.1 — subcomponent refinements (Q3 2026):** Episodic/procedural memory constructs, cognitive resource allocation, hallucination/retrieval precision, capability-to-instrument mapping table.
- **Architecture whitepaper (planned, Q3–Q4 2026):** HCQM as a prescriptive capacity-layer specification for synthetic cognitive architectures, with module decomposition and integration model.
- **v2.0 — empirical validation (2027+):** Full instrument battery, psychometric validation, predictive validity studies, cross-cultural validation.

See `ROADMAP.md` for full detail.

## Author

**Kameron M. Green**
ORCID: [0009-0002-8350-3641](https://orcid.org/0009-0002-8350-3641)
Independent researcher working at the intersection of human capability taxonomy and AI cognitive architecture. MS in Computer Science (AI concentration), University of Nebraska at Omaha.

## Citing this work

If you reference HCQM, please cite the most recent archived version. Metadata is in `CITATION.cff`.

**Citing v0.8 (most recent Zenodo archive):**
> Green, K. M. (2026). *HCQM: A Hierarchical Capability Map for Assessing and Developing Human and Synthetic Intelligence* (v0.8). Zenodo. https://doi.org/10.5281/zenodo.20632044

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

Update the version and DOI to the most recent Zenodo archive when citing.

## License

This work is licensed under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). You are free to share and adapt the material with appropriate attribution.

## Acknowledgments

The author thanks Dr. Kevin McGrew (Institute for Applied Psychometrics) for substantive feedback on the treatment of Cattell–Horn–Carroll theory, and two anonymous reviewers for feedback on the cognitive-architecture and AI-evaluation sections.

## Engagement

This is an active research project. Issues, discussions, and critique are welcome via GitHub Issues. The author is particularly interested in:

- Critique of the HCQM structure from researchers in cognitive science, psychology, or AI
- Pointers to capability traditions not yet represented in the framework
- Discussion of the reliability-and-autonomy layer (§5.2) and its mapping to agent evaluation
