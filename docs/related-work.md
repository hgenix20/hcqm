# Related Work

**Author:** Kameron M. Green
**Last updated:** 2026-05-21
**Status:** Living document; grows with literature review
**Purpose:** Catalog of literatures HCQM draws on and contemporary frameworks it is compared against. This document complements the formal References section of the whitepaper (`04-whitepaper/HCQM_v0.5.md`) and the Reading List (`03-literature/Reading List.md`).

---

## 1. Contemporary AGI and AI capability frameworks (direct comparison)

HCQM is compared against four contemporary frameworks in the whitepaper Appendices D, E, G, and H. Each is summarized here.

### 1.1 DeepMind 2026: *Measuring Progress Toward AGI: A Cognitive Framework* (Burnell et al., 2026)

A ten-faculty cognitive taxonomy (perception, generation, attention, learning, memory, reasoning, metacognition, executive functions, problem solving, social cognition) paired with a three-stage evaluation protocol (cognitive assessment → human baselines → cognitive profiles). Accompanies a Kaggle hackathon targeting five evaluation-gap areas (learning, metacognition, attention, executive functions, social cognition) with a $200,000 prize pool. HCQM positioning: DeepMind is structurally close in cognitive-faculty coverage; HCQM extends beyond cognition into motivational, cultural, adversity, digital, and systems-thinking dimensions. Full comparative analysis: `01-thesis/positioning-vs-deepmind.md` and `03-literature/papers/burnell-2026-deepmind-cognitive-taxonomy.md`. Whitepaper: §2.11.3 and Appendix D.

### 1.2 Hendrycks et al. (2025): *A Definition of AGI* (arXiv:2510.18212)

A CHC-grounded operational definition of AGI as matching "the cognitive versatility and proficiency of a well-educated adult." Decomposes general intelligence into ten equally weighted (10% each) cognitive domains: General Knowledge (Gc/Gkn), Reading and Writing (Grw), Mathematics (Gq), On-the-Spot Reasoning (Gf), Working Memory (Gwm), Long-Term Memory Storage, Long-Term Memory Retrieval, Visual Processing (Gv), Auditory Processing (Ga), Speed (Gs). Reports GPT-4 at 27% and GPT-5 at 57% aggregate AGI scores, with 0% on Long-Term Memory Storage and Hallucinations/Retrieval Precision for both models. HCQM positioning: closest CHC-faithful contemporary framework; natural anchor for HCQM Domain 1 evaluation. HCQM extends beyond Hendrycks' cognitive-only scope. Full comparative analysis: `03-literature/papers/hendrycks-2025-definition-of-agi.md`. Whitepaper: §2.11.4 and Appendix G.

### 1.3 CoALA: *Cognitive Architectures for Language Agents* (Sumers et al., 2024)

A structural framework for language agents organized along three dimensions: memory modules (working, episodic, semantic, procedural), structured action space (internal reasoning/retrieval/learning + external grounding actions), and decision-making procedure (proposal → evaluation → selection → execution loop). Published in *Transactions on Machine Learning Research* (arXiv:2309.02427). HCQM positioning: CoALA addresses the architectural layer; HCQM addresses the capacity layer. Complementary, not competing. CoALA's memory decomposition (especially episodic vs. procedural and read vs. write asymmetry) is a candidate refinement for HCQM v1.1. Full comparative analysis: whitepaper Appendix E.

### 1.4 OECD AI Capability Indicators (OECD, 2025)

A policy-facing capability framework organized around nine human-grounded ability domains (language, social interaction, problem solving, creativity, metacognition and critical thinking, knowledge/learning/memory, vision, manipulation, robotic intelligence), each on a five-level scale. Developed by a working group of over 50 experts over approximately five years. Places the most advanced LLMs at Level 2 for metacognition and critical thinking, Level 3 for creativity. HCQM positioning: OECD operates at a coarser operational level than HCQM (nine domains, five levels). Convergent inclusion of vision and manipulation as first-class capabilities is one signal that HCQM should reconsider its sensory/motor scope-out for embodied-AI use cases. Whitepaper: §2.11.5 and Appendix H.

