# HCQM Positioning vs. Adjacent Work

**Author:** Kameron M. Green
**Last updated:** 2026-05-21
**Status:** Living document
**Purpose:** Explicit comparison table and positioning statements for HCQM relative to adjacent capability and cognitive frameworks. This document complements the detailed framework-by-framework analyses in the whitepaper (Appendices D, E, G, H) and the comparative paper notes in `03-literature/papers/`.

---

## What HCQM is

HCQM (Human Capability Quotient Map) is a **synthesis taxonomy** that organizes eight top-level capability domains and thirty-two constituent capabilities into a single hierarchical structure with defined subcomponents and behavioral indicators. It is positioned as **dual-use**: a taxonomy for both holistic human assessment and synthetic cognitive architecture specification, at the *capacity* layer rather than the structural or evaluation layer.

HCQM does not claim to invent new capabilities. Every construct in HCQM maps back to one or more prior research traditions (see whitepaper Appendix C). The novelty is in the integration.

---

## What HCQM is not

- **Not an empirical instrument.** HCQM has not been validated as an integrated assessment battery. Component constructs have varying validation levels (CHC-aligned cognitive abilities: strong; grit and mindset: meta-analytically attenuated; AQ and adaptability quotient: weak peer-reviewed support).
- **Not an evaluation protocol.** v0.5 sketches a three-stage protocol (§6.7) but does not specify a complete one.
- **Not a competitor to CoALA or DeepMind or Hendrycks.** HCQM addresses a different layer of the stack (capacity) than CoALA (structural) and a different breadth than DeepMind/Hendrycks (cognitive plus motivational, emotional, cultural, adversity, etc.).
- **Not architectural.** HCQM does not specify module interfaces, message formats, control flow, training regimes, or computational substrate. A companion architecture specification document is identified as priority future work (whitepaper §6.6, §6.9 item 7).

---

## High-level comparison table

| Framework | Type | Scope | Granularity | Includes motivational/emotional/cultural? | Includes architecture? | Includes evaluation protocol? |
|---|---|---|---|---|---|---|
| **HCQM** | Capacity taxonomy | Broad (8 domains incl. cognitive + non-cognitive) | Hierarchical (domain → capability → subcomponent → indicator) | Yes (Domains 3, 5; partial 7) | No (target surface only) | Sketched (§6.7) |
| **CHC** (Carroll 1993; McGrew 2009) | Cognitive taxonomy | Cognitive only | Three-stratum (g → broad → narrow) | No | No | No (taxonomy; instruments separate) |
| **CoALA** (Sumers et al., 2024) | Cognitive architecture | LLM agents | Three-dimension (memory + actions + decisions) | No | Yes (structural) | No |
| **DeepMind 2026** (Burnell et al.) | Cognitive evaluation | Cognitive only (10 faculties) | Three-level (faculty → process → indicator) | No | No | Yes (3-stage protocol + Kaggle benchmarks) |
| **Hendrycks et al. (2025)** | Cognitive evaluation | Cognitive only (10 domains, CHC-grounded) | Two-level (domain → sub-faculty, equal-weighted) | No | No | Yes (psychometric battery adaptations; aggregate score) |
| **OECD 2025** | Policy capability | Cognitive + manipulation + robotic (9 domains) | Five-level scale per domain | No | No | Yes (level-scoring rubric) |

---

## HCQM's unique value claims

### 1. First-class motivational and adaptive capabilities

Curiosity (5.1), Adaptability (5.2), Adversity (5.3), and Grit (5.4) are HCQM Domain 5 capabilities. None of CHC, CoALA, DeepMind 2026, Hendrycks 2025, or OECD 2025 treats these as first-class. The Adversity Quotient (5.3) specifically has **zero direct equivalent** in the intersection of all four contemporary AI capability frameworks (DeepMind, CoALA, Hendrycks, OECD); see whitepaper §2.11.7.

### 2. First-class cultural intelligence as competence (not knowledge)

HCQM 3.3 Cultural Intelligence draws on Earley & Ang (2003) and treats cross-cultural functioning as a capability. Hendrycks treats culture as knowledge (sub-faculty of K); DeepMind treats it partially under social cognition; CoALA and OECD do not address it. HCQM is the only framework that operationalizes cultural intelligence as competence.

### 3. Systems and strategic thinking as a top-level domain

HCQM Domain 8 (Systems Intelligence, Strategic Intelligence, Pattern Intelligence, Predictive Intelligence) is absent from CoALA, DeepMind, Hendrycks, and OECD as a coherent domain. DeepMind treats causal reasoning under problem-solving sub-faculties; HCQM treats it as a top-level capability area with its own constructs and indicators.

### 4. Digital intelligence as a top-level domain

HCQM Domain 7 includes Digital Intelligence (DQ), Information Literacy, and Computational Thinking. CoALA, DeepMind, Hendrycks, and OECD either omit this entirely or treat fragments (e.g., OECD's "language" domain includes some digital-literacy elements; CoALA's "digital grounding" action type covers tool use).

