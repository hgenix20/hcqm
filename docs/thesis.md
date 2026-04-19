# HCQM: Research Thesis and Positioning

**Author:** Kameron Green  
**ORCID:** [0009-0002-8350-3641](https://orcid.org/0009-0002-8350-3641)  
**Date:** 2026-04-19  
**Status:** Living document, updated as the research evolves  
**Project:** [github.com/hgenix20/hcqm](https://github.com/hgenix20/hcqm)  
**DOI:** [10.5281/zenodo.19587600](https://doi.org/10.5281/zenodo.19587600)

---

## 1. Problem Statement

Intelligence research has a fragmentation problem. Decades of work in cognitive science, psychology, psychometrics, and intelligence research have produced many well-validated constructs for describing human capability: fluid and crystallized intelligence (Cattell, 1963; Carroll, 1993), emotional intelligence (Salovey & Mayer, 1990), social intelligence (Thorndike, 1920), cultural intelligence (Earley & Ang, 2003), executive function (Miyake et al., 2000; Diamond, 2013), metacognition (Flavell, 1979), creativity (Guilford, 1950; Torrance, 1966), grit (Duckworth et al., 2007), adversity tolerance (Stoltz, 1997), adaptability (Pulakos et al., 2000), digital intelligence (DQ Institute, 2019), computational thinking (Wing, 2006), and systems thinking (Senge, 1990; Meadows, 2008), among others.

These constructs were developed independently, in separate research traditions, using different methodologies and vocabularies. No single framework integrates them into a unified, hierarchical taxonomy that serves both assessment and engineering purposes.

This fragmentation matters in two domains. For human development, practitioners lack a unified vocabulary for evaluating the full range of human capabilities. Assessments typically focus on one dimension (IQ, EQ, creativity, grit) without a framework for understanding how they relate or how to prioritize development across them. For AI systems, cognitive architecture research increasingly draws on cognitive science to structure agent capabilities, but existing frameworks remain focused on cognitive and perceptual faculties without systematically addressing motivational, emotional, social, cultural, creative, or strategic dimensions.

## 2. The HCQM Thesis

HCQM (Human Capability Quotient Map) proposes an integrated, hierarchical taxonomy that synthesizes existing capability research into a unified framework spanning eight domains:

1. **General Cognitive Intelligence** : reasoning, fluid and crystallized intelligence, processing speed, working memory
2. **Executive / Self-Regulatory Intelligence** : metacognition, cognitive control, flexibility, planning, inhibitory control
3. **Emotional & Social Intelligence** : emotional awareness and regulation, social dynamics, cultural adaptation, interpersonal awareness
4. **Creative & Innovation Intelligence** : originality, divergent thinking, associative thinking
5. **Motivational & Adaptive Intelligence** : curiosity, adaptability, adversity tolerance, grit
6. **Learning & Knowledge Intelligence** : learning agility, knowledge integration, transfer
7. **Digital & Technological Intelligence** : digital fluency, information literacy, computational thinking
8. **Systems & Strategic Intelligence** : systems thinking, strategic reasoning, pattern recognition, predictive intelligence

Each domain contains named quotients, each quotient has defined subcomponents, and each subcomponent has observable behavioral indicators. This consistent structure (domain, quotient, subcomponent, indicator) is designed to support both human capability assessment and synthetic system design.

The central thesis is that **human capability taxonomies from psychology and intelligence research can serve as prescriptive engineering blueprints for AI cognitive architectures, not just descriptive frameworks for understanding human performance**. Where existing taxonomies describe what capabilities exist, HCQM is additionally designed to specify what capabilities a synthetic cognitive system should implement, how they decompose into buildable components, and what indicators would demonstrate successful implementation.

## 3. Origin

HCQM originated as a practical tool for assessing and developing a child's capabilities across the full range of human intelligence, not just IQ but emotional, social, creative, motivational, and strategic dimensions. The initial synthesis drew on existing constructs from cognitive science, psychology, and intelligence research to build a unified assessment framework that could support targeted development planning.

During this process, it became clear that the same hierarchical structure could serve a second purpose: as an architectural blueprint for designing AI systems that mirror the structure of human cognition rather than only approximating its outputs. This dual-use framing (human development and synthetic architecture) is what distinguishes HCQM from both classical psychometric taxonomies and existing cognitive architecture frameworks.

## 4. Positioning Against Adjacent Work

### 4.1 Classical Cognitive Architectures (SOAR, ACT-R, CLARION)

Classical cognitive architectures model the mechanisms of cognition: perception, memory systems, production rules, goal stacks, and learning processes. They are mechanistically detailed and computationally grounded. However, they generally do not address emotional intelligence, social and cultural capability, motivational persistence, adversity tolerance, creativity as a distinct generative capacity, or systems-level strategic reasoning. HCQM complements these architectures by providing a broader capability map that extends beyond core cognition into applied human performance domains.

### 4.2 CoALA (Sumers et al., 2023)

CoALA (Cognitive Architectures for Language Agents) draws on the lineage of classical cognitive architectures to propose a framework for organizing LLM-based agents. It describes modular memory components, structured action spaces, and generalized decision-making processes. CoALA is valuable as a retrospective survey and prospective blueprint for agent design. However, it does not organize capabilities around a human capability taxonomy and does not systematically address emotional, motivational, cultural, creative, or strategic dimensions. HCQM provides the capability taxonomy that frameworks like CoALA could use to define what an agent should be capable of, not just how it should be structured.

### 4.3 DeepMind Cognitive Taxonomy (Burnell et al., 2026)

Google DeepMind's 2026 cognitive taxonomy is the most directly adjacent work to HCQM. It identifies 10 cognitive faculties (perception, generation, attention, learning, memory, reasoning, metacognition, executive functions, problem solving, and social cognition) and proposes a three-stage evaluation protocol for measuring AI progress against human baselines.

A detailed comparative analysis (see `docs/deepmind-comparison.md` in this repository) mapped all 31 HCQM constructs against DeepMind's 10 faculties. Key findings:

**Where DeepMind is stronger.** DeepMind provides finer-grained mechanistic decomposition of cognitive processes. Its treatment of perception (modality-specific, low-level vs. high-level), memory (semantic, episodic, procedural, prospective, forgetting), reasoning (deductive, inductive, abductive, analogical, mathematical), and problem solving (representation, retrieval, decomposition, planning, execution) is more granular than HCQM's current structure. HCQM v1.0 will incorporate lessons from this decomposition, particularly by adding Memory, Perception, and Attention as more explicit architectural domains.

**Where HCQM is broader.** HCQM covers capability dimensions that DeepMind's taxonomy does not model as standalone faculties: emotional intelligence, cultural intelligence, creativity as a distinct macro-domain, curiosity and epistemic drive, adaptability, adversity tolerance, grit, digital intelligence, information literacy, systems intelligence, strategic intelligence, and predictive intelligence. Of all 31 HCQM constructs, only one (Adversity Quotient) has zero equivalent in DeepMind's framework. This means the differentiation is primarily about depth and framing rather than entirely different territory, with the critical exception that DeepMind does not model resilience, stress endurance, or recovery under pressure as cognitive faculties at all.

**The key structural difference.** DeepMind's taxonomy is evaluative: it measures how close AI systems are to human cognitive performance. HCQM is additionally prescriptive: it maps capabilities to buildable architectural components for synthetic systems. DeepMind asks how well a given AI perceives, reasons, and remembers compared to humans. HCQM asks what capabilities should be built into a cognitive architecture and how they decompose into implementable modules.

### 4.4 CHC Theory (Cattell-Horn-Carroll)

CHC theory is the most empirically validated taxonomy of cognitive abilities and serves as a foundational reference for HCQM's first domain (General Cognitive Intelligence). HCQM draws on CHC for its treatment of fluid intelligence, crystallized intelligence, processing speed, and working memory. However, CHC is restricted to cognitive abilities and does not extend to the emotional, social, motivational, creative, or strategic capabilities addressed in HCQM's remaining seven domains.

### 4.5 Multiple Intelligence Frameworks (Gardner, Sternberg)

Gardner's theory of multiple intelligences (1983) and Sternberg's triarchic theory (1985) both argue for broader conceptions of intelligence beyond IQ. HCQM shares this motivation and extends it further by providing hierarchical structure, defined subcomponents, and observable indicators, features that Gardner's and Sternberg's frameworks lack in sufficient detail for either systematic assessment or engineering application.

## 5. What HCQM Is and Is Not

**HCQM is:**

- A synthesis framework that integrates existing capability research into a unified taxonomy
- A hierarchical structure designed for both assessment and engineering use
- A prescriptive blueprint proposing what capabilities a cognitive architecture should implement
- A living research artifact that will be revised as the literature review progresses
- An open, citeable, publicly developed framework (CC BY 4.0)

**HCQM is not:**

- A claim to have invented new capabilities; the underlying constructs are drawn from existing research
- An empirically validated unified theory; it is a proposed framework awaiting formal validation
- A complete cognitive architecture specification; the architecture whitepaper is a separate, planned work
- A replacement for existing taxonomies; it is intended to complement and integrate them

## 6. Research Program

The HCQM research program has four planned phases:

**Phase 1 (in progress): HCQM v1.0, Scholarly Framework Paper.** A full literature review across all eight domains (see Section 2), formal attribution to source research, revision of the taxonomy based on findings, and publication as a citeable framework paper with DOI. The v1.0 revision will incorporate structural additions informed by the DeepMind comparison, particularly Memory, Perception, and Attention as more explicit domains.

**Phase 2 (planned): Architecture Whitepaper.** A companion paper proposing HCQM as a prescriptive engineering blueprint for synthetic cognitive architectures, with module decomposition, integration model, data flow design, and explicit mapping from HCQM domains to buildable system components.

**Phase 3 (planned): Reference Implementation.** A first working module demonstrating HCQM-grounded architecture principles, with tests, documentation, and evaluation against the framework's own indicators.

**Phase 4 (long-term): Expansion, Evaluation, and Community.** Additional modules, integration proof-of-concept, formal evaluation frameworks, and engagement with the research community for feedback and adoption.

## 7. Contributions

The intended contributions of HCQM, once the scholarly v1.0 is published, are:

1. **Integration.** A unified hierarchical taxonomy that brings together capability constructs from cognitive science, psychology, psychometrics, and intelligence research into a single framework, where no such integration currently exists at this scope.

2. **Prescriptive engineering framing.** The explicit proposal that capability taxonomies should serve as engineering blueprints for cognitive architecture, not just descriptive or evaluative frameworks.

3. **Dual-use design.** A single framework that supports both human capability assessment (development, coaching, education) and synthetic system design (AI architecture, agent design).

4. **Assessment-ready structure.** A consistent domain-to-quotient-to-subcomponent-to-indicator pattern that makes the taxonomy directly adaptable to rubrics, benchmarks, and evaluation instruments.

5. **Broader scope than existing cognitive taxonomies.** Coverage of motivational, emotional, social, cultural, creative, adaptive, digital, and strategic dimensions that are absent or underrepresented in purely cognitive frameworks.

## 8. Current Limitations

- HCQM v0.1 was developed as a synthesis without formal citations to source literature. The v1.0 revision will address this through a comprehensive literature review.
- The framework has not been empirically validated as a unified construct. Validation is part of the long-term research program.
- The prescriptive engineering application (architecture whitepaper and reference implementation) has not yet been demonstrated. It is a stated thesis, not a proven result.
- The taxonomy's current mechanistic depth is weaker than frameworks like DeepMind's cognitive taxonomy. The v1.0 revision will strengthen this through the addition of Memory, Perception, and Attention domains and finer-grained sub-capability decomposition where warranted.
- The author is an independent researcher without institutional backing. The work's credibility will depend entirely on the quality of the published scholarship and the rigor of the implementation.

## 9. Engagement

This is an active research project. The author welcomes substantive engagement from researchers and practitioners working on adjacent problems, including but not limited to:

- Cognitive architecture for AI agents
- Capability taxonomies grounded in human intelligence research
- Long-horizon agent systems and memory architectures
- Pathways toward more general and capable AI through architectural design
- Critique of HCQM's structure from researchers in cognitive science, psychology, or AI

Feedback can be directed through GitHub Issues on the project repository or via the contact information on the author's GitHub profile.

## References

Anderson, J. R. (2007). *How Can the Human Mind Occur in the Physical Universe?* Oxford University Press.

Burnell, R., Yamamori, Y., Firat, O., Olszewska, K., Hughes-Fitt, S., Kelly, O., Galatzer-Levy, I. R., Morris, M. R., Dafoe, A., Snyder, A. M., Goodman, N. D., Botvinick, M., & Legg, S. (2026). Measuring Progress Toward AGI: A Cognitive Framework. Google DeepMind.

Carroll, J. B. (1993). *Human Cognitive Abilities: A Survey of Factor-Analytic Studies.* Cambridge University Press.

Cattell, R. B. (1963). Theory of fluid and crystallized intelligence: A critical experiment. *Journal of Educational Psychology, 54*(1), 1-22.

Diamond, A. (2013). Executive functions. *Annual Review of Psychology, 64*, 135-168.

Duckworth, A. L., Peterson, C., Matthews, M. D., & Kelly, D. R. (2007). Grit: Perseverance and passion for long-term goals. *Journal of Personality and Social Psychology, 92*(6), 1087-1101.

Earley, P. C., & Ang, S. (2003). *Cultural Intelligence: Individual Interactions Across Cultures.* Stanford University Press.

Flavell, J. H. (1979). Metacognition and cognitive monitoring: A new area of cognitive-developmental inquiry. *American Psychologist, 34*(10), 906-911.

Gardner, H. (1983). *Frames of Mind: The Theory of Multiple Intelligences.* Basic Books.

Guilford, J. P. (1950). Creativity. *American Psychologist, 5*(9), 444-454.

Laird, J. E. (2012). *The Soar Cognitive Architecture.* MIT Press.

Meadows, D. H. (2008). *Thinking in Systems: A Primer.* Chelsea Green Publishing.

Miyake, A., Friedman, N. P., Emerson, M. J., Witzki, A. H., Howerter, A., & Wager, T. D. (2000). The unity and diversity of executive functions and their contributions to complex "frontal lobe" tasks: A latent variable analysis. *Cognitive Psychology, 41*(1), 49-100.

Park, Y. (Ed.). (2019). *DQ Global Standards Report 2019: Common Framework for Digital Literacy, Skills and Readiness.* DQ Institute.

Pulakos, E. D., Arad, S., Donovan, M. A., & Plamondon, K. E. (2000). Adaptability in the workplace: Development of a taxonomy of adaptive performance. *Journal of Applied Psychology, 85*(4), 612-624.

Salovey, P., & Mayer, J. D. (1990). Emotional intelligence. *Imagination, Cognition and Personality, 9*(3), 185-211.

Senge, P. M. (1990). *The Fifth Discipline: The Art and Practice of the Learning Organization.* Doubleday.

Sternberg, R. J. (1985). *Beyond IQ: A Triarchic Theory of Human Intelligence.* Cambridge University Press.

Stoltz, P. G. (1997). *Adversity Quotient: Turning Obstacles into Opportunities.* John Wiley & Sons.

Sumers, T. R., Yao, S., Narasimhan, K., & Griffiths, T. L. (2023). Cognitive Architectures for Language Agents. *arXiv preprint arXiv:2309.02427.*

Sun, R. (2006). The CLARION cognitive architecture: Extending cognitive modeling to social simulation. In R. Sun (Ed.), *Cognition and Multi-Agent Interaction.* Cambridge University Press.

Thorndike, E. L. (1920). Intelligence and its uses. *Harper's Magazine, 140*, 227-235.

Torrance, E. P. (1966). *Torrance Tests of Creative Thinking.* Personnel Press.

Wing, J. M. (2006). Computational thinking. *Communications of the ACM, 49*(3), 33-35.

---

*HCQM is a synthesis framework. It does not claim to invent the underlying capabilities; it draws on extensive prior research and integrates it into a hierarchical structure with prescriptive applications. Full attribution to source literature will appear in HCQM v1.0.*