---

## 2. Psychometric and intelligence-research foundations

### 2.1 General cognitive abilities

- **Spearman (1904)** — positive manifold and *g*
- **Cattell (1963); Horn & Cattell (1966)** — fluid (Gf) vs. crystallized (Gc) intelligence
- **Carroll (1993)** — *Human Cognitive Abilities: A Survey of Factor-Analytic Studies*, three-stratum model
- **McGrew (2009)** — integration of Cattell-Horn and Carroll into CHC theory
- **Schneider & McGrew (2018)** — updated CHC reference
- **Jensen (1998)** — *The g Factor*, *g*-purist position
- **Gottfredson (1997)** — "Mainstream Science on Intelligence" editorial

### 2.2 Working memory

- **Baddeley & Hitch (1974)** — original working memory model
- **Baddeley (2000)** — episodic buffer addition
- **Engle (2002)** — working memory capacity as executive attention

### 2.3 Multiple and triarchic intelligences

- **Gardner (1983, 1999)** — multiple intelligences
- **Sternberg (1985, 1999)** — triarchic theory; successful intelligence
- **Waterhouse (2006)** — psychometric critique of multiple-intelligences

---

## 3. Executive function and metacognition

- **Flavell (1979)** — metacognition as cognition about cognition
- **Schraw & Moshman (1995)** — metacognitive knowledge vs. regulation
- **Miyake et al. (2000)** — three-factor executive function model (updating, shifting, inhibition)
- **Diamond (2013)** — review in *Annual Review of Psychology*
- **Gioia, Isquith, Guy, & Kenworthy (2000)** — BRIEF informant-report instrument
- **Newell & Simon (1972)** — *Human Problem Solving*, planning literature
- **Koriat (1993)** — confidence calibration

---

## 4. Emotional, social, and cultural intelligence

### 4.1 Emotional intelligence

- **Salovey & Mayer (1990)** — original EI definition
- **Mayer, Salovey, & Caruso (2002, 2004)** — four-branch ability model; MSCEIT instrument
- **Goleman (1995)** — popularization; mixed model
- **Bar-On (1997)** — EQ-i instrument
- **Bagby, Parker, & Taylor (1994)** — Toronto Alexithymia Scale
- **Mayer, Roberts, & Barsade (2008)** — review and critique

### 4.2 Social intelligence

- **Thorndike (1920)** — original social intelligence proposal
- **Mafiascum dataset (de Ruiter & Kachergis, 2018)** — candidate evaluation substrate for multi-player social inference

### 4.3 Cultural intelligence

- **Earley & Ang (2003)** — *Cultural Intelligence*, Stanford University Press
- **Ang & Van Dyne (2008)** — *Handbook of Cultural Intelligence*
- **Ang et al. (2007)** — CQS instrument
- **Henrich, Heine, & Norenzayan (2010)** — WEIRD bias in psychological samples
- **Atari et al. (2023)** — *Which Humans?* on WEIRD bias in LLMs
- **AlKhamissi et al. (2024)** — cultural alignment of LLMs

---

## 5. Motivational and adaptive constructs

- **Duckworth, Peterson, Matthews, & Kelly (2007)** — grit definition and West Point validation
- **Duckworth & Quinn (2009)** — Grit-S
- **Credé, Tynan, & Harms (2017)** — meta-analytic critique of grit
- **Dweck (2006)** — *Mindset*; fixed vs. growth
- **Stoltz (1997)** — *Adversity Quotient*, CORE dimensions
- **Ployhart & Bliese (2006)** — I-ADAPT taxonomy of adaptability
- **Ryan & Deci (2000)** — self-determination theory
- **Kashdan, Rose, & Fincham (2004)** — curiosity and exploration
- **Kashdan et al. (2018)** — Five-Dimensional Curiosity Scale

---