### 5. Indicator-based assessment framing

Each HCQM capability is accompanied by behavioral indicators (~130 across the framework). CoALA, DeepMind, Hendrycks, and OECD specify tests or tasks but not indicators usable in qualitative human assessment. HCQM's indicators support coaching, education, development planning, and 360-feedback applications that the AI-focused frameworks do not address.

### 6. Dual-use framing

HCQM is positioned for both human-development assessment and synthetic cognitive architecture specification at the capacity layer. CHC and CoALA are single-use (cognitive measurement; LLM agent architecture). DeepMind, Hendrycks, and OECD are AI-evaluation-only.

---

## Where HCQM is weaker than each comparison framework

This is the converse list, recorded honestly.

### vs. CHC

- HCQM compresses CHC's narrow-ability layer; loses some granularity within Domain 1
- HCQM does not represent Ga, Grw, Gh, Gk, Go, Gp, or Gps as separate capabilities (whitepaper Appendix F)
- HCQM Domain 1 definitions are looser than canonical CHC and may admit ambiguous mapping (flagged for v1.0 tightening)

### vs. CoALA

- HCQM does not currently capture episodic vs. procedural memory as distinct types (CoALA does)
- HCQM does not distinguish memory *encoding* from *retrieval* operations
- HCQM does not currently capture *grounding* as a distinct bridging action between internal state and external environment
- HCQM does not capture *metareasoning* (compute allocation for reasoning) at the construct level
- HCQM treats capabilities primarily as static capacity, not as dynamic processes within a decision loop

### vs. DeepMind 2026

- HCQM does not separately model perception or generation as cognitive faculties
- HCQM does not provide a complete evaluation protocol (sketch only in §6.7)
- HCQM's social-cognition decomposition is broader but shallower in mechanistic terms than DeepMind's

### vs. Hendrycks 2025

- HCQM does not decompose memory into storage (MS) vs. retrieval (MR) as standalone domains
- HCQM does not include hallucination / retrieval precision as a measurable construct
- HCQM does not include auditory processing as a domain
- HCQM does not include visual generation as a sub-faculty
- HCQM treats Speed as a single construct; Hendrycks decomposes into 10 sub-faculties

### vs. OECD 2025

- HCQM does not include vision and manipulation as first-class capabilities (HCQM scopes sensory and motor out at §6.4)
- HCQM does not include "robotic intelligence" as a domain
- HCQM is not policy-facing; it does not provide a level-scoring rubric usable for governance or disclosure
- HCQM has not undergone the kind of multi-expert consensus process the OECD framework received (50+ experts, ~5 years)

---

## Relationship to prior comparison documents

Two earlier comparison documents exist in the vault:

- `01-thesis/positioning-vs-deepmind.md` — detailed DeepMind comparison, including a 32-construct gradient match table and per-domain coverage analysis. This document remains the most thorough single-framework comparison and is the basis for the summary statements above.
- `03-literature/papers/burnell-2026-deepmind-cognitive-taxonomy.md` — paper-note format for the DeepMind paper.
- `03-literature/papers/hendrycks-2025-definition-of-agi.md` — paper-note format for Hendrycks, including a parallel 32-construct gradient match table.

This `positioning.md` is the synthesis layer. The two paper notes and `positioning-vs-deepmind.md` are the detail layer.

---

## Outstanding comparison work

| Framework | Detailed comparison status |
|---|---|
| DeepMind 2026 | Complete (`positioning-vs-deepmind.md` + Appendix D + paper note) |
| Hendrycks 2025 | Complete (Appendix G + paper note) |
| CoALA | Complete (Appendix E in whitepaper) |
| OECD 2025 | Complete (Appendix H in whitepaper); standalone paper note not yet written |
| CHC | Complete (Appendix F + whitepaper §2.1, §2.11) |
| Kotseruba & Tsotsos (2020) cognitive architectures review | Pending |
| Wu et al. (2025) | Pending |

---

## Positioning statement (canonical, for use in external communication)

> HCQM is a synthesis taxonomy of human and synthetic cognitive capability. It integrates eight top-level domains (cognitive, executive, emotional/social, creative, motivational, learning, digital, systems/strategic) and 32 capabilities into a hierarchical structure with defined behavioral indicators. HCQM is intended for both holistic human-development assessment and capacity-layer specification of synthetic cognitive architectures. Compared to contemporary AI capability frameworks (CoALA, DeepMind 2026, Hendrycks 2025, OECD 2025), HCQM extends the capability surface beyond cognitive faculties to include motivational, emotional, cultural, adversity, digital, and systems-thinking dimensions. HCQM does not replace these frameworks; it specifies the broader capacity surface that structural architectures should cover and that cognitive-evaluation frameworks measure subsets of.