## 6. Creativity

- **Guilford (1950)** — APA presidential address on creativity neglect
- **Mednick (1962)** — associative theory of creativity
- **Torrance (1974)** — TTCT
- **Amabile (1982)** — consensual assessment technique
- **Runco & Jaeger (2012)** — standard definition (novelty + usefulness)
- **Benedek & Neubauer (2013)** — revisiting Mednick

---

## 7. Learning, knowledge integration, and transfer

- **Lombardo & Eichinger (2000)** — original learning agility operationalization
- **De Meuse, Dai, & Hallenbeck (2010)** — *Learning Agility: A Construct Whose Time Has Come*
- **De Meuse (2017)** — review of learning agility evidence
- **Bransford, Brown, & Cocking (2000)** — *How People Learn*
- **Barnett & Ceci (2002)** — taxonomy for far transfer
- **Chi & Ohlsson (2005)** — complex declarative learning

---

## 8. Digital and computational

- **Park (2019); DQ Institute** — Digital Intelligence (DQ) framework (basis for IEEE 3527.1 standard)
- **Wing (2006, 2008, 2017)** — computational thinking
- **Román-González et al. (2017)** — Computational Thinking Test
- **ACRL Framework for Information Literacy (2016)** — information literacy standards
- **Wineburg & McGrew (2019)** — lateral reading and source evaluation
- **Ji et al. (2023)** — hallucination survey
- **Lin, Hilton, & Evans (2022)** — calibration in LLMs
- **Korbak et al. (2025)** — chain-of-thought unfaithfulness

---

## 9. Systems, strategy, and forecasting

- **Forrester (1961)** — *Industrial Dynamics*
- **Senge (1990)** — *The Fifth Discipline*
- **Meadows (2008)** — *Thinking in Systems*
- **Sterman (2000)** — *Business Dynamics*
- **Booth Sweeney & Sterman (2000)** — bathtub dynamics inventory
- **Liedtka (1998)** — strategic thinking
- **Heuer (1999)** — *Psychology of Intelligence Analysis*
- **Gibson (1979)** — *Ecological Approach to Visual Perception*
- **Tetlock (2005); Tetlock & Gardner (2015)** — forecasting and calibration

---

## 10. Cognitive architectures (classical)

- **Newell (1990)** — *Unified Theories of Cognition*
- **Anderson (2007)** — ACT-R
- **Laird (2012)** — Soar
- **Hudlicka (2007)** — MAMID, emotion modeling in cognitive architectures
- **Wray, Kirk, & Laird (2025)** — cognitive design patterns for LLM agents

---

## 11. Predictive processing and AI grounding

- **Friston (2010)** — free energy principle
- **Clark (2013)** — predictive processing
- **Block (1995); Chalmers (1996)** — consciousness and qualia (relevant to whitepaper §6.6 discussion of behavioral vs. phenomenal equivalence)

---

## 12. Wisdom and contested constructs

- **Grossmann et al. (2020)** — *The Science of Wisdom in a Polarized World*

---

## 13. Methodology

- **Embretson & Reise (2000)** — Item Response Theory for psychologists
- **Morris et al. (2026)** — additional jaggedness evidence in current AI systems

---

## Currently un-cited but on the reading list

The following items are on the active reading list (`03-literature/Reading List.md`) but not yet incorporated into the whitepaper. Inclusion criteria: deep-read + writing of a comparative note before citation.

- Kotseruba & Tsotsos (2020) — *A Review of 40 Years of Cognitive Architecture Research*
- Wu et al. (2025) — (specific citation pending)
- Several classical psychometric and cognition references; see Reading List for full enumeration.

---

## Maintenance notes

- When a new paper is deep-read and a markdown note is written in `03-literature/papers/`, add a one-line summary here under the appropriate section.
- When a citation is added to the whitepaper References section, verify it appears here.
- This document is the public-facing literature map; it does not duplicate the in-vault Reading List, which is the working tracker for what has been read vs. queued.
