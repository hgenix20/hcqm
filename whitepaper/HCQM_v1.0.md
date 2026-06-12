# HCQM: A Hierarchical Capability Map for Assessing and Developing Human and Synthetic Intelligence

**Author:** Kameron M. Green
**Version:** 1.0
**Date:** 2026-06-09
**Correspondence:** kameron.m.green@outlook.com
**Framework repository:** https://github.com/hgenix20/hcqm
**DOI (framework v0.1, priority anchor):** 10.5281/zenodo.19587600
**ORCID:** 0009-0002-8350-3641

**Note on version numbers.** This *paper* is version 1.0. References in the text to "HCQM v0.1" denote the *framework tree* (the canonical capability structure first timestamped on Zenodo and maintained at the GitHub repository above), which is versioned independently of the paper. Statements that "HCQM v0.1 does not…" therefore describe the current state of the framework specification, not a limitation of this paper.

---

## Abstract

The field of intelligence research has long been characterized by fragmentation, with distinct traditions examining general cognitive abilities (Carroll, 1993; McGrew, 2009), emotional and social competencies (Salovey & Mayer, 1990; Goleman, 1995), creativity (Guilford, 1950), metacognition (Flavell, 1979), grit and adaptability (Duckworth et al., 2007), and more recent constructs such as digital intelligence (Park, 2019) and systems thinking (Senge, 1990; Meadows, 2008). While each line of inquiry has yielded valuable insights and measurement tools, the absence of an integrated taxonomy limits holistic assessment of human potential and the principled design of synthetic cognitive architectures. This paper proposes the Human Capability Quotient Map (HCQM) as a hierarchical synthesis that organizes eight top-level domains (General Cognitive Intelligence, Executive/Self-Regulatory Intelligence, Emotional & Social Intelligence, Creative & Innovation Intelligence, Motivational & Adaptive Intelligence, Learning & Knowledge Intelligence, Digital & Technological Intelligence, and Systems & Strategic Intelligence) into a coherent framework. Each domain includes subcomponents and observable indicators drawn from established psychometric, psychological, and cognitive-science literature.

HCQM makes three contributions: the integration itself, a coverage-asymmetry observation, and an explicitly dual-use framing; the two durable differentiators are the integration and the dual-use framing. HCQM is positioned to support broad human capability assessment while also providing a partial prescriptive target, at the capacity layer, for engineering synthetic cognitive architectures, with the explicit limitation that full architectural prescriptiveness requires a companion specification document (§6.6). These are applied to a coverage asymmetry: the human-capability tradition treats motivational, affective, cultural, and adversity capability as first-class (contemporary CHC, for example, now includes emotional intelligence as a broad ability), whereas contemporary AI architecture and evaluation frameworks largely do not. Unlike purely evaluative taxonomies such as DeepMind's 2026 *Measuring Progress Toward AGI: A Cognitive Framework* (Burnell et al., 2026), which identifies 10 cognitive faculties for benchmarking AGI progress, HCQM brings these dimensions to bear as a specification target. Unlike engineering-oriented architectural frameworks such as CoALA (Sumers et al., 2024), which specifies memory modules, action spaces, and decision loops for language agents, HCQM specifies the capacity surface those structural slots are expected to implement. The dimensions the AI frameworks omit are not a miscellaneous remainder: they concentrate in the motivational, adaptive, and metacognitive capacities (persistence under failure, strategy revision, self-monitoring, calibration) that govern whether a long-horizon autonomous agent is *reliable*, as distinct from whether it is *capable*. HCQM's distinctive AI-facing contribution is to organize these as a first-class reliability-and-autonomy layer and specify it at the capacity level (§5.2); a worked example maps a documented long-horizon agent failure pattern to the layer it omits. HCQM consolidates and ports existing constructs rather than claiming to discover them.

Drawing on CHC theory (Carroll, 1993; Schneider & McGrew, 2018), multiple-intelligences and triarchic models (Gardner, 1983; Sternberg, 1985), cultural intelligence (Earley & Ang, 2003), computational thinking (Wing, 2006), and modern cognitive architectures for language agents (Sumers et al., 2024), HCQM offers a synthesis rather than a novel discovery. We outline design principles, detail the hierarchical structure, discuss applications in human development and AI engineering, and acknowledge limitations, including the need for empirical validation, operationalized assessment instruments, and an explicit evaluation protocol. This revised draft aims to stimulate cross-disciplinary dialogue and guide future instrument development and architectural design.

**Keywords:** human capabilities, intelligence taxonomy, cognitive architecture, AGI evaluation, capability-grounded architectures, autonomous agents, agent reliability, long-horizon agents, metacognition, grit, cultural intelligence, systems thinking, CHC theory, CoALA

---

## 1. Introduction

### 1.1 The fragmentation problem

Research on human capabilities has generated, over roughly a century, a large and growing inventory of "intelligences" and "quotients." The Cattell–Horn–Carroll (CHC) tradition in psychometrics describes a hierarchical taxonomy of broad and narrow cognitive abilities (Carroll, 1993; McGrew, 2009). Gardner (1983) proposed multiple relatively independent intelligences. Sternberg (1985) proposed a triarchic account. Salovey and Mayer (1990) formalized emotional intelligence (EI), later popularized by Goleman (1995) and refined by Mayer, Salovey, and Caruso (2004). Earley and Ang (2003) introduced cultural intelligence (CQ). Duckworth, Peterson, Matthews, and Kelly (2007) introduced grit as a trait-level construct. Dweck (2006) introduced mindset. Stoltz (1997) introduced the adversity quotient (AQ). Park (2019) and the DQ Institute introduced digital intelligence (DQ). Wing (2006) introduced computational thinking (CT). Senge (1990) and Meadows (2008) popularized systems thinking.

Each of these programs has accumulated its own measurement tradition, its own journals, and its own debates. The result is a body of work that is individually rigorous but collectively fragmented. A practitioner who wants to assess a person "holistically" (for admissions, for hiring, for development planning, or for clinical or educational purposes) faces a menu of partially overlapping, differently operationalized instruments with no shared taxonomy. A researcher who wants to compare findings across domains (say, between EI and grit, or between metacognition and learning agility) often finds that shared conceptual ground is implicit rather than documented.

A parallel fragmentation exists on the synthetic side. Classical cognitive architectures (Newell, 1990; Anderson, 2007; Laird, 2012) organized human cognition into modules (working memory, long-term memory, procedural knowledge, a central production system, decision-making) and provided unified theories of cognition grounded in psychology; their shared commitments were later abstracted into the Common Model of Cognition (Laird, Lebiere, & Rosenbloom, 2017), which §2.11 uses as the classical comparator. Recent work on large language model (LLM) agents has revived interest in cognitive architectures as organizing principles for artificial intelligence. Sumers, Yao, Narasimhan, and Griffiths (2024) proposed CoALA (Cognitive Architectures for Language Agents), which organizes language agents along three dimensions: memory modules, structured action space, and decision-making procedure. In early 2026, DeepMind released *Measuring Progress Toward AGI: A Cognitive Framework* (Burnell et al., 2026), a 10-ability taxonomy for evaluating general intelligence in AI systems, drawing on decades of research in psychology, neuroscience, and cognitive science. These efforts share the premise that *some* integrated taxonomy of cognition is necessary, but they disagree on which dimensions to include and at what layer (structural vs. capacity) the decomposition should operate.

### 1.2 Why integration matters for both humans and machines

The case for an integrated capability taxonomy is strongest when human development and AI system design are considered together. Human development practice (coaching, education, talent management) already implicitly draws on multiple frameworks, but the selection is ad hoc and rarely theoretically grounded. A unified map would make the coverage of an assessment explicit and would surface blind spots.

On the synthetic side, the space of cognitive architectures is increasingly shaped by what LLMs make cheap (text generation, pattern completion, associative retrieval) rather than by what general intelligence actually requires. The position taken here is that "general" intelligence in humans requires motivational persistence, emotional regulation, cultural adaptation, and systems thinking in addition to reasoning, memory, and perception; on this view, an architecture that lacks modules or functional equivalents for these capabilities is, by construction, not general. This is the broad-construct view associated with multi-intelligences and triarchic theorists (Gardner, 1983; Sternberg, 1985) and with the EI, CQ, and grit research traditions. It is opposed by the *g*-purist view (Jensen, 1998; Gottfredson, 1997) that confines "intelligence" to cognitive ability proper and treats motivational and affective constructs as personality traits or non-ability factors. We acknowledge this position is contested in the field; HCQM's choice to include motivational and affective capabilities is a position, not a settled consensus. The position is supported empirically by observations that current LLM-based systems show a "jagged" capability profile: strong in pattern completion and factual recall, weak in sustained learning, metacognition, and social cognition (Burnell et al., 2026; Morris et al., 2026).

HCQM's dual-use framing treats this parallelism as a design claim rather than an analogy. A taxonomy that specifies the capacity surface for human cognition should, if correctly constructed, also specify the capacity surface that a synthetic cognitive architecture must cover in order to be general in the same sense humans are. This paper treats the claim operationally: HCQM provides a capability checklist that can be applied to either a human or a synthetic system without modification of the taxonomy itself, only modification of the instruments used.

### 1.3 Contributions

This paper argues for HCQM on three grounds:

First, HCQM consolidates eight top-level capability domains and thirty-three constituent capabilities into a single hierarchical taxonomy, each with defined subcomponents and behavioral indicators. The consolidation is deliberately conservative: almost every capability in HCQM is drawn from an existing, peer-reviewed research tradition. The novelty is in the arrangement, not in the parts.

Second, HCQM includes motivational, emotional, social, cultural, and adversity dimensions as first-class top-level domains, alongside cognitive, executive, creative, learning, digital, and systems domains. Contemporary CHC has itself moved into the affective space: Emotional Intelligence is now included as the Gei broad ability (Schneider & McGrew, 2018), so HCQM's first-class treatment of EQ is best read as alignment with contemporary CHC rather than as an extension beyond it. The extension claim holds for the motivational, social, cultural, and adversity dimensions, which are not represented as CHC broad abilities (though related constructs appear in the trilogy-of-mind frameworks CHC researchers situate alongside the cognitive-ability layer). HCQM is more clearly differentiated from contemporary AI capability frameworks including the Hernández-Orallo and Vold (2019) catalogue (Tolan et al., 2021), the DeepMind 2026 cognitive taxonomy (Burnell et al., 2026), Hendrycks et al. (2025), and the OECD AI Capability Indicators (OECD, 2025), most of which focus on cognitive or mixed cognitive-and-task ability sets without first-class motivational or adversity dimensions. The Hernández-Orallo and Vold (2019) catalogue, associated with the ADeLe evaluation line, is a partial exception and a predecessor: it included emotion, social, and metacognitive abilities, though not motivational, creative, cultural, digital, or systems dimensions (§2.11.6). The coverage asymmetry between these AI frameworks and the human-capability tradition is developed in §2.11.8; the Adversity Quotient's absence from all five AI frameworks is one illustration of it, reported with the qualifications noted there rather than as a load-bearing claim.

Third, HCQM is positioned as a *dual-use capability-grounded framework*. The same taxonomy is intended to function (a) as a holistic instrument for assessing and developing human capability, and (b) as a partial specification target at the capacity layer for synthetic cognitive architectures. "Partial" is deliberate: HCQM specifies *what* an architecture must be capable of in order to cover the human capability surface, but it does not specify *how* (module interfaces, control flow, data representations); §6.6 returns to this distinction and identifies the companion architecture specification as priority future work. The dual-use framing is a design claim: that a capability taxonomy useful for humans should constrain and inform the specification of artificial systems intended to operate in the same functional space. This framing positions HCQM as a *complement* rather than a *competitor* to existing architectural frameworks such as CoALA and evaluative taxonomies such as DeepMind's; it addresses a different layer of the stack (capacity) than architectural frameworks address (structure) and covers a different breadth than cognitive-faculty taxonomies cover (cognitive plus motivational, emotional, cultural, adversity, etc.). The sharpest, most AI-relevant form of this contribution is the **reliability-and-autonomy layer** (§5.2): the AI capability frameworks reviewed here inherit a cognitive-faculty frame and therefore omit the motivational, adaptive, and metacognitive capacities (persistence under failure, strategy revision, self-monitoring, calibration) that determine whether a long-horizon autonomous agent is reliable rather than merely capable. HCQM organizes those capacities as a first-class layer and specifies it as an architecture target, with a worked example mapping a documented agent-failure pattern to the omitted capacities.

We make no claim that HCQM has been empirically validated as an integrated instrument. It has not. We also make no claim that the capabilities it contains are novel; they are not. What HCQM offers is a defensible, citable integration that can serve as a starting point for empirical work and for architecture design.

The remainder of the paper is organized as follows. Section 2 reviews prior work across each capability domain and across the cognitive architecture and AI-capability literature, including direct comparisons to five contemporary frameworks: the Hernández-Orallo and Vold (2019) cognitive-ability catalogue (elaborated in Tolan et al., 2021), CoALA (Sumers et al., 2024), DeepMind 2026 (Burnell et al., 2026), Hendrycks et al. (2025), and the OECD AI Capability Indicators (OECD, 2025). Section 3 articulates the design principles that govern HCQM. Section 4 presents the framework in detail with per-domain theoretical grounding, human-application notes, and synthetic-architecture-application notes. Section 5 discusses applications in human development, AI architecture, and research and evaluation. Section 6 discusses limitations and future work, including an explicit evaluation-protocol gap identified during drafting. Section 7 concludes. Appendices present the full HCQM tree, the indicator catalog, concept-to-source mapping, the CHC broad-ability mapping, and the gradient-match comparisons with each of the contemporary frameworks named above (the ADeLe comparison is reported in §2.11.6; CoALA, DeepMind 2026, Hendrycks 2025, and OECD 2025 in Appendices E, D, G, and H).

---

## 2. Prior Work

This section reviews the research traditions HCQM draws on. Each subsection identifies seminal sources for a capability domain, summarizes the field's internal structure and current debates, and indicates how the domain is represented in HCQM. Two final subsections address the cognitive-architecture literature (§2.11) and synthesize the prior work into a statement of what, specifically, HCQM adds (§2.12).

### 2.1 General cognitive abilities: from factor analysis to CHC

The modern psychometric tradition traces to Spearman's (1904) discovery of positive manifold (the observation that performance across superficially unrelated cognitive tasks is positively correlated) and his proposal of a general factor, *g*. Cattell (1963) and Horn and Cattell (1966) distinguished fluid intelligence (Gf), the ability to solve novel problems without prior domain knowledge, from crystallized intelligence (Gc), accumulated knowledge and vocabulary. Carroll's (1993) *Human Cognitive Abilities: A Survey of Factor-Analytic Studies* reanalyzed over 460 datasets spanning decades of research and proposed a three-stratum model: narrow abilities at the base, broad abilities in the middle (including Gf, Gc, visual processing Gv, auditory processing Ga, short-term memory Gsm, long-term storage/retrieval Glr, processing speed Gs, quantitative knowledge Gq, and reading/writing Grw), and a general factor at the top.

The integration of the Cattell–Horn Gf–Gc extended theory with Carroll's three-stratum model is known as Cattell–Horn–Carroll (CHC) theory (McGrew, 2009; Schneider & McGrew, 2018). CHC is widely regarded as the consensus psychometric model of cognitive abilities and forms the theoretical basis for several contemporary intelligence batteries including the Woodcock-Johnson V, WISC-V, and KABC-II. The taxonomy has been revised since McGrew (2009): in the contemporary integration (Schneider & McGrew, 2018), the short-term memory broad ability was redefined as short-term working memory (Gwm), the older long-term storage and retrieval ability (Glr) was split into Learning Efficiency (Gl) and Retrieval Fluency (Gr), and Emotional Intelligence (Gei) was added as a broad ability (pp. 87–88, 140–141). Debate continues over the empirical status of *g* (Horn consistently argued against it; Carroll and others argued for it; McGrew, 2009 discusses the history), over the boundaries among broad abilities (e.g., whether short-term memory and working memory are separable; whether quantitative knowledge is subsumed under Gc), and over whether further broad abilities (olfactory, tactile, kinesthetic) should be added to the canonical broad-ability set.

Working memory, as distinct from short-term storage, is treated as a separable construct in the Baddeley tradition (Baddeley & Hitch, 1974; Baddeley, 2000), with components for a phonological loop, visuospatial sketchpad, central executive, and episodic buffer. Working memory capacity is a strong correlate of fluid intelligence and a robust predictor of reasoning performance (Engle, 2002).

HCQM Domain 1 (*General Cognitive Intelligence*) draws directly on this tradition. It includes IQ as a composite, Gf and Gc as separable capabilities, visual-spatial intelligence (Gv), processing speed (Gs), working memory (Gwm), and retrieval fluency (Gr, capability 1.7). Emotional Intelligence (Gei), now a CHC broad ability, is located in Domain 3 (3.1) rather than Domain 1. It does not attempt to replicate the full CHC narrow-ability catalog. The CHC broad abilities Ga (auditory processing), Grw (reading/writing), Gh (tactile), Gk (kinesthetic), Go (olfactory), and Gp/Gps (psychomotor) are not represented as separate HCQM capabilities; they are either scoped out (sensory and psychomotor) or partially absorbed into existing capabilities (reading/writing into Gc and Digital Intelligence 7.1). Appendix F contains the full CHC-to-HCQM mapping table, and Section 6.3 discusses the scoping tradeoffs this induces.

### 2.2 Multiple and triarchic intelligences

Gardner's (1983) *Frames of Mind* proposed that intelligence is not a single capacity but a set of relatively independent intelligences: originally linguistic, logical-mathematical, spatial, bodily-kinesthetic, musical, interpersonal, and intrapersonal, with naturalist added later (Gardner, 1999). Gardner's framework has been influential in education and in broadening public conceptions of intelligence, though it has faced criticism from psychometricians for weak empirical grounding; the proposed intelligences do not emerge cleanly from factor-analytic work, and measurement instruments have not matched the rigor of CHC-aligned tests (Waterhouse, 2006).

Sternberg's (1985) triarchic theory distinguished analytical, creative, and practical intelligence. The practical component, in particular, was argued to predict real-world outcomes that purely analytical measures missed. Sternberg's later "successful intelligence" framework (Sternberg, 1999) integrated these three with a self-management overlay.

HCQM does not treat Gardner's intelligences as separate top-level domains, because most of Gardner's categories map onto HCQM's existing structure (linguistic and logical-mathematical under Gc/Gf; spatial under visual-spatial; interpersonal under social intelligence; intrapersonal under emotional intelligence and metacognition). Bodily-kinesthetic and musical are not represented as top-level domains in HCQM; this is a scoping choice, discussed in Section 6.

### 2.3 Emotional intelligence

Salovey and Mayer's (1990) original article *Emotional Intelligence* defined EI as "the subset of social intelligence that involves the ability to monitor one's own and others' feelings and emotions, to discriminate among them and to use this information to guide one's thinking and actions." Mayer, Salovey, and Caruso (2004) developed this into a four-branch ability model: (1) perceiving emotions, (2) using emotions to facilitate thought, (3) understanding emotions, and (4) managing emotions. The Mayer-Salovey-Caruso Emotional Intelligence Test (MSCEIT) operationalizes this model.

Goleman's (1995) *Emotional Intelligence: Why It Can Matter More Than IQ* popularized the construct and extended it with self-awareness, self-regulation, motivation, empathy, and social skill. Goleman's model is more mixed (combining abilities with traits and competencies) and has been criticized by Mayer and others for conceptual sprawl (Mayer, Roberts, & Barsade, 2008).

Salovey and Mayer (1990) also note that emotional intelligence may or may not correlate to other types of intelligence; this should not reflect on its classification as a type of intelligence, though it may reflect on the general *g* model. This implies that emotional intelligence (HCQM Domain 3) interacts with General Cognitive Intelligence (HCQM Domain 1), a relationship HCQM preserves by treating Domain 1 as a partial precursor for perception-side capabilities invoked by Domain 3.

Alexithymia (emotional blindness, the reduced ability to identify and describe one's own emotions) represents a gap in emotional intelligence. It is relevant to both human assessment and AI system design: current LLM-based systems exhibit emotional processing limited by what can be inferred from text, which is a constrained form of alexithymia in the sense that the system cannot directly access embodied emotional signal. HCQM v0.1 does not include alexithymia as an explicit construct; this is flagged as a gap in Section 6.

HCQM Domain 3.1 (Emotional Intelligence) adopts the ability-model structure (emotional awareness, labeling, regulation, empathy, and expression), which is closer to the Mayer-Salovey-Caruso tradition than to Goleman's mixed model. We note the construct-validity debates but do not attempt to adjudicate them here.

### 2.4 Social and cultural intelligence

Thorndike (1920) is typically cited as the first proposer of "social intelligence" (the ability to understand and manage people) as distinct from abstract and mechanical intelligence. Formal operationalization proved difficult and the construct languished for decades before being revived in the 1980s and later. Salovey and Mayer (1990) later characterized social intelligence as the ability to understand people and act in relation, with related framings treating it as the ability to manage or influence the responses of others; this is measurable in part through social knowledge and moral reasoning.

Earley and Ang (2003) introduced cultural intelligence (CQ) in their monograph *Cultural Intelligence: Individual Interactions Across Cultures* (Stanford University Press). CQ is defined as the capability to function effectively in culturally diverse settings, and is decomposed into metacognitive, cognitive, motivational, and behavioral facets (Ang & Van Dyne, 2008). The construct has generated a substantial empirical literature on expatriate effectiveness, cross-cultural teams, and intercultural communication.

HCQM Domain 3 bundles emotional, social, cultural, and interpersonal-awareness capabilities. Social intelligence (3.2) draws on the Thorndike tradition and its later operationalizations; cultural intelligence (3.3) draws directly on Earley and Ang (2003) and Ang and Van Dyne (2008); interpersonal awareness (3.4) represents a finer-grained set of listening, intention-inference, and boundary-sensitivity subcomponents that appear across the social-cognition literature.

Moral and ethical reasoning (Kohlberg, 1969; Rest et al., 1999) is referenced in some social-intelligence operationalizations (including Salovey and Mayer's own early framing) but is not currently represented as a top-level HCQM capability. Section 6 returns to this scoping decision.

### 2.5 Motivational and adaptive constructs

Duckworth, Peterson, Matthews, and Kelly (2007) defined grit as "perseverance and passion for long-term goals" and showed incremental predictive validity over IQ and Big Five conscientiousness in samples including West Point cadets and Scripps National Spelling Bee finalists. The Short Grit Scale (Duckworth & Quinn, 2009) operationalizes two factors: consistency of interest and perseverance of effort. Grit has since been subject to meta-analytic critique (Credé, Tynan, & Harms, 2017), who found that the relationship between grit and performance is weaker than originally claimed and that grit is substantially redundant with conscientiousness.

Dweck's (2006) *Mindset: The New Psychology of Success* distinguished fixed from growth mindsets (beliefs about whether abilities are static or improvable). The mindset construct has generated a large intervention literature with mixed replication outcomes; meta-analyses (Sisk, Burgoyne, Sun, Butler, & Macnamara, 2018) report small effects, and the validity of short-mindset interventions has been contested.

Stoltz (1997) introduced the adversity quotient (AQ) in the popular book *Adversity Quotient: Turning Obstacles into Opportunities*. AQ is framed around four dimensions (Control, Ownership, Reach, and Endurance, abbreviated CORE) intended to predict how individuals respond to setbacks. The construct has generated empirical work primarily in management and educational settings. HCQM includes AQ as a distinct capability because it covers a conceptual space (setback recovery, frustration tolerance under continued effort) that is not substantially captured by grit's long-horizon framing. As a separate matter of coverage, the gradient-match analyses (§2.11.6 and Appendices D, E, G, and H) find AQ to be the only HCQM construct with no direct equivalent in the *intersection* of all five AI frameworks compared in this paper (the Hernández-Orallo and Vold (2019) catalogue, Tolan et al., 2021; CoALA, Sumers et al., 2024; DeepMind 2026, Burnell et al., 2026; Hendrycks et al., 2025; OECD, 2025). This is scoped to those AI frameworks: several other HCQM constructs (EQ, CQ, Curiosity, Grit, and others) also lack equivalents in individual frameworks, the AI frameworks omit motivational capability broadly rather than AQ specifically, and at the human-capability level the AQ construct space overlaps the SENNA SEMS Negative-Emotion-Regulation facet within CAMML (McGrew, 2022). The observation is contingent on AQ being a meaningful capability (an empirical question revisited in §6.1) and is treated as an illustration of the coverage asymmetry (§2.11.8), not as a primary justification for the construct's inclusion.

Curiosity and intrinsic motivation are treated in the self-determination theory tradition (Ryan & Deci, 2000) and in Kashdan's work on curiosity and exploration (Kashdan, Rose, & Fincham, 2004; Kashdan et al., 2018).

HCQM Domain 5 (Motivational & Adaptive Intelligence) consolidates curiosity, adaptability, adversity tolerance, and grit into a single top-level domain. We acknowledge that the empirical standing of these constructs is uneven (grit and curiosity have larger peer-reviewed literatures than adaptability quotient or AQ), and Section 6 returns to this.

### 2.6 Creativity

Guilford (1950), in his APA presidential address, drew attention to the neglect of creativity in psychological research and proposed divergent production as a distinguishing feature. Torrance (1974) developed the Torrance Tests of Creative Thinking (TTCT), scoring fluency, flexibility, originality, and elaboration; the TTCT remains one of the most widely used creativity assessments (Kim, 2006).

Mednick (1962) proposed the associative theory of creativity: creative individuals have flatter associative hierarchies and can therefore retrieve more remote associations. The Remote Associates Test (RAT) operationalizes this. Benedek and Neubauer (2013) revisited Mednick's model and found qualified empirical support.

Runco and Jaeger (2012) identified what they called the "standard definition of creativity" (originality plus usefulness/effectiveness) and argued that novelty alone is insufficient. This bipartite definition is widely cited in contemporary creativity research.

HCQM Domain 4 (Creative & Innovation Intelligence) includes a general Creativity Quotient, Divergent Thinking (Guilford–Torrance tradition), and Associative Thinking (Mednick tradition). The definition of the Creativity Quotient at 4.1 aligns with Runco and Jaeger (2012).

### 2.7 Metacognition and executive functions

Flavell (1979) introduced metacognition as "cognition about cognition" and distinguished metacognitive knowledge, experiences, goals, and actions. Schraw and Moshman (1995) proposed a framework distinguishing tacit, informal, and formal metacognitive theories and differentiated metacognitive knowledge (declarative, procedural, conditional) from metacognitive regulation (planning, monitoring, evaluating). Their 1995 *Educational Psychology Review* article remains a foundational reference, revisited by Moshman (2018) in a follow-up.

Executive functions (the set of top-down control processes including inhibition, working memory updating, and cognitive flexibility) are typically treated in the Miyake tradition (Miyake et al., 2000, "The unity and diversity of executive functions"). Diamond (2013) provides a widely cited review in *Annual Review of Psychology*. Executive functions are empirically related to but separable from general cognitive ability.

HCQM Domain 2 (Executive / Self-Regulatory Intelligence) draws on both literatures. Metacognitive Intelligence (2.1) follows Schraw and Moshman. Cognitive Control (2.2), Cognitive Flexibility (2.3), and Inhibitory Control (2.5) map closely to the Miyake-Diamond executive-function taxonomy. Strategic Planning (2.4) extends into longer-horizon planning, which is treated less centrally in the executive-function literature but is well represented in the problem-solving and planning-AI literatures (Newell & Simon, 1972).

### 2.8 Learning agility and knowledge integration

Learning agility emerged from the leadership-development literature. Lombardo and Eichinger (2000) first operationalized the construct in organizational contexts. De Meuse, Dai, and Hallenbeck (2010), in *Consulting Psychology Journal: Practice and Research*, reviewed the learning-agility literature and defined it as the willingness and ability to learn from experience and apply that learning in novel situations. The construct has four commonly cited facets: mental agility, people agility, change agility, and results agility.

Critiques of the learning-agility literature note that much of the research has been conducted by consulting firms with commercial interests (De Meuse, 2017), and that the construct overlaps substantially with openness to experience and learning orientation.

Knowledge integration and transfer are treated in the educational-psychology and learning-sciences literatures (Bransford, Brown, & Cocking, 2000; Barnett & Ceci, 2002).

HCQM Domain 6 (Learning & Knowledge Intelligence) includes Learning Agility, Knowledge Integration, and Transfer Intelligence. The framing is deliberately broader than the applied-leadership construct of learning agility alone.

### 2.9 Digital intelligence and computational thinking

Park (Ed., 2019) and the DQ Institute proposed a Digital Intelligence (DQ) framework consisting of eight areas (e.g., digital identity, digital use, digital safety, digital security, digital emotional intelligence, digital communication, digital literacy, digital rights) across three levels (citizenship, creativity, competitiveness), adopted as a basis for the IEEE 3527.1 standard for digital intelligence in 2020.

Wing's (2006) *Communications of the ACM* viewpoint introduced computational thinking (CT) as a fundamental skill applicable beyond computer science, later refined (Wing, 2008, 2017) to emphasize problem decomposition, abstraction, pattern recognition, and algorithmic reasoning. CT has been operationalized in assessments such as the Computational Thinking Test (Román-González et al., 2017).

Information literacy and source evaluation are treated in the library-and-information-science literature (ACRL Framework for Information Literacy, 2016).

HCQM Domain 7 (Digital & Technological Intelligence) includes Digital Intelligence (Park/DQ Institute), Information Literacy, and Computational Thinking (Wing).

### 2.10 Systems and strategic thinking

Systems thinking as an organizational and individual capability was popularized by Senge's (1990) *The Fifth Discipline*, which drew on system dynamics (Forrester, 1961) and organizational learning. Meadows' (2008) *Thinking in Systems* provides a widely cited introductory account covering stocks, flows, feedback loops, leverage points, and system archetypes. The academic system-dynamics tradition (Sterman, 2000, *Business Dynamics*) provides more formal grounding.

Strategic thinking as an individual capability is treated in the management literature (Liedtka, 1998) and overlaps substantially with long-horizon planning in executive-function research. Pattern recognition has a lineage in perception research (Gibson, 1979) and in the applied domain of intelligence analysis (Heuer, 1999). Predictive reasoning and forecasting have a robust applied literature (Tetlock, 2005; Tetlock & Gardner, 2015).

HCQM Domain 8 (Systems & Strategic Intelligence) consolidates Systems Intelligence (Senge, Meadows), Strategic Intelligence, Pattern Intelligence, and Predictive Intelligence.

### 2.11 Cognitive architectures and AGI-evaluation taxonomies

Cognitive architectures are computational frameworks that specify the structure, modules, and operating principles of a cognitive system. The canonical synthesis of the classical tradition is the **Common Model of Cognition** (CMC; Laird, Lebiere, & Rosenbloom, 2017; originally the Standard Model of the Mind), a community consensus abstracted from three long-standing architectures, ACT-R (Anderson, 2007), Soar (Laird, 2012; Newell, 1990), and Sigma (Rosenbloom, Demski, & Ustun, 2016). The CMC specifies four core structural components: working memory (a global communication buffer holding the active symbol structures of the current cycle), procedural long-term memory (rule-based knowledge that provides global control), declarative long-term memory (facts and concepts), and perception and motor. Processing is organized around a cognitive cycle, driven by procedural memory, that selects a single deliberate act per cycle (~50 ms in human terms); complex behavior arises from sequences of such cycles rather than from specialized higher-level modules. Declarative memory may be unitary or further decomposed into semantic and episodic stores; the CMC explicitly records that no consensus exists on this split (Laird et al., 2017). ACT-R and Soar instantiate this shared structure differently: ACT-R coordinates modules around a central production system grounded in rational analysis and activation-based retrieval, using a single declarative memory; Soar separates semantic and episodic declarative memories and adds problem spaces, universal subgoaling, and chunking as its control and learning mechanisms. The CMC is the classical tradition's own synthesis and is the appropriate reference point for contrasting architectural approaches against a capacity-layer framework such as HCQM.

The CMC's authors explicitly state that the model "remains incomplete in a number of ways," noting it is "silent... concerning metacognition, emotion, mental imagery, direct communication and learning across modules, the distinction between semantic and episodic memory, and mechanisms necessary for social cognition" (Laird et al., 2017). It is silent altogether on motivational, cultural, adversity, and grit-like dimensions, which do not appear even among the gaps the authors enumerate. Emotion has since been taken up as a proposed extension: Larue et al. (2018), a working group including CMC co-author Rosenbloom, map points of interaction between emotion models and the CMC's structural components, though the group had not reached consensus at time of publication. This work does not address cultural adaptation, adversity tolerance, or grit-like persistence. The coverage gap runs in both directions: the CMC includes perception and motor as core components, which HCQM scopes out (§6.4), while HCQM covers motivational, emotional, cultural, and adversity dimensions on which the CMC is silent. HCQM's contribution against the CMC is therefore this latter set of dimensions, not a strict superset of the CMC's structure.

#### 2.11.1 Predictive Processing and Predictive Intelligence

Predictive processing (Friston, 2010; Clark, 2013) offers a unifying theoretical account of both biological and synthetic cognition. In this framework, the brain is not a passive receiver of sensory data but a hierarchical generative system that continuously produces top-down predictions of environmental states. Perception, learning, and motor control are all recast as minimization of prediction error, in which discrepancies between expected and observed signals drive updating of internal models. The result is a single computational principle spanning multiple levels of the cognitive system.

For synthetic systems, predictive processing maps directly onto the substrate of large language models, which are trained to model the conditional distribution of future tokens given observed context. This parallel clarifies a common failure mode in both systems: when contextual grounding is absent or ambiguous, top-down generative predictions can dominate bottom-up evidence, producing outputs that are internally coherent but factually incorrect. In humans, the analogous condition is known as confabulation or source-monitoring failure; in LLM-based systems, it is the hallucination phenomenon documented extensively in the literature (Ji et al., 2023). HCQM's Predictive Intelligence construct (8.4) operates at the capacity layer of this mechanism, assessing how accurately a system's predictive outputs track external reality rather than describing the computational substrate itself.


#### 2.11.2 CoALA (Sumers et al., 2024)

The LLM era has revived interest in cognitive architectures as organizing principles for language agents. Sumers, Yao, Narasimhan, and Griffiths (2024) proposed **CoALA** (Cognitive Architectures for Language Agents), published in *Transactions on Machine Learning Research* (arXiv:2309.02427). CoALA organizes language agents along three dimensions:

1. **Memory modules.** Working memory (active variables in the current decision cycle, persisting across LLM calls), episodic memory (stored experience/event sequences), semantic memory (knowledge about the world and self), and procedural memory (implicit knowledge in LLM weights plus explicit knowledge in agent code).
2. **Structured action space.** Internal actions on memory: reasoning (reads/writes working memory), retrieval (reads from long-term memory), and learning (writes to long-term memory). External grounding actions: physical (sensors/actuators), dialogue (with humans or other agents), and digital (APIs, code, websites, games).
3. **Decision-making procedure.** An interactive loop of planning (proposal → evaluation → selection) and execution, in which planning may iterate and use reasoning plus retrieval to build multi-step simulations before committing to an action.

CoALA is the closest antecedent to HCQM's architecture-side framing. It retrospectively organizes a large body of LLM-agent work and prospectively identifies gaps. However, CoALA operates at the *architectural* layer (components, data flow, control flow), while HCQM operates at the *capability/measurement* layer (latent traits, behavioral indicators). These layers are complementary rather than competing: CoALA specifies structural slots; HCQM specifies what capacities fill or execute within those slots. Wray, Kirk, and Laird (2025) extend this thread by articulating recurring cognitive design patterns found in both classical and LLM-based architectures.

A gradient-match analysis of HCQM coverage against all 14 CoALA sub-concepts (4 memory types, 3 internal action types, 3 grounding types, 4 decision stages) is reported in Appendix E. The summary finding: every CoALA sub-concept has at least a partial HCQM mapping (0 full matches, 8 strong, 6 partial, 0 none). The reverse coverage is asymmetric: 10 HCQM constructs (primarily in Domains 3, 4, 5, and parts of 8) have zero or weak CoALA equivalents. This asymmetry is the positioning claim: HCQM extends beyond what architectural frameworks like CoALA cover, particularly along motivational, emotional, cultural, and adversity dimensions.

#### 2.11.3 DeepMind 2026 cognitive taxonomy

Most directly relevant to HCQM's evaluation framing is DeepMind's *Measuring Progress Toward AGI: A Cognitive Framework* (Burnell et al., 2026), released on March 17, 2026. The paper proposes a cognitive taxonomy of 10 abilities: **perception, generation, attention, learning, memory, reasoning, metacognition, executive functions, problem solving, and social cognition**, drawn from decades of research in psychology, neuroscience, and cognitive science. The framework is accompanied by an evaluation protocol in which AI systems are benchmarked against representative human samples to produce a "cognitive profile," generating three artifacts: a cognitive assessment, human baselines, and per-system cognitive profiles. It is paired with a Kaggle hackathon targeting the five abilities with the largest evaluation gaps (**learning, metacognition, attention, executive functions, and social cognition**) with a $200,000 prize pool. The framework explicitly scopes itself as a starting point for *breadth of coverage* of human cognition, not as the definitive account of all cognition.

A gradient-match analysis of HCQM coverage against the DeepMind 10 cognitive faculties is reported in Appendix D. Summary findings:

- **Strong alignment.** DeepMind's attention maps to HCQM 2.2 (Cognitive Control); metacognition to HCQM 2.1 (Metacognitive Intelligence); executive functions to HCQM Domain 2 broadly; reasoning to HCQM 1.1–1.2 and parts of Domain 8; memory to HCQM 1.3 and 1.6; learning to HCQM 6.1–6.3; social cognition to HCQM 3.1–3.2 and partially 3.4.
- **HCQM covers what DeepMind does not.** Cultural Intelligence (3.3), Creative & Innovation Intelligence (Domain 4), Motivational & Adaptive Intelligence (Domain 5, particularly Grit and Adversity Quotient), Digital & Technological Intelligence (Domain 7), and Systems & Strategic Intelligence (Domain 8) are not substantially represented in the DeepMind taxonomy.
- **DeepMind covers what HCQM does not.** Perception (sensory processing) and Generation (output production) are not directly represented in HCQM. These omissions are deliberate in HCQM's scoping: HCQM focuses on cognitive and affective capability structure above the sensory and output levels. For embodied AI systems, HCQM would need to be extended at its boundaries with sensory-processing and action-generation layers.

HCQM differs from the DeepMind 2026 framework in two important ways. First, HCQM covers motivational, emotional, cultural, adversity, creative, digital, and systems dimensions that the DeepMind 10-ability taxonomy either does not address or treats only indirectly. Second, HCQM's purpose is both evaluative and partially prescriptive at the capacity layer: it is intended not only as a way to score existing systems but as a capacity-surface specification target for architecture design, with the explicit limitation noted in §6.6 that full architectural prescriptiveness requires a companion specification document. DeepMind's framework is purely evaluative.

A calibration on scope is warranted. CHC is a taxonomy of *cognitive* abilities by design; it does not claim to cover non-cognitive capabilities and cannot be faulted for not doing so. HCQM is therefore best positioned as *extending beyond* the cognitive-ability scope that CHC (by design) and the DeepMind 10-faculty taxonomy (by choice) restrict themselves to. This is a scope difference, not a defect in the prior frameworks.

Recent analyses of chain-of-thought reasoning have documented unfaithfulness phenomena in which models produce structurally articulate reasoning traces that do not reliably reflect their actual computation (Korbak et al., 2025). Such findings are consistent with the DeepMind framing of metacognition and executive functions as evaluation-gap areas and are recorded here as context for HCQM's treatment of Metacognitive Intelligence (§2.7, §4.2) rather than as evidence about HCQM itself.

#### 2.11.4 Hendrycks et al. (2025): A Definition of AGI

Hendrycks et al. (2025), in *A Definition of AGI* (arXiv:2510.18212), propose an operational definition of AGI as a system that matches "the cognitive versatility and proficiency of a well-educated adult." The framework is explicitly grounded in Cattell–Horn–Carroll (CHC) theory and dissects general intelligence into ten equally weighted (10% each) cognitive domains: General Knowledge (Gc/Gkn), Reading and Writing Ability (Grw), Mathematical Ability (Gq), On-the-Spot Reasoning (Gf), Working Memory (Gwm), Long-Term Memory Storage, Long-Term Memory Retrieval, Visual Processing (Gv), Auditory Processing (Ga), and Speed (Gs). Each domain is operationalized through adapted human psychometric batteries. The paper reports a strongly "jagged" cognitive profile in contemporary models (GPT-4 at 27% aggregate score; GPT-5 at 57%), with proficiency in knowledge-intensive domains but pronounced deficits in foundational cognitive machinery: both models score 0% on Long-Term Memory Storage and 0% on the Hallucinations/Retrieval Precision sub-faculty of Long-Term Memory Retrieval.

The Hendrycks framework is the closest contemporary parallel to HCQM Domain 1 (General Cognitive Intelligence) in its CHC grounding, but it is also a useful comparison point for HCQM's broader scope claim. Three observations follow:

1. **Scope.** Hendrycks et al. (2025) restrict their definition of AGI to *cognitive* faculties, in the CHC sense. They do not include motivational, emotional, social-cultural, adversity, or systems-thinking dimensions. This is a deliberate scoping choice grounded in the empirical maturity of CHC, not an oversight, but it means the Hendrycks definition shares the same cognitive-only boundary as the DeepMind (2026) framework (§2.11.3) and CHC itself (§2.1).
2. **Methodological alignment.** The use of adapted human psychometric batteries to score AI systems is methodologically aligned with HCQM's assessment-readiness principle (§3.3) and with the DeepMind three-stage protocol (§2.11.3). For Domain 1 evaluation under HCQM, the Hendrycks battery adaptations are direct candidates for instrument-level operationalization.
3. **Jaggedness convergence.** The finding that current models exhibit a "jagged" capability profile (strong in knowledge, weak in foundational machinery such as long-term memory) converges with the comparable jaggedness finding in Burnell et al. (2026) and Morris et al. (2026). HCQM treats this convergence as cross-validation of the broader observation that uniform AGI-progress claims are not supported by current evidence; the per-capability decomposition that HCQM offers is consistent with what these AGI-evaluation frameworks report empirically.

A gradient-match analysis of HCQM coverage against the Hendrycks ten cognitive domains is reported in Appendix G. Summary: Hendrycks's ten cognitive domains map primarily onto HCQM Domain 1 (six of ten Hendrycks domains correspond directly to Domain 1 constructs via shared CHC grounding), with partial extensions into Domain 2 (Cognitive Flexibility, Strategic Planning via R sub-faculties) and Domain 3 (Theory of Mind via R). Six HCQM constructs have zero Hendrycks equivalent at any sub-faculty level: 2.5 Inhibitory Control, 5.1 Curiosity Quotient, 5.3 Adversity Quotient, 5.4 Grit / Persistence, 7.1 Digital Intelligence, and 8.1 Systems Intelligence. HCQM Domains 4 (Creative & Innovation), 5 (Motivational & Adaptive), 7 (Digital & Technological), and 8 (Systems & Strategic) are not substantially represented in the Hendrycks taxonomy. Adversity Quotient (5.3) has no direct equivalent in the Hendrycks framework, mirroring its status in the Hernández-Orallo and Vold (2019) catalogue (Tolan et al., 2021), DeepMind (2026), CoALA (Sumers et al., 2024), and the OECD (2025) capability indicators (see §2.11.8).

#### 2.11.5 OECD AI Capability Indicators (2025)

The OECD (2025) *Introducing the OECD AI Capability Indicators*, developed over approximately five years by a working group of more than 50 experts, organizes AI capability measurement around nine human-grounded ability domains: language, social interaction, problem solving, creativity, metacognition and critical thinking, knowledge/learning/memory, vision, manipulation, and robotic intelligence. Each domain is presented on a five-level scale where Level 1 corresponds to limited or basic functionality and Level 5 corresponds to full human capacity. The report locates the most advanced LLMs at Level 2 for metacognition and critical thinking and at Level 3 for creativity, with social interaction and creativity assessed primarily through expert judgment due to limited formal benchmarks.

The OECD indicators are useful as a HCQM comparison point for three reasons:

1. **Policy-facing taxonomy.** Unlike DeepMind (2026) and Hendrycks et al. (2025), which are AI-research artifacts, the OECD framework is designed for policymakers. Its operational level is therefore coarser (nine domains, five levels) than HCQM's hierarchical decomposition. This is appropriate to its purpose; HCQM's finer-grained capability and indicator levels remain available for technical evaluation, while the OECD level can support governance and disclosure use cases.
2. **Inclusion of perception and manipulation.** The OECD framework includes vision and manipulation as distinct domains, which HCQM scopes out (§6.4). This convergent inclusion in a major policy framework is one of several signals that HCQM's omission of sensory and motor boundaries should be reconsidered for embodied-AI use cases.
3. **Coverage gap consistency.** The OECD framework, like DeepMind (2026) and Hendrycks et al. (2025), does not include motivational, adaptive, cultural, adversity, or systems-strategic dimensions as first-class abilities. This is the third independent contemporary AI capability framework with this gap. The convergence supports HCQM's positioning claim: motivational, adaptive, cultural, and adversity capabilities are not currently treated as first-class in mainstream AI evaluation frameworks, regardless of whether the framework is academic (Hendrycks, DeepMind) or intergovernmental (OECD).

A gradient-match analysis of HCQM coverage against the nine OECD domains is reported in Appendix H. Summary: OECD's nine domains map onto HCQM Domains 1, 2, 3 (social interaction subset), 4 (creativity), 6 (knowledge/learning/memory), and 7 (problem solving overlap). HCQM Domains 5 (Motivational & Adaptive), 8 (Systems & Strategic), and the cultural and adversity subcomponents of Domain 3 are not represented in the OECD framework. Vision and manipulation are OECD-side additions not represented in HCQM.

#### 2.11.6 The Hernández-Orallo and Vold (2019) cognitive-ability catalogue

Hernández-Orallo and Vold (2019) introduced a cognitive-ability catalogue of 14 abilities for evaluating natural and artificial systems; the construct is associated with the ADeLe line of ability-oriented AI evaluation. It was more fully elaborated and applied to occupational AI exposure by Tolan, Pesole, Martínez-Plumed, Fernández-Macías, Hernández-Orallo, and Gómez (2021) in *Measuring the Occupational Impact of AI* (*Journal of Artificial Intelligence Research*, 71, 191–236), and subsequently adopted with modifications (knowledge abilities added; auditory processing removed) in the *Nature* study of Zhou et al. (2026), which extends the ADeLe evaluation line. It is the earliest of the AI-capability frameworks compared in this paper and a direct predecessor to the ability-oriented framing that DeepMind (2026), Hendrycks et al. (2025), and the OECD (2025) later adopted. Like HCQM, it is dual-use by design: its rubric is written to apply to "a robot or a human."

The 14 abilities, grouped by the object operated on, are: **people**, Emotion and self-control (EC), Mind-modelling and social interaction (MS), Metacognition and confidence assessment (MC), Communication (CO); **ideas**, Comprehension and expression (CE), Planning and sequential decision-making (PA), Memory processes (MP), Attention and search (AS), Conceptualisation, learning and abstraction (CL), Quantitative and logical reasoning (QL); **things**, Sensorimotor interaction (SI), Navigation (NV), Visual processing (VP), Auditory processing (AP).

Three design choices bear on the comparison. First, the catalogue deliberately excludes general intelligence, creativity, and personality traits (the Big Five) as either too general or simulable by changing objective functions, and it excludes working memory from its Memory-processes ability, which covers only long-term and episodic memory. Second, it draws its broad-ability level from the Cattell-Horn-Carroll model as stated at its 2021 writing, using the pre-2018 codes Gsm and Glr; HCQM adopts the Schneider and McGrew (2018) revision (Gwm; the Gl/Gr split) and is correspondingly more granular on the memory axis (working memory at 1.6, retrieval fluency at 1.7, learning efficiency in Domain 6). Third, ADeLe's dual-use is for *evaluation* (occupational AI exposure), whereas HCQM's dual-use framing targets *architecture specification* at the capacity layer.

A gradient-match analysis of HCQM coverage of the 14 abilities in the catalogue, using the same rubric as Appendices D, E, G, and H, is reported in full in Appendix I. Summary: 0 full, 8 strong, 3 partial, 1 weak, 2 none. HCQM covers 12 of 14 at partial-or-better. The two with no HCQM equivalent (Auditory processing, Navigation) and the one weak match (Sensorimotor interaction) fall on the sensory-motor boundary HCQM deliberately scopes out (§6.4), convergent with the perception and manipulation gaps noted for DeepMind (2026) and the OECD (2025).

Reverse coverage is the more important direction for positioning. The Hernández-Orallo and Vold catalogue has no equivalent for HCQM Domain 4 (Creative & Innovation; creativity is explicitly excluded), Domain 5 (Motivational & Adaptive: curiosity, adaptability, adversity, grit; excluded as conative or personality constructs), Cultural Intelligence (3.3), Digital & Technological Intelligence (Domain 7), or Systems Intelligence (8.1) and Pattern Intelligence (8.3). It is, however, the broadest of the five AI frameworks on the affective, social, and metacognitive axis: its EC, MS, and MC abilities included emotion, social cognition, and metacognition as AI-evaluable abilities in 2019, before the later frameworks did. HCQM's differentiation against it therefore does not rest on broadening beyond pure cognition, which the Hernández-Orallo and Vold work already did, but specifically on the motivational, creative, cultural, digital, and systems dimensions, on the four-level hierarchical structure, and on the architecture-specification form of its dual-use framing. The full standalone gradient-match analysis, in parity with Appendices D, E, G, and H, is in Appendix I.

#### 2.11.7 HCQM as a mapping target for AI-evaluation protocols

As AI systems are increasingly deployed as autonomous agents operating within architectural frameworks such as CoALA (Sumers et al., 2024), monolithic static benchmarks (e.g., MMLU, GSM8K) capture a narrowing slice of relevant capability. HCQM's subcomponent-level decomposition can be used as a mapping target for Stage 1 of the DeepMind 2026 three-stage protocol; that is, the construction of a broad suite of cognitive tasks corresponding to specific capability nodes. Executive-function evaluation, for example, can be assembled by mapping existing tasks to HCQM's Inhibitory Control (2.5), Cognitive Control (2.2), and Working Memory Capacity (1.6) subcomponents.

Social-cognition evaluation is one area where HCQM's broader scope is directly applicable: HCQM's SQ (3.2) and CQ (3.3) subcomponents can support the design of multi-agent simulation environments that evaluate coalition dynamics, role inference, and cross-cultural communication. The Mafiascum dataset (de Ruiter & Kachergis, 2018), originally constructed for textual deception detection, is one candidate substrate for SQ-related evaluation in multi-player social-inference settings, although adaptation to controlled evaluation conditions is itself research work.

Metacognitive evaluation is similarly amenable to HCQM-anchored measurement. The Metacognitive Intelligence (2.1) subcomponents, particularly confidence calibration and reflection quality, provide assessment targets distinct from raw task accuracy, including the detection of models that produce articulate but unfaithful chain-of-thought traces (Korbak et al., 2025).

These uses do not constitute a complete HCQM evaluation protocol; that is identified as future work in §6.7. They illustrate how HCQM's capability granularity is intended to support evaluation design rather than replace it.

#### 2.11.8 The coverage asymmetry between AI frameworks and the human-capability tradition

The central positioning observation of this paper is an asymmetry, not a uniqueness claim about any single construct. The human-capability tradition covers motivational, affective, cultural, and adversity-related capability: contemporary CHC includes Emotional Intelligence as the Gei broad ability (Schneider & McGrew, 2018), and motivational and affective constructs are situated alongside the cognitive layer in the trilogy-of-mind frameworks (Snow's aptitude complexes; Ackerman's PPIK; McGrew's CAMML, 2022). The five contemporary AI cognitive and capability frameworks compared in this paper (the Hernández-Orallo and Vold (2019) catalogue, Tolan et al., 2021; CoALA, Sumers et al., 2024; DeepMind 2026, Burnell et al., 2026; Hendrycks et al., 2025; OECD, 2025) largely do not, with one partial exception noted below. The gradient-match analyses (§2.11.6 and Appendices D, E, G, H) show motivational and adaptive capability (HCQM Domain 5), along with the cultural, creative, digital, and systems dimensions, to be the least represented HCQM region across all five. HCQM's contribution at this layer is to port that human-side coverage into a single capacity-layer specification target for AI architectures and evaluations that systematically omit it. The omitted dimensions are not a miscellaneous remainder: they concentrate in the motivational, adaptive, and metacognitive capacities that govern long-horizon agent reliability, which §5.2 develops as HCQM's distinctive AI-facing contribution (the reliability-and-autonomy layer).

The partial exception is the Hernández-Orallo and Vold (2019) catalogue, associated with the ADeLe evaluation line, which, alone among the five, included emotion (EC), social interaction (MS), and metacognition (MC) as first-class AI-evaluable abilities, and did so earliest. HCQM does not claim priority over this work for the move beyond pure cognition; it is a predecessor on that axis. HCQM's distinct coverage is narrower and specific: the motivational, creative, cultural, digital, and systems dimensions, which the catalogue also omits (it excludes creativity and conative or personality constructs by design).

The Adversity Quotient (HCQM 5.3) illustrates the gap rather than constituting the differentiator. Per the gradient-match analyses, it is the only HCQM construct with zero direct equivalent across all five AI frameworks simultaneously. This observation is reported with three qualifications. First, the AI frameworks omit a wide range of motivational constructs by design (Grit, Curiosity, and others are also absent from most of them; see Appendix E.5 and §2.11.6); AQ is distinctive only in being absent from all five at once, which is an intersection property rather than evidence that AQ is the most important missing capability. Second, the observation is scoped to these AI frameworks and is not a uniqueness claim against the human-capability tradition, where the AQ construct space (frustration tolerance, stress modulation) overlaps the Negative-Emotion-Regulation facet of the SENNA SEMS model within CAMML (McGrew, 2022). Third, it is conditional on AQ being a meaningful, separable construct, the empirical status of which is uneven (see §2.5 and §6.1). The durable differentiators of HCQM are the integrative arrangement and the dual-use capacity-layer framing (§2.12), not the coverage status of any individual construct.

![[HCQM-comparison.png]]

**Figure 2.** HCQM domain coverage across five contemporary AI capability frameworks: CoALA (Sumers et al., 2024), DeepMind 2026 (Burnell et al., 2026), Hendrycks et al. (2025), the OECD AI Capability Indicators (2025), and the Hernández-Orallo and Vold (2019) catalogue (Tolan et al., 2021), the last labelled "ADeLe" in the figure after the ability-oriented evaluation line it is associated with. Domain 5 (Motivational & Adaptive Intelligence) is the least represented HCQM region across all five frameworks (no match in any), illustrating the coverage asymmetry between these AI frameworks and the human-capability tradition (§2.11.8). Domain 1 (General Cognitive Intelligence) is the only domain with full coverage across them. Coverage ratings: full (direct construct-level equivalent), partial (sub-faculty or distributed coverage), weak (implicit or marginal), absent (entirely missing). Detailed gradient-match analyses in §2.11.6 and Appendices D, E, G, H, and I.

### 2.12 Synthesis: what HCQM adds

The prior work surveyed above establishes three things. First, each of HCQM's capability domains is independently supported by a mature research literature. Second, no existing taxonomy integrates all eight domains into a single hierarchical structure with defined subcomponents and indicators. CHC covers general cognitive and (partially) executive dimensions; EI and CQ literatures cover emotional and cultural; grit and mindset literatures cover motivational; creativity literatures cover creative; DQ and CT literatures cover digital; systems-thinking literatures cover systems. Each of these traditions operates largely in isolation. Third, recent cognitive and AI-capability frameworks (classical: the Common Model of Cognition (CMC; Laird, Lebiere, & Rosenbloom, 2017), which unifies ACT-R (Anderson, 2007), Soar (Laird, 2012), and Sigma (Rosenbloom et al., 2016); agent-architectural: CoALA; and AGI-evaluative: DeepMind 2026, Hendrycks et al. 2025, OECD AI Capability Indicators 2025) provide partial templates for how a capability taxonomy can be translated into architecture specification or evaluation protocol, but none covers the full surface HCQM addresses, and each addresses a different layer of the stack.

HCQM's contribution is therefore specifically:

1. **Integration.** Pulling the above literatures into a single hierarchical taxonomy with uniform structural treatment (domain → capability → subcomponent → indicator).
2. **Coverage asymmetry between the human-capability tradition and AI frameworks.** The human-capability tradition treats motivational, affective, cultural, and adversity capability as first-class: contemporary CHC includes Emotional Intelligence (Gei; Schneider & McGrew, 2018), and motivational and affective constructs are situated alongside the cognitive layer in the trilogy-of-mind frameworks (Snow's aptitude complexes; Ackerman's PPIK; McGrew's CAMML, 2022). Contemporary AI capability frameworks largely do not. The clearest partial exception is the Hernández-Orallo and Vold (2019) catalogue (Tolan et al., 2021), which included emotion, social, and metacognitive abilities first and earliest; the others (CoALA, DeepMind 2026, Hendrycks et al. 2025, OECD 2025) cover narrower cognitive or mixed cognitive-and-task sets, and none of the five covers the motivational, creative, cultural, digital, and systems dimensions. HCQM brings the human-side coverage to bear as a capacity-layer specification target for the AI side. This is a scope claim about AI frameworks, not a claim of novelty against the human-capability tradition: HCQM's emotional dimension is CHC-aligned, and the motivational and adversity dimensions exist in the trilogy-of-mind literature. What HCQM adds is the consolidation and the porting, not the discovery of these constructs.
3. **Dual-use framing at the capacity layer.** The same taxonomy is intended for both human-development assessment and synthetic-architecture specification, at the level of *what a system must be capable of* rather than *how it is implemented*. HCQM does not replace CoALA (structural), DeepMind/Hendrycks (evaluative-cognitive), or OECD (policy-evaluative); it specifies the capacity surface that those frameworks either structurally implement or evaluate against. We note (and revisit in §6.6) that the dual-use framing is a design claim, not an empirical equivalence proof, and that full architectural prescriptiveness will require a companion specification document beyond the taxonomy itself.

The two durable differentiators are the **integration** (contribution 1) and the **dual-use capacity-layer framing** (contribution 3); the coverage asymmetry (contribution 2) is what those two are applied to. Their sharpest, most AI-relevant expression is the **reliability-and-autonomy layer** (§5.2): the motivational, adaptive, and metacognitive capacities the AI frameworks omit are exactly those that govern long-horizon agent reliability, which positions HCQM not as another capability checklist but as a specification of the capacities a generally capable agent must have to be *reliable*, not merely *capable*. Coverage observations about individual constructs, including the Adversity Quotient's absence from all five AI frameworks (§2.11.8), are illustrations of that asymmetry and are not load-bearing for the paper's contribution.

**A note on predictive contribution.** HCQM does not claim incremental predictive validity over the union of its source constructs; that is an empirical question (§6.1) that the present paper does not attempt to answer. The contribution claimed here is integrative rather than predictive: a coverage map and a scaffold for instrument design and architecture specification. A future empirical study could test whether HCQM-aligned assessment batteries predict outcomes that individual source instruments do not, but this paper does not present such evidence and does not rely on it.

The next section articulates the design principles that govern how this integration was done.

---

## 3. Design Principles

HCQM was designed according to five explicit principles: (1) *hierarchical structure* to reflect both breadth and depth (inspired by CHC strata); (2) *integration over invention*, grounding every element in prior peer-reviewed literature; (3) *assessment-readiness* via observable behavioral indicators; (4) *architecture-readiness* to serve as a capacity-surface specification for cognitive-system design; and (5) *domain selection criteria* that prioritize coverage of capabilities shown to predict real-world success across human and machine contexts. Detailed rationale and decision matrices for domain selection are identified as future-revision work (§6.9).

### 3.1 Hierarchical structure

HCQM uses a four-level hierarchy: domain → capability → subcomponent → indicator. Domains are broad functional areas of cognitive and affective operation (e.g., executive/self-regulatory intelligence). Capabilities are the constructs that appear in the named-quotient literature (e.g., metacognitive intelligence, cognitive control). Subcomponents are the finer-grained abilities used in operationalization (e.g., self-monitoring, error detection). Indicators are observable behavioral markers that can anchor assessment items.

Hierarchical structure is adopted for three reasons. First, it matches the dominant structural choice in psychometrics (CHC's three-stratum model; Carroll, 1993; McGrew, 2009) and in the DeepMind 2026 taxonomy, which itself organizes abilities hierarchically. Second, it supports partial adoption: a practitioner who cares only about certain domains can work at the domain or capability level without being forced to engage with every subcomponent. Third, it makes coverage claims explicit; gaps become visible as missing branches.

![[HCQM.png]]

**Figure 1.** HCQM schematic: eight top-level domains and thirty-three constituent capabilities. Subcomponents and behavioral indicators for each construct are detailed in Appendix A.

### 3.2 Integration over invention

HCQM is a synthesis framework. The strong preference throughout its construction is to use existing, well-sourced capabilities rather than to invent new ones. Every capability in HCQM Section 4 maps back to one or more prior sources; the mapping is documented in Appendix C.

This principle has two consequences. First, where two traditions describe similar capabilities under different names (e.g., "self-monitoring" in metacognition research and "self-awareness" in EI research), HCQM keeps them separated when the field keeps them separated, because collapsing them would obscure the source literatures. Second, where a prior construct is contested or weakly validated (e.g., adversity quotient relative to grit; mindset effect sizes in intervention studies), HCQM includes the construct but flags the validation gap in Section 6.

### 3.3 Assessment-readiness

Each capability in HCQM is accompanied by subcomponents and indicators designed to support operationalization. HCQM does not itself provide validated instruments; it is a taxonomy, not a test battery. But the indicator level is intended to be specific enough that existing instruments can be mapped onto it (e.g., MSCEIT branches onto EI subcomponents; Grit-S onto Grit/Persistence subcomponents; the Metacognitive Awareness Inventory onto Metacognitive Intelligence subcomponents), and new instruments can be developed against it.

HCQM v0.1 does not specify an integrated evaluation protocol. This is a known gap. The DeepMind 2026 framework pairs its taxonomy with a three-stage protocol (conduct cognitive assessment; collect human baselines; build cognitive profiles). A comparable protocol for HCQM, covering both human and synthetic systems and specifying how capability scores should be aggregated, normalized, and compared, is identified as future work in Section 6.

### 3.4 Architecture-readiness

HCQM is designed so that each capability is also a candidate specification for a module or capability in a synthetic cognitive architecture. The CoALA framework (Sumers et al., 2024) illustrates how a memory/action/decision decomposition can be mapped to LLM-agent design; HCQM's broader decomposition specifies the capacity surface that such architectures are expected to implement, and extends the expected surface to emotional, motivational, cultural, and systems dimensions that CoALA does not address. Architecture-readiness imposes two constraints on the taxonomy: (a) capabilities must be describable at a level that admits computational operationalization, not only behavioral operationalization; and (b) the taxonomy must be modular enough that capabilities can be implemented or omitted independently, to support incremental architecture development. The sharpest application of architecture-readiness is the reliability-and-autonomy layer developed in §5.2.

A related constraint, identified during the gradient-match analysis with CoALA, is that HCQM capabilities have two facets: **static capacity** (a latent trait that can be measured at a point in time) and **dynamic process** (a capacity enacted within a decision loop). HCQM v0.1 treats capabilities primarily at the static-capacity level. Architecture-ready use may require explicit process-level annotation that specifies how a capability participates in an iterative decision loop of the sort CoALA describes. This is identified as future work.

### 3.5 Domain selection criteria

The eight top-level domains were selected using three criteria: (1) the existence of a mature peer-reviewed or widely adopted applied literature supporting the domain as a distinct capability area; (2) coverage of capabilities commonly invoked in holistic human-development contexts (education, hiring, coaching, clinical assessment); and (3) relevance to current debates about what general intelligence requires in synthetic systems. Domains were excluded if they failed any of these criteria. For example, bodily-kinesthetic and musical intelligences from Gardner's framework are not represented as top-level domains, because their relevance to general intelligence in AI systems is weak and because their measurement tradition is narrower. Section 6 revisits these scoping decisions as limitations.

---

## 4. The HCQM Framework

This section presents each of HCQM's eight top-level domains. For each domain we state the definition, enumerate the constituent capabilities, summarize the theoretical grounding, and describe how the domain is expected to manifest in human assessment and in synthetic-system design. Subcomponents and indicators are catalogued in Appendix A; the full source-to-capability mapping is in Appendix C.

### 4.1 Domain 1: General Cognitive Intelligence

**Definition.** Raw mental power for reasoning, understanding, and manipulating information.

**Capabilities.** IQ (general cognitive ability), Fluid Intelligence (Gf), Crystallized Intelligence (Gc), Visual-Spatial Intelligence (Gv), Processing Speed (Gs), Working Memory Capacity (Gwm), Retrieval Fluency (Gr).

**Theoretical grounding.** This domain is the most directly inherited from an existing taxonomy: it is essentially a compressed CHC broad-ability layer (Cattell, 1963; Horn & Cattell, 1966; Carroll, 1993; McGrew, 2009; Schneider & McGrew, 2018). IQ is treated as a composite rather than as a separate construct from Gf and Gc, following the standard psychometric position that IQ batteries measure *g* through the covariance of broad abilities. This composite treatment is consistent with contemporary network and emergent-property accounts (Protzko & Colom, 2021; van der Maas et al., 2019; McGrew, Schneider, Decker, & Bulut, 2023) that treat psychometric *g* as an emergent statistical regularity of the positive manifold rather than a separable underlying construct. Working memory is treated separately from short-term storage following Baddeley and Hitch (1974) and Baddeley (2000), and is treated as part of the Gwm-AC (working-memory plus attentional-control) complex identified in McGrew et al. (2023). HCQM omits the CHC narrow-ability layer for parsimony. A practitioner or architect who needs narrow-ability specification can substitute the CHC narrow abilities directly; the HCQM capability layer is compatible with that substitution.

**Relationship to CHC broad abilities.** Gf → 1.2; Gc → 1.3; Gwm (short-term working memory) → 1.6; Gv → 1.4; Gs and Gt (decision/reaction speed) → 1.5; Gl (Learning Efficiency, formerly part of Glr) → partially 1.3 via semantic-memory overlap, with capacity-layer correspondence in Domain 6; Gr (Retrieval Fluency, formerly part of Glr) → 1.7; Gq (quantitative knowledge) → partially 1.1 and 1.3; Gkn (general domain-specific knowledge) → 1.3; Gei (Emotional Intelligence) → 3.1 Emotional Intelligence (located in Domain 3, not here). CHC broad abilities not represented in Domain 1: Ga (auditory), Grw (reading/writing), Gh (tactile), Gk (kinesthetic), Go (olfactory), Gp (psychomotor), Gps (psychomotor speed). The full mapping is in Appendix F. Per McGrew (2009) and Schneider and McGrew (2018), the older Glr broad ability was officially split into Gl and Gr; HCQM adopts the split, and the Gr correspondence is placed in Domain 1 as 1.7 (McGrew, personal communication, 2026-05-29).

**Human application.** Domain 1 capabilities are assessed by established psychometric batteries (Wechsler, Woodcock-Johnson V, KABC-II). Scores are typically reported as normalized IQ-scale scores or percentile ranks. The Working Memory Capacity construct (1.6) can be measured by span tasks (digit span, Corsi block) and *n*-back tasks; Gf by matrix-reasoning tasks (Raven's Progressive Matrices); Gc by vocabulary and general-knowledge tests; Gs by symbol-search and coding tasks.

**Synthetic application.** Gf maps onto novel problem-solving capacity in AI systems (the ability to solve problems outside the training distribution). Gc maps onto the knowledge encoded in model weights plus any retrieval-augmented knowledge store (cf. CoALA semantic memory; Sumers et al., 2024). Gv maps onto visual processing modules in multimodal systems. Gs maps onto inference latency and throughput. Working memory maps onto the context window plus any active-state buffer the system maintains across reasoning steps (cf. CoALA working memory, which emphasizes persistence-across-LLM-calls as the operational definition). This domain is where HCQM and CoALA align most cleanly at the structural level, and where the DeepMind 2026 "memory" and "reasoning" faculties provide direct evaluation targets.

**Known gaps and overlap flags.** The Working Memory indicator "resists losing track under interruption" overlaps in phrasing with the Cognitive Control (2.2) indicator "stays focused despite noise or interruption." This redundancy is flagged in Section 6.2. McGrew et al. (2023) report a unified Gwm-AC (working-memory plus attentional-control) complex in their network analysis, which is supporting evidence that HCQM's separation of Working Memory (1.6, Domain 1) and Cognitive Control (2.2, Domain 2) may be partly artificial; this is flagged as a candidate for future architectural review. The CoALA distinction between *read* and *write* operations on memory is not currently captured in HCQM's working-memory treatment, which frames capacity as a single quantity rather than separating encoding from retrieval; this is a candidate refinement for future work (see §6.9, item 4).

| **Subcategory**                      | **Description & Theoretical Alignment**                                                                                                                                                                  | **Observable Performance Indicators**                                                                                                                                          |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **IQ (general cognitive ability)**   | Aggregate reasoning capacity across cognitive tasks, treated as a *g*-loaded composite of broad CHC abilities rather than a separable construct. Consistent with the emergent-property account of *g* in McGrew et al. (2023). Grounded in Carroll (1993) and McGrew (2009).           | Solves unfamiliar problems accurately; detects underlying rules quickly; understands complexity with limited explanation; handles multi-variable reasoning effectively.        |
| **Fluid Intelligence (Gf)**          | Capacity to solve novel problems independent of acquired knowledge. Aligns with CHC's broad fluid-reasoning ability (Cattell, 1963; Carroll, 1993).                                                      | Performs well in unfamiliar environments; infers structure from sparse data; adapts reasoning when rules change; builds new mental models fluently.                             |
| **Crystallized Intelligence (Gc)**   | Depth, breadth, and accuracy of accumulated domain knowledge and semantic memory. Aligns with CHC's broad crystallized-knowledge ability (Horn & Cattell, 1966; Schneider & McGrew, 2018).               | Explains concepts clearly; draws on relevant prior knowledge; uses terminology accurately; recognizes deep analogies from experience.                                          |
| **Working Memory Capacity (Gwm)**    | Cognitive workspace for temporarily holding and actively manipulating information; attentional control is considered a key feature of working memory capacity (Engle, 2002; McGrew et al., 2023). Grounded in Baddeley and Hitch (1974) and Baddeley (2000).                                                                        | Keeps track of multiple variables at once; holds steps in mind during complex reasoning; maintains context during long chains of thought; resists losing track under interruption. |
| **Processing Speed (Gs)**            | Speed of perceiving, comparing, and responding to information. Aligns with CHC's broad processing-speed ability (Carroll, 1993).                                                                          | Completes routine cognitive tasks rapidly; maintains pace under information density; quickly notices relevant differences; responds with low lag in structured tasks.          |
| **Visual-Spatial Intelligence (Gv)** | Ability to perceive, imagine, rotate, and manipulate spatial relationships. Aligns with CHC's broad visual-processing ability (Carroll, 1993).                                                            | Understands diagrams and layouts quickly; visualizes object movement in space; maps relationships between parts and wholes; excels in geometry, design, or 3D reasoning.       |
| **Retrieval Fluency (Gr)**           | Ease and breadth of retrieving stored information from long-term memory. Encompasses the Gr narrow-ability cluster: ideational fluency, associational fluency, word fluency, expressional fluency, figural fluency, and naming facility. Aligns with CHC's Retrieval Fluency broad ability as separated from Gl in Schneider and McGrew (2018). | Retrieves relevant information without hesitation; produces a wide range of associations to a given prompt; accesses stored vocabulary, names, or concepts fluidly; generates many responses to open-ended cues across categories. |

### 4.2 Domain 2: Executive / Self-Regulatory Intelligence

**Definition.** Control layer for attention, behavior, goals, and thinking processes.

**Capabilities.** Metacognitive Intelligence (MQ), Cognitive Control, Cognitive Flexibility, Strategic Planning, Inhibitory Control.

**Theoretical grounding.** Metacognitive Intelligence draws on Flavell (1979) and Schraw and Moshman (1995), with subcomponents (self-monitoring, error detection, strategy selection, self-regulation, learning optimization, confidence calibration, reflection) that cover both Schraw-Moshman's regulation-of-cognition category and confidence-calibration work from the judgment-and-decision-making literature (Koriat, 1993). Cognitive Control, Cognitive Flexibility, and Inhibitory Control correspond closely to Miyake et al.'s (2000) three-factor executive-function model (updating, shifting, inhibition) as refined in Diamond (2013). Strategic Planning extends into longer-horizon planning (goal decomposition, contingency planning, time-horizon reasoning), which is treated in the problem-solving and planning literatures (Newell & Simon, 1972).

**Relationship to executive function taxonomy.** Miyake's three core executive functions map as follows: Inhibition → 2.5 (Inhibitory Control) and partially 2.2 (Cognitive Control); Working Memory (updating) → 1.6 (Working Memory Capacity, located in Domain 1 rather than here); Cognitive Flexibility (shifting) → 2.3 (Cognitive Flexibility). The higher-order executive functions Miyake and Diamond describe (reasoning, problem solving, planning) map to 1.1 (IQ), 1.2 (Fluid Intelligence), and 2.4 (Strategic Planning), respectively. HCQM's hierarchical separation between basic executive capacity (in Domain 2) and higher-order reasoning (in Domain 1) is a deliberate design choice: it allows independent evaluation of the control layer and the reasoning substrate it operates on.

**Human application.** Metacognitive Intelligence can be assessed using instruments such as the Metacognitive Awareness Inventory (Schraw & Dennison, 1994). Executive functions are typically assessed by neuropsychological tasks (Stroop, Wisconsin Card Sorting Test, Trail Making, Go/No-Go) and by self-report or informant-report scales such as the BRIEF (Behavior Rating Inventory of Executive Function; Gioia, Isquith, Guy, & Kenworthy, 2000). Strategic Planning is less well measured by standard executive-function batteries and is often assessed via project-management, goal-pursuit, or in-basket simulations.

**Synthetic application.** Metacognitive Intelligence maps onto self-monitoring and self-critique loops in LLM agents (e.g., chain-of-verification, self-consistency, confidence-calibration prompting). Cognitive Control maps onto attention mechanisms and focus preservation in long-context reasoning. Cognitive Flexibility maps onto task-switching and reframing capacity, including the ability to revise a plan when new information arrives. Strategic Planning maps onto explicit planning modules (CoALA's planning stage: proposal → evaluation → selection) and hierarchical task decomposition. Inhibitory Control maps onto refusal policies, output-filtering, and the suppression of low-quality fast responses in favor of deliberative ones.

Inhibitory control in AI systems has a dual character: it includes both the suppression of undesirable outputs (safety-style filtering) and the inhibition of premature closure in reasoning (selecting a better answer over the first plausible one). In practice, these may compete for the same compute budget. Explicit inhibition rules consume context that would otherwise be available for reasoning, creating a tradeoff between output-quality constraints and available reasoning capacity.

CoALA's decision-making loop (proposal, evaluation, selection, execution) distributes across this domain and Domain 4 and 8. Proposal uses Divergent Thinking (4.2) and Strategic Planning (2.4); evaluation uses Predictive Intelligence (8.4) and Metacognitive Intelligence (2.1); selection uses Strategic Intelligence (8.2) and Inhibitory Control (2.5); execution uses Cognitive Control (2.2) and Strategic Planning (2.4). This is the domain where HCQM and the DeepMind (2026) taxonomy overlap most cleanly: DeepMind's "metacognition" and "executive functions" both appear here, and DeepMind explicitly identifies both as evaluation-gap areas.

**Known gaps and overlap flags.** Metareasoning (the allocation of reasoning compute before committing to an answer) is flagged in CoALA §6 as an understudied open direction. HCQM has no explicit construct for metareasoning; it partially overlaps with 2.1 (Metacognitive Intelligence) but deserves a dedicated subcomponent (candidate: *2.1.x Cognitive resource allocation / reasoning budget control*). This is recorded as future work.

| **Subcategory**                     | **Description & Theoretical Alignment**                                                                                                                                                                                | **Observable Performance Indicators**                                                                                                                                                |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Metacognitive Intelligence (MQ)** | Awareness and regulation of one's own thinking processes. Grounded in Flavell (1979) and Schraw and Moshman (1995).                                                                                                    | Notices when understanding is weak; detects mistakes before external feedback; switches strategy when current approach fails; evaluates certainty realistically.                     |
| **Cognitive Control**               | Ability to direct attention toward task-relevant goals; the attentional-control facet of the Miyake et al. (2000) executive-function model as refined in Diamond (2013).                                                | Stays focused despite noise or interruption; maintains task direction over time; filters irrelevant stimuli effectively; avoids frequent context drift.                              |
| **Cognitive Flexibility**           | Capacity to shift between mental models, rules, or perspectives; the *shifting* facet of Miyake et al. (2000).                                                                                                          | Adapts quickly to changing demands; reframes problems productively; avoids rigid attachment to one model; handles exceptions without breaking down.                                  |
| **Strategic Planning**              | Ability to sequence actions toward long-range objectives via goal decomposition, sequencing, and contingency planning. Extends the planning literature of Newell and Simon (1972).                                      | Works backward from desired outcomes; anticipates dependencies and bottlenecks; allocates effort where leverage is highest; maintains coherence across multiple steps.               |
| **Inhibitory Control**              | Ability to suppress impulses or incorrect default responses; the *inhibition* facet of Miyake et al. (2000) and Diamond (2013).                                                                                         | Pauses before reacting; avoids low-quality quick answers; resists distraction or temptation; suppresses emotionally driven missteps.                                                 |

### 4.3 Domain 3: Emotional & Social Intelligence

**Definition.** Capacity to understand emotions, relationships, and social systems.

**Capabilities.** Emotional Intelligence (EQ), Social Intelligence (SQ), Cultural Intelligence (CQ), Interpersonal Awareness.

**Theoretical grounding.** EQ follows the ability model of Mayer, Salovey, and Caruso (2004) rather than the mixed model of Goleman (1995), though we acknowledge that many applied assessments draw on Goleman, and corresponds to CHC Emotional Intelligence (Gei) as added to the integrated CHC taxonomy in Schneider and McGrew (2018, pp. 87–88, 140–141). Social Intelligence follows the Thorndike (1920) tradition and its later operationalizations. Cultural Intelligence draws directly on Earley and Ang (2003) and Ang and Van Dyne (2008), preserving the metacognitive/cognitive/motivational/behavioral four-facet structure at the subcomponent level. Interpersonal Awareness covers listening depth, intention inference, boundary sensitivity, and relational memory: subcomponents that appear across the social-cognition, theory-of-mind, and active-listening literatures.

**Relationship to CHC.** Contemporary CHC includes Emotional Intelligence (Gei) as a broad ability (Schneider & McGrew, 2018, pp. 87–88, 140–141), to which HCQM 3.1 Emotional Intelligence corresponds directly. HCQM 3.1's sub-construct decomposition (emotional awareness, labeling, regulation, empathy, expression) was cross-checked against the published Gei structure, which follows the Mayer–Salovey–Caruso perceive/understand/manage/use ability model, and found consistent. Social Intelligence (3.2), Cultural Intelligence (3.3), and Interpersonal Awareness (3.4) are not represented as CHC broad abilities at the time of writing, though related constructs appear in the broader trilogy-of-mind frameworks that contemporary CHC researchers situate alongside the cognitive-ability layer (Snow's aptitude complexes; McGrew, 2022, CAMML).

**Relationship to General Cognitive Intelligence.** As noted in Section 2.3, Salovey and Mayer (1990) observed that emotional intelligence may or may not correlate with other types of intelligence. HCQM treats this relationship as a partial precursor: some Domain 3 subcomponents (e.g., emotional labeling, social cue reading) depend on Domain 1 capabilities (Gc for vocabulary; Gv for perception of facial and postural cues). This does not collapse the domains; it means Domain 3 capability is conditional on, but not reducible to, Domain 1 capability.

**Human application.** EQ can be assessed via the MSCEIT (ability-based; Mayer, Salovey, & Caruso, 2002) or the EQ-i (mixed-model, self-report; Bar-On, 1997). CQ is typically measured via the CQS (Cultural Intelligence Scale; Ang et al., 2007). Social Intelligence and Interpersonal Awareness are less standardized; they are often measured by behavior-based assessment, 360-degree feedback, or observational rubrics. Alexithymia (reduced ability to identify and describe one's own emotions) can be assessed via the Toronto Alexithymia Scale (Bagby, Parker, & Taylor, 1994), and is a recognized gap in Domain 3.1 that HCQM v0.1 does not currently treat as a distinct subcomponent.

**Synthetic application.** EQ maps onto affective computing capabilities: emotion recognition from text, voice, or face; emotionally appropriate response generation; and emotion-regulated agent behavior. Current LLM-based systems exhibit a functional analogue of what is clinically described as alexithymia (Bagby, Parker, & Taylor, 1994): they cannot directly access embodied emotional signal and must rely on textual or multimodal inference. The analogy is structural rather than clinical; LLMs are not patients, and the term is used here to describe a measurable input-modality limitation, not a diagnosis. Closing this gap in synthetic systems requires either (a) richer input modalities that capture emotional signal beyond text, or (b) explicit emotion-state modeling beyond surface pattern-matching. SQ maps onto dialogue and multi-agent coordination (reading status, role, and intent within a conversation). CQ is typically treated as a training-data property in current systems (cultural variation enters the distribution of the corpus rather than the system architecture; see Atari et al., 2023, on WEIRD bias in LLMs and AlKhamissi et al., 2024, on cultural alignment) rather than as an architected capability, which leaves it brittle: a system cannot reliably adapt to an unfamiliar cultural frame outside its training distribution, and does not reliably detect when it is operating in one. Interpersonal Awareness maps onto long-horizon relational memory (remembering prior interactions with a specific user, tracking their stated preferences, and respecting boundaries across sessions; cf. CoALA episodic memory).

This domain is one of the primary differentiators between HCQM and the DeepMind 2026 framework. DeepMind includes "social cognition" as one of its ten abilities but does not separately elaborate cultural intelligence, which has a substantial independent research base. It is also one of the primary differentiators between HCQM and CoALA, which addresses dialogue only as a grounding action type without treating emotional, cultural, or relational-depth capability as architecturally distinct.

**Known gaps.** Alexithymia is not represented as a subcomponent. Moral and ethical reasoning (Kohlberg, 1969; Rest et al., 1999) is not represented as a separate capability; current treatment is distributed across Strategic Intelligence (tradeoff evaluation) and Metacognitive Intelligence (reflection quality). Both are flagged in Section 6.

| **Subcategory**                 | **Description & Theoretical Alignment**                                                                                                                                                                          | **Observable Performance Indicators**                                                                                                                                              |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Emotional Intelligence (EQ)** | Ability to perceive, understand, regulate, and use emotions effectively. Follows the ability model of Mayer, Salovey, and Caruso (2004); corresponds to CHC Gei (Schneider & McGrew, 2018).                                                                          | Identifies emotional states accurately; manages emotional intensity under stress; responds rather than reacts; understands emotional signals in self and others.                  |
| **Social Intelligence (SQ)**    | Ability to interpret and navigate social dynamics effectively. Follows the Thorndike (1920) tradition and its later operationalizations.                                                                          | Reads group dynamics accurately; adjusts communication to audience and context; recognizes hidden motives and incentives; navigates disagreement without unnecessary escalation.   |
| **Cultural Intelligence (CQ)**  | Ability to operate effectively across cultures and norm systems. Grounded in Earley and Ang (2003) and Ang and Van Dyne (2008).                                                                                   | Recognizes culture-bound assumptions; adapts behavior to different contexts appropriately; avoids misreading unfamiliar norms; communicates effectively across backgrounds.        |
| **Interpersonal Awareness**     | Fine-grained understanding of others' needs, intentions, and boundaries; composite of listening depth, intention inference, and relational memory from the social-cognition and theory-of-mind literatures.       | Notices subtle shifts in tone or engagement; tracks relational context over time; detects unspoken needs or concerns; respects and navigates interpersonal limits well.            |

### 4.4 Domain 4: Creative & Innovation Intelligence

**Definition.** Capacity to generate useful novelty and transform it into workable ideas.

**Capabilities.** Creativity Quotient, Divergent Thinking, Associative Thinking.

**Theoretical grounding.** The Creativity Quotient is defined consistently with Runco and Jaeger's (2012) "standard definition of creativity": outputs must be both original and useful/effective. Divergent Thinking draws on Guilford (1950) and Torrance (1974), with subcomponents (ideational fluency, flexibility, originality, possibility expansion) that map directly onto the TTCT scoring rubric. Associative Thinking draws on Mednick (1962) and the Remote Associates Test tradition, as extended by Benedek and Neubauer (2013). Convergent thinking is represented implicitly through the "usefulness" component of the Creativity Quotient rather than as a separate capability, since convergent thinking in the Guilford tradition overlaps substantially with reasoning capabilities already covered in Domain 1 (Gf).

**Relationship to CHC.** Creativity is not represented as a broad ability in contemporary CHC. Carroll (1993) tentatively included narrow creativity abilities in his three-stratum work but flagged them as tentative, and they have since been dropped from the CHC literature (McGrew, personal communication, 2026-05-29). The narrow fluency abilities under CHC Gr (Retrieval Fluency): ideational, associational, word, expressional, and figural fluency, facilitate creative production and are a component of it, but they are not the core essence of creativity as defined in the creativity literature (Runco & Jaeger, 2012; Guilford, 1950; Mednick, 1962); they are placed in HCQM 1.7 Retrieval Fluency rather than in Domain 4. Domain 4 therefore extends beyond the contemporary CHC broad-ability structure, drawing on the Guilford–Torrance divergent-thinking tradition, Mednick's associative-thinking tradition, and the Runco–Jaeger and Amabile consensual-assessment traditions as its primary theoretical grounding.

**Human application.** Divergent Thinking is typically assessed by the TTCT (Torrance, 1974) or the Alternate Uses Test. Associative Thinking is assessed by the RAT (Mednick). The Creativity Quotient as a composite is assessed only indirectly, typically via consensual-assessment rubrics (Amabile, 1982) or expert panels on actual creative products.

**Synthetic application.** Creativity capabilities map onto generation diversity, novelty of output, and the ability to recombine distant concepts. Divergent Thinking maps onto temperature-and-sampling behavior plus explicit prompting for option generation; current LLM systems can generate many plausible options but do not reliably filter for usefulness without additional scaffolding. Associative Thinking maps onto cross-domain analogy generation (the ability to find structural similarities between unrelated domains). This is partially native to LLMs (associative retrieval over training corpora) but not reliably controlled. The Creativity Quotient, as defined by Runco-Jaeger (novelty + usefulness), requires the system to hold both criteria simultaneously; current evaluation methods are weak, as the DeepMind 2026 paper acknowledges regarding the difficulty of isolating and evaluating creativity objectively in AI systems.

This domain has no direct equivalent in CoALA and weak representation in the DeepMind 2026 taxonomy (the DeepMind paper treats creativity as an open measurement problem rather than a distinct faculty). HCQM's inclusion of creativity as a first-class domain follows the human-capability research tradition rather than current AGI-evaluation practice.

| **Subcategory**          | **Description & Theoretical Alignment**                                                                                                                                                                                       | **Observable Performance Indicators**                                                                                                                                |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Creativity Quotient**  | Composite capacity for generating outputs that are both original and useful, per the standard definition of creativity (Runco & Jaeger, 2012). Treated as a higher-order construct over divergent and associative subcomponents. | Produces ideas that are both novel and relevant; generates options under constraints; builds raw ideas into stronger concepts; avoids cliché solution patterns.       |
| **Divergent Thinking**   | Ability to produce multiple possible answers or directions through ideational fluency, flexibility, and possibility expansion. Grounded in Guilford (1950) and Torrance (1974).                                              | Generates many plausible alternatives; shifts angles without fixation; moves beyond first-obvious answers; produces broad option sets quickly.                       |
| **Associative Thinking** | Ability to connect distant concepts into meaningful combinations through analogical reasoning and cross-domain linkage. Grounded in Mednick (1962) and Benedek and Neubauer (2013).                                          | Connects ideas across unrelated domains; finds hidden structural similarities; creates coherent syntheses from distant concepts; produces unconventional but valid insights. |

### 4.5 Domain 5: Motivational & Adaptive Intelligence

**Definition.** Capacity to sustain effort, adapt under change, and recover under stress.

**Capabilities.** Curiosity Quotient, Adaptability Quotient, Adversity Quotient, Grit / Persistence.

**Theoretical grounding.** Grit follows Duckworth et al. (2007) and the Short Grit Scale (Duckworth & Quinn, 2009), with subcomponents distinguishing consistency of interest from perseverance of effort. Adversity Quotient follows Stoltz (1997). Adaptability Quotient draws on the organizational-adaptability literature, including Ployhart and Bliese (2006) on the I-ADAPT taxonomy, as well as change-management research. Curiosity Quotient draws on Kashdan et al. (2004, 2018) and on the self-determination theory tradition (Ryan & Deci, 2000).

**Relationship to CHC.** The CHC broad-ability structure does not include motivational, adaptive, or persistence constructs at the broad-ability layer. Contemporary trilogy-of-mind frameworks (Snow's aptitude complexes; Ackerman's PPIK; McGrew's CAMML, 2022) situate motivational and conative constructs alongside the cognitive-ability layer rather than within it, and HCQM Domain 5 corresponds most closely to that conative layer. Substantive integration with CAMML and the Snow aptitude-complex tradition is identified as a future-work priority.

**Human application.** Grit is assessed by the Grit-S (Duckworth & Quinn, 2009). Curiosity is assessed by the Five-Dimensional Curiosity Scale (Kashdan et al., 2018). Adaptability Quotient and Adversity Quotient have less consolidated measurement traditions than grit and curiosity; most operationalizations are from applied management or consulting contexts and have weaker peer-reviewed validation.

**Synthetic application.** This is the HCQM domain with the weakest correspondence to current AI architectural patterns and the strongest claim to be a genuine prescriptive contribution. Curiosity Quotient maps onto intrinsic motivation mechanisms: exploration bonuses in reinforcement learning, active-learning queries, or explicit curiosity drives that push an agent toward high-information or novel states. Adaptability Quotient maps onto the ability to revise strategy when the environment changes and to transfer skills across contexts (related to but distinct from Learning Agility in Domain 6). Adversity Quotient has no canonical implementation pattern; it would need to be engineered as explicit persistence policies over long-horizon tasks. For example, policies for recovering from partial failures, handling repeated errors without collapsing to default behaviors, and maintaining task commitment when rewards are delayed or sparse. A user-contributed note frames this in computational terms: "computational stress" (e.g., resource pressure, failure accumulation) could be a monitored state, with learned recovery policies that preserve output quality by reducing processing speed, reducing computational complexity, or increasing retrieval-augmented generation for accuracy, rather than degrading gracefully or terminating. Grit / Persistence maps onto sustained goal commitment across long-horizon tasks, which contemporary agent loops (including those in the CoALA tradition) do not reliably implement; most LLM agents terminate early or drift off-task over long executions.

This domain is one of HCQM's clearest differentiators from cognitive-ability-first taxonomies. General-intelligence batteries do not measure motivational persistence; the DeepMind 2026 framework does not list it as a core cognitive faculty; CoALA does not specify motivational state as an architectural component. HCQM treats it as first-class because (a) parts of the empirical literature support some incremental predictive validity for grit and curiosity above cognitive-ability measures (Duckworth et al., 2007; Kashdan et al., 2018), although the size of this incremental effect has been meta-analytically attenuated relative to the original claims (Credé, Tynan, & Harms, 2017) and overlap with conscientiousness is substantial; and (b) any synthetic architecture aiming at long-horizon task performance under failure conditions will require functional equivalents of motivational persistence even if their psychometric structure within humans remains contested.

**Note on AQ coverage.** Per the comparative analyses across all five AI capability frameworks compared in this paper (§2.11.6 and Appendices D, E, G, H), Adversity Quotient (5.3) is the only HCQM construct with no direct equivalent in the intersection of the Hernández-Orallo and Vold (2019) catalogue (Tolan et al., 2021), CoALA, DeepMind 2026, Hendrycks et al. (2025), and the OECD (2025) capability indicators. This is a coverage observation about those AI frameworks, not a uniqueness claim against the human-capability tradition: the AQ construct space (frustration tolerance, stress modulation) overlaps the Negative-Emotion-Regulation facet of the SENNA SEMS model within CAMML (McGrew, 2022), and the AI frameworks omit motivational constructs broadly rather than AQ specifically (CoALA alone omits several; see Appendix E.5). AQ's distinctiveness is the *five-framework intersection* property, contingent on AQ being a meaningful capability, an empirical question Section 6 addresses as a limitation. It illustrates the coverage asymmetry developed in §2.11.8 and is not, on its own, a differentiating contribution of the paper.

| **Subcategory**             | **Description & Theoretical Alignment**                                                                                                                                                                | **Observable Performance Indicators**                                                                                                                              |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Curiosity Quotient**      | Drive to explore, question, and seek understanding beyond instrumental need. Grounded in epistemic-curiosity research (Kashdan et al., 2004, 2018) and self-determination theory (Ryan & Deci, 2000).   | Asks high-quality questions; pursues understanding beyond surface answers; explores new domains voluntarily; maintains inquiry despite ambiguity.                  |
| **Adaptability Quotient**   | Ability to adjust effectively to new demands, tools, and conditions; context sensitivity and change tolerance. Draws on the organizational-adaptability literature (Ployhart & Bliese, 2006).            | Recovers quickly after change; learns new systems without extended resistance; modifies behavior to fit new constraints; operates effectively in ambiguity.        |
| **Adversity Quotient (AQ)** | Ability to withstand setbacks, pressure, and difficulty; frustration tolerance, stress endurance, and recovery capacity. Grounded in the CORE dimensions of Stoltz (1997).                              | Continues functioning under pressure; bounces back after failure; does not collapse after setbacks; maintains effort despite discomfort.                            |
| **Grit / Persistence**      | Sustained effort and commitment toward long-term goals; consistency of interest plus perseverance of effort. Grounded in Duckworth et al. (2007) and Duckworth and Quinn (2009).                          | Continues work across long time horizons; resists quitting during plateaus; maintains focus on valued goals; invests effort when rewards are delayed.              |

### 4.6 Domain 6: Learning & Knowledge Intelligence

**Definition.** Capacity to acquire, integrate, retain, and transfer knowledge.

**Capabilities.** Learning Agility, Knowledge Integration, Transfer Intelligence.

**Theoretical grounding.** Learning Agility follows De Meuse, Dai, and Hallenbeck (2010) and the broader leadership-development literature, with subcomponents (feedback uptake, rapid skill acquisition, experimentation, self-correction) consistent with their four-facet model. Knowledge Integration draws on the schema-formation and conceptual-change literatures (Chi & Ohlsson, 2005). Transfer Intelligence draws on Barnett and Ceci (2002) on the conditions of transfer and on the expert-novice literature.

**Relationship to CHC.** Contemporary CHC (Schneider & McGrew, 2018) splits the older Glr broad ability into two distinct broad abilities: Gl (Learning Efficiency, the rate and quality of acquiring new information) and Gr (Retrieval Fluency, the speed and breadth of retrieving stored information). HCQM Domain 6 corresponds to the capacity-layer expression of Gl: Learning Agility (6.1), Knowledge Integration (6.2), and Transfer Intelligence (6.3) are the behavioral surface of what Gl captures as the underlying broad ability. McGrew et al. (2023) note that the WJ IV operationalization of Gl (Visual-Auditory Learning, Story Recall) has measurement-validity concerns; HCQM's broader behavioral framing complements narrow-ability work still in motion in contemporary CHC research. Gr, the second component of the former Glr, is placed in Domain 1 as 1.7 Retrieval Fluency rather than here.

**Human application.** Learning Agility is typically assessed by self-report or 360-degree instruments developed in applied leadership contexts (e.g., Choices Architect®, now rebranded as Learning Agility Architect™ under Korn Ferry; Lombardo & Eichinger, 2000) and by separate academic instruments such as the Learning Agility Assessment Inventory (LAAI) developed at Teachers College, Columbia University. Knowledge Integration and Transfer Intelligence are typically assessed via educational-assessment methods such as transfer problems, analogical-reasoning tasks, and near-vs-far transfer paradigms.

**Synthetic application.** Learning Agility maps onto in-context learning (few-shot adaptation), online fine-tuning capacity, and the ability of a deployed system to update from feedback during operation. This is a capability gap in current LLM systems: most are static after training, though tool-use, retrieval augmentation, and agent-loop feedback integration provide partial workarounds. Knowledge Integration maps onto synthesis across retrieved sources, contradiction reconciliation, and the construction of consistent mental models from fragmented information. Transfer Intelligence maps onto out-of-distribution generalization, cross-domain analogical application, and the abstraction of reusable principles. CoALA's *learning* action type (writing to long-term memory: episodic, semantic, or procedural) is an architectural correlate but does not exhaust the capacity-level decomposition here; a system may have the *architectural slot* for learning without strong *capacity* in it.

This domain is closely related to DeepMind's (2026) "learning" ability (one of the five DeepMind evaluation-gap areas) but is broader: DeepMind's learning targets acquisition from experience and instruction, while HCQM's Learning & Knowledge domain also covers synthesis, schema formation, and cross-context application. CoALA's memory decomposition (episodic, semantic, procedural) suggests that HCQM may benefit from adding explicit episodic-memory and procedural-memory constructs to this domain; this is flagged as future work.

| **Subcategory**             | **Description & Theoretical Alignment**                                                                                                                                                          | **Observable Performance Indicators**                                                                                                                                |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Learning Agility**        | Speed and quality of learning from experience and feedback; feedback uptake, rapid skill acquisition, and self-correction. Capacity-layer expression of CHC Gl (Learning Efficiency; Schneider & McGrew, 2018). Grounded in De Meuse, Dai, and Hallenbeck (2010) and De Meuse (2017). | Learns quickly from mistakes; improves performance after feedback; experiments without excessive hesitation; transfers lessons across attempts.                     |
| **Knowledge Integration**   | Ability to combine separate information into coherent mental models; synthesis, schema formation, and contradiction reconciliation. Draws on the schema-formation literature (Chi & Ohlsson, 2005). | Combines fragmented information into a whole; builds stable conceptual frameworks; resolves conflicts between ideas productively; understands relationships between concepts. |
| **Transfer Intelligence**   | Ability to apply knowledge from one context to another; principle extraction, analogical transfer, and abstraction. Grounded in Barnett and Ceci (2002).                                          | Applies lessons from one domain to another; recognizes reusable principles; adapts known methods to new problems; moves from examples to general rules.              |

### 4.7 Domain 7: Digital & Technological Intelligence

**Definition.** Capability to operate effectively in digital, informational, and computational environments.

**Capabilities.** Digital Intelligence (DQ), Information Literacy, Computational Thinking.

**Theoretical grounding.** Digital Intelligence follows the Park/DQ Institute framework (Park, 2019), which itself is the basis for the IEEE 3527.1 standard. The HCQM subcomponents (digital fluency, platform navigation, digital identity awareness, cyber-risk awareness) are a compressed mapping of DQ's eight areas at the digital-citizenship level. Information Literacy draws on the ACRL Framework and on the source-evaluation literature (Wineburg & McGrew, 2019). Computational Thinking follows Wing (2006, 2008, 2017), with the canonical subcomponents of decomposition, pattern recognition, abstraction, and algorithmic reasoning.

**Human application.** DQ is assessed in the DQ Institute's own instruments and in the IEEE 3527.1 standard framework. Information Literacy is assessed via source-evaluation tasks and by educational instruments developed in library-and-information-science contexts (SAILS, TRAILS). Computational Thinking is assessed via the Computational Thinking Test (Román-González et al., 2017) and related instruments.

**Synthetic application.** Digital Intelligence maps onto the ability of an AI system to operate in digital environments: use APIs, navigate web interfaces, understand platform norms and risks, protect its own credentials and state from misuse. This aligns closely with CoALA's digital-grounding action type, with the addition of risk and identity awareness that CoALA does not centrally address. Information Literacy maps onto source evaluation in retrieval-augmented systems (distinguishing strong from weak sources, verifying claims before accepting them, handling conflicting evidence productively). This is a central capability gap in LLM-based systems, which have a documented tendency toward confident but inaccurate assertion (hallucination); see the survey by Ji et al. (2023) and the calibration evidence in Lin, Hilton, and Evans (2022). Computational Thinking maps onto the ability to decompose a problem into algorithmic steps, recognize patterns that can be automated, and produce structured solutions.

Digital intelligence is absent from the DeepMind 2026 cognitive taxonomy, likely because it is partly culturally and contextually scoped rather than purely cognitive. HCQM includes it because (a) contemporary human-development practice requires it, and (b) synthetic systems operating in digital environments inherit analogous requirements for platform literacy, information verification, and security awareness.

| **Subcategory**               | **Description & Theoretical Alignment**                                                                                                                                                                            | **Observable Performance Indicators**                                                                                                                                                                  |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Digital Intelligence (DQ)** | Broad digital fluency, judgment, and effectiveness; platform navigation, digital identity awareness, and cyber-risk awareness. Defined by the DQ Institute (Park, 2019) and basis for the IEEE 3527.1 standard.    | Uses digital tools effectively; understands platform norms and risks; protects data and account integrity; learns software environments quickly.                                                       |
| **Information Literacy**      | Ability to find, assess, verify, and synthesize information; source evaluation, credibility filtering, and bias detection. Grounded in the ACRL Framework (2016) and Wineburg and McGrew (2019).                   | Distinguishes strong from weak sources; verifies claims before accepting them; handles conflicting evidence productively; avoids being misled by confidence alone.                                     |
| **Computational Thinking**    | Ability to structure problems in logical, modelable, automatable ways; decomposition, abstraction, pattern recognition, and algorithmic reasoning. Grounded in Wing (2006, 2008, 2017).                              | Breaks large problems into manageable parts; recognizes repeatable logic patterns; converts messy processes into structured flows; designs stepwise solutions that can be executed or automated.       |

### 4.8 Domain 8: Systems & Strategic Intelligence

**Definition.** Capacity to understand interdependent systems and act effectively across time.

**Capabilities.** Systems Intelligence, Strategic Intelligence, Pattern Intelligence, Predictive Intelligence.

**Theoretical grounding.** Systems Intelligence draws on Senge (1990), Meadows (2008), and the system-dynamics tradition (Forrester, 1961; Sterman, 2000). Subcomponents include causal mapping, feedback-loop recognition, interdependence awareness, constraint recognition, and leverage-point detection: concepts drawn directly from Meadows (2008). Strategic Intelligence draws on the strategic-management and competitive-strategy literatures (Liedtka, 1998), with subcomponents covering objective clarity, positioning, tradeoff evaluation, sequencing, and long-horizon reasoning. Pattern Intelligence and Predictive Intelligence draw on the forecasting and judgment literatures (Tetlock, 2005; Tetlock & Gardner, 2015) and on applied work in intelligence analysis (Heuer, 1999).

**Human application.** Systems Intelligence is assessed via systems-thinking rubrics that include stock-flow distinction tasks (Booth Sweeney & Sterman, 2000) and causal-loop diagramming (Sterman, 2000; Meadows, 2008). Strategic Intelligence is assessed via case-based or simulation-based measures in management research. Pattern Intelligence is assessed via anomaly-detection and trend-identification tasks. Predictive Intelligence is assessed via forecasting accuracy and calibration, including Brier scores and calibration curves (Tetlock's tradition).

**Synthetic application.** Systems Intelligence maps onto causal modeling, multi-step forward simulation, and the ability to recognize that a local intervention may have global consequences (and vice versa). Current LLM-based systems are weak at this; they typically reason locally and can miss second-order effects. Strategic Intelligence maps onto long-horizon planning with competition, uncertainty, and tradeoff evaluation; this overlaps with Strategic Planning (2.4) but adds competitive and adversarial reasoning. Pattern Intelligence maps onto signal extraction, trend recognition, and anomaly detection in streaming data. Predictive Intelligence maps onto probabilistic forecasting, scenario modeling, and calibration, an area where LLM-based systems are poorly calibrated and where explicit calibration training (or post-hoc calibration) is an active research area.

Systems thinking is not separately represented in the DeepMind 2026 taxonomy. It is arguably latent in "reasoning" and "problem solving," but the system-dynamics literature makes a substantive case that systemic reasoning has distinct cognitive requirements (feedback-loop tracking, stock-flow distinction, counterintuitive-behavior understanding) that generic reasoning does not automatically produce. CoALA does not address systems thinking as an architectural primitive.

| **Subcategory**             | **Description & Theoretical Alignment**                                                                                                                                                                                  | **Observable Performance Indicators**                                                                                                                                                                              |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Systems Intelligence**    | Ability to understand interacting parts within a larger whole; causal mapping, feedback-loop recognition, and leverage-point detection. Grounded in Senge (1990) and Meadows (2008).                                      | Sees root causes rather than just symptoms; understands second-order interactions; detects why local fixes may fail globally; identifies high-leverage intervention points.                                        |
| **Strategic Intelligence**  | Ability to make effective long-range choices under competition and uncertainty; objective clarity, positioning, sequencing, and tradeoff evaluation. Grounded in Liedtka (1998).                                          | Chooses paths aligned to desired outcomes; manages tradeoffs consciously; anticipates downstream consequences; coordinates action over time rather than reacting moment to moment.                                |
| **Pattern Intelligence**    | Ability to detect recurring structures across data, behavior, and events; signal extraction, trend recognition, and anomaly detection. Draws on the perception (Gibson, 1979) and intelligence-analysis (Heuer, 1999) literatures. | Notices repeat structures quickly; distinguishes signal from noise; detects meaningful deviations from baseline; compresses complexity into understandable patterns.                                               |
| **Predictive Intelligence** | Ability to anticipate probable outcomes from patterns and causal models; forecasting, scenario modeling, and confidence calibration. Grounded in Tetlock (2005) and Tetlock and Gardner (2015).                            | Anticipates likely next states accurately; models multiple possible futures; updates predictions with new evidence; assigns confidence with reasonable realism.                                                    |


---

## 5. Applications

HCQM is intended to support three classes of application: human development, synthetic cognitive architecture, and research and evaluation.

### 5.1 Human development

**Why not just use the source literatures directly?** A natural reviewer objection is that a practitioner can already consult the CHC, EI, grit, and cultural-intelligence literatures separately; what does HCQM add over the union of its sources? The answer is threefold: (1) a *shared vocabulary* across literatures that otherwise use incompatible terminology; (2) a *coverage map* that makes it explicit which capabilities are addressed by an assessment battery and which are not; and (3) a *gap-visualization scaffold* that supports auditing existing assessments for under-coverage (e.g., a typical leadership battery covers EI, grit, and learning agility but underweights metacognition and systems thinking). HCQM does not replace the source instruments; it provides the connecting taxonomy that the individual literatures do not jointly provide.

The primary human-development use case for HCQM is holistic capability assessment and development planning. In educational, clinical, and talent-management contexts, practitioners routinely draw on multiple instruments (an IQ battery, an EI assessment, a personality measure, a grit scale) without a shared taxonomy describing how the results relate. HCQM provides such a taxonomy. A practitioner using HCQM can (a) check whether existing instruments cover the intended assessment scope by mapping them onto HCQM domains and capabilities, (b) identify coverage gaps in that mapping, and (c) construct development plans that target specific subcomponents rather than generic "improve your EQ" prescriptions.

HCQM does not replace validated instruments. A practitioner using HCQM for assessment still needs to rely on existing, validated measures for each capability. What HCQM provides is the scaffolding that makes multi-capability assessment legible and comparable across individuals, teams, and contexts.

For educational design, HCQM's hierarchical structure supports curriculum-coverage analysis: a curriculum can be mapped onto the HCQM tree, and gaps can be identified at the domain, capability, or subcomponent level. For coaching and development, the indicator level supports goal setting at a resolution below "improve leadership" or "develop emotional intelligence." Goals can be set on specific indicators like "notices when understanding is weak" (Metacognitive Intelligence) or "reads group dynamics accurately" (Social Intelligence).

### 5.2 Synthetic cognitive architecture

The second use case is prescriptive: HCQM as a specification target for the capability surface a synthetic cognitive architecture should cover. This framing treats the taxonomy not as a description of observed human performance but as a capacity-layer specification; a statement of what an artificial system would need to be capable of in order to cover the same functional space that humans cover.

Three observations motivate this framing. First, current LLM-based systems show a "jagged" capability profile: strong in pattern completion and factual recall, weak in sustained learning, metacognition, and social cognition (Burnell et al., 2026; Morris et al., 2026). Second, the classical cognitive architecture tradition, represented in its unified form by the Common Model of Cognition (CMC; Laird, Lebiere, & Rosenbloom, 2017), was designed around four core structural components (working memory, procedural long-term memory, declarative long-term memory, and perception/motor) organized by a cognitive cycle, without explicit motivational, cultural, or systems-thinking components; its authors note the model is "silent... concerning metacognition, emotion... and mechanisms necessary for social cognition" (Laird et al., 2017). Emotion has since been taken up as a proposed extension, with a working group mapping points of interaction between emotion models and the CMC's structure (Larue et al., 2018); this work does not address cultural adaptation, adversity tolerance, or grit-like persistence, which remain absent from the classical architectural tradition. Third, contemporary language-agent architectures (CoALA; Sumers et al., 2024) provide a memory/action/decision decomposition that elegantly organizes LLM agents structurally but does not address the broader capacity surface HCQM covers.

**HCQM as a complement to CoALA.** CoALA specifies *structural* slots: what components an agent has, what data flows between them, and what control loop coordinates them. HCQM specifies *capacity*: what the agent can do within and across those slots. Appendix E contains the full gradient-match between HCQM and CoALA's 14 sub-concepts. Key findings:

- Every CoALA sub-concept has at least a partial HCQM mapping. No CoALA concept is entirely absent from HCQM.
- 10 HCQM constructs have zero or weak CoALA equivalents, concentrated in Domains 3 (emotional/social/cultural), 4 (creative), 5 (motivational/adaptive), and parts of 8 (pattern).
- CoALA introduces concepts that HCQM does not currently capture well: episodic and procedural memory as distinct types, the read-vs-write asymmetry in memory operations, metareasoning (compute allocation for reasoning), and grounding as a distinct bridging action between internal state and external environment. These are candidates for future refinement.

For each HCQM capability, an architect can ask: what module, representation, or control mechanism would implement this? In many cases, existing architectural patterns apply directly: Domain 1 (General Cognitive Intelligence) maps onto reasoning modules, retrieval-augmented generation, working memory buffers; Domain 2 (Executive/Self-Regulatory) maps onto planning modules, inhibition mechanisms, self-critique loops, confidence calibration. In other cases, the specification highlights gaps. Domain 5 (Motivational & Adaptive Intelligence) does not have a canonical implementation pattern in LLM agents; equivalents of grit or adversity tolerance are not currently built into agent loops and would need to be engineered as explicit persistence policies over long-horizon tasks. Domain 3.3 (Cultural Intelligence) is typically treated as a training-data property rather than as an architected capability, which leaves it brittle.

**HCQM as a complement to DeepMind's evaluation framework.** Appendix D contains the full gradient-match with the 10 DeepMind cognitive faculties. Where DeepMind's taxonomy asks "how does this system perform on 10 cognitive faculties relative to a representative human sample," HCQM asks "what capability surface does this system cover, and where are the gaps against a broader human-capability taxonomy that includes motivational, emotional, cultural, and adversity dimensions." The two frameworks are not substitutes; they answer different questions.

**Two illustrative mapping examples.**

*Example 1: Metacognition (HCQM 2.1) as a capacity-level specification.* A design note before the specification: the CMC is explicitly silent on metacognition (Laird et al., 2017), and Soar treats it not as a dedicated module but as behavior emerging from general problem-space reasoning over the architecture's own state (Laird, 2012). HCQM's capacity-layer treatment is consistent with that position: HCQM 2.1 specifies what a system must be capable of, not that metacognition must be implemented as a distinct module. These capacities can be realized within existing cognitive-cycle machinery rather than requiring a separate architectural slot. With that framing in place: an architect targeting the Metacognitive Intelligence capacity in an LLM agent would need to achieve (a) a self-monitoring function that observes the agent's own reasoning trace and detects when understanding is weak or strategy is failing; (b) an error-detection function that flags likely mistakes before external feedback arrives; (c) a strategy-selection function that switches approach when the current one is failing; (d) a confidence-calibration function that produces probability estimates or confidence levels aligned with actual accuracy. CoALA's memory/action/decision decomposition provides structural scaffolding (self-monitoring writes to working memory; strategy switching is a decision-loop operation) but does not prescribe the capacity level. HCQM's subcomponents of 2.1 specify the capacity target; the architectural implementation is a separate design decision.

*Example 2: Adversity Quotient (HCQM 5.3) as an architectural module.* There is no canonical implementation pattern. A minimal sketched implementation might include: (a) a monitored "computational stress" state capturing failure accumulation, resource pressure, or degraded output quality; (b) explicit recovery policies that activate on that state, such as reducing reasoning depth, switching to more conservative retrieval, or requesting clarification rather than proceeding on weak grounds; (c) a persistence policy that prevents premature termination of long-horizon tasks after partial failures. None of these is present as an architectural primitive in CoALA or as an evaluation target in the DeepMind taxonomy; all of them are described at the capacity level in HCQM 5.3. This sketch is illustrative rather than evidential: it shows how HCQM's capacity-layer specification can be used as a scaffold for architectural decomposition; it does not establish that the sketched architecture works or that HCQM is sufficient as an architecture specification. As §6.6 notes, full architectural prescriptiveness requires a companion specification document.

HCQM is not a complete architecture; it does not specify module interfaces, message formats, or control flow. It is a specification *target*: a statement of the capacity surface that an architecture must cover to be general in the sense that human capability is general. Section 6 discusses this positioning as a limitation as well as a claim.

**The reliability and autonomy layer: HCQM's distinctive contribution to agent design.** The preceding examples generalize into the paper's central AI-facing claim. The contemporary AI capability frameworks reviewed in §2.11 (ADeLe, Tolan et al., 2021; DeepMind 2026, Burnell et al., 2026; Hendrycks et al., 2025; OECD, 2025) are organized around *cognitive faculties*: perception, memory, reasoning, attention, and the like. That organizing frame is inherited from psychometrics and cognitive science, which developed it to explain individual differences in human cognitive *performance*. It was not built to predict whether an autonomous system remains *reliable* across a long, failure-prone trajectory. As AI shifts from single-turn task performance to long-horizon autonomous agents, the binding constraint on usefulness is increasingly not raw cognitive capability but reliability over extended execution: recovering from errors, not drifting off the goal, calibrated judgement about when to stop or ask, and persisting through partial failure without either quitting prematurely or perseverating on a failing plan. The cognitive-faculty frame does not pose these as capacity questions, so the capability *taxonomies* built on it do not represent them as first-class capacities. A distinction matters here: individual benchmarks can and do measure reliability behaviorally as an outcome (for example, consistency of success across repeated trials), and several document that current agents are markedly unreliable. The gap HCQM addresses is not that reliability is unmeasurable but that the capability *taxonomies* used to organize and target AI capability have no first-class place for the capacities that produce it.

HCQM already contains the constructs that name these capacities, distributed across its domains: Adversity Quotient (5.3, recovery under sustained failure), Grit / Persistence (5.4, sustained commitment over long horizons), Adaptability Quotient (5.2, strategy revision under change), Metacognitive Intelligence (2.1, self-monitoring and confidence calibration), and Predictive Intelligence (8.4, calibrated anticipation of outcomes). HCQM's distinctive contribution to AI is to organize these as a coherent **reliability and autonomy layer** and to specify them at the capacity level as targets an architecture must meet. This is a positional and organizational contribution, not a claim that the constituent constructs are novel (they are drawn from the existing literature) or that HCQM introduces new mechanisms (it does not); it is the claim that this particular set of capacities, treated together as the determinant of agent reliability, is precisely the region the cognitive-faculty frameworks omit.

A worked example makes the claim concrete and falsifiable. A recurring, documented failure pattern in long-horizon LLM agents on coding, web-navigation, and tool-use benchmarks is the **failure-perseveration-collapse trajectory**: an agent encounters a sub-task failure and then exhibits a cascade that cognitive-faculty evaluation does not anticipate. Each observed behavior maps to a specific missing HCQM reliability capacity and to a corresponding capacity target an architecture would need to meet:

| Observed agent behavior (documented failure mode) | Missing capacity (HCQM) | Capacity target for an architecture |
|---|---|---|
| Does not detect its own error before external feedback arrives | Metacognitive self-monitoring (2.1) | A self-monitoring function that flags weak or failing reasoning before feedback |
| Reports success on a non-working solution | Confidence calibration (2.1); Predictive Intelligence (8.4) | Confidence estimates aligned with actual outcome probability |
| Repeats the same failing action rather than revising | Adaptability Quotient (5.2) | Strategy revision triggered by repeated failure |
| Collapses or quits after a setback | Adversity Quotient (5.3) | A recovery policy over a monitored failure/stress state |
| Drifts off the long-horizon goal or loops indefinitely | Grit / Persistence (5.4) | A persistence policy preventing premature termination or unbounded looping |

The insight that carries the contribution is this: a capability taxonomy organized by cognitive faculties (ADeLe, DeepMind, Hendrycks, OECD) would profile this agent on reasoning, memory, and planning, and could rate it highly capable, while the agent still fails in deployment because the reliability capacities (5.2 through 5.4, 2.1, 8.4) those taxonomies do not represent are absent. The behavioral failures are observable, and benchmarks record them; what is missing is a taxonomic place for the *capacities* whose absence produces them. **HCQM's reliability layer names that capacity region, which the cognitive-faculty taxonomies leave unrepresented.** This connects directly to the coverage asymmetry of §2.11.8: the dimensions the AI frameworks omit are not a miscellaneous remainder, they are concentrated in exactly the capacities that govern autonomous reliability.

Two honesty constraints bound this claim. First, the worked example is illustrative and literature-grounded, not the result of a controlled HCQM-instrumented study; the failure modes are drawn from published agent-evaluation findings (e.g., consistency-across-trials reliability gaps in tool-agent benchmarks, Yao et al., 2024; documented self-correction limits, Huang et al., 2024; long-horizon coding and web-agent failure rates, Jimenez et al., 2024; Zhou et al., 2024) and from the unfaithful-reasoning-trace findings already discussed in §2.7 and §2.11.3 (Korbak et al., 2025). Whether HCQM-aligned instrumentation, applied developmentally to an agent learning a long-horizon task, surfaces capability gaps (observed as characteristic failures) more informatively than cognitive-faculty evaluation is an empirical question, identified as priority future work in §6.7. Second, specifying the capacity targets is not the same as delivering an architecture that meets them; full prescriptiveness still requires the companion specification document of §6.6. The reliability capacities are also developmental: they are the capacities that must *develop* for an agent to sustain long-horizon performance, so the natural empirical test is to track their acquisition and expression while an agent learns a long-horizon task, treating characteristic failures as diagnostic readouts of capability gaps rather than as the primary target. This developmental capability-profiling study is identified as priority future work (§6.7).

### 5.3 Research and evaluation

The third use case is as a taxonomic scaffold for research and evaluation. HCQM provides a shared vocabulary across the traditionally separate literatures covered in Section 2. Researchers studying the interaction of two capabilities (say, grit and metacognition, or cultural intelligence and learning agility) can situate their constructs in the HCQM tree and communicate coverage claims precisely.

For AI evaluation specifically, HCQM can serve as a complement to the DeepMind 2026 cognitive framework. DeepMind's framework is optimized for AGI progress measurement against human baselines in ten cognitive faculties; HCQM's broader scope means it can host evaluations that address capabilities DeepMind does not centrally treat (motivational persistence, cultural adaptation, systems thinking, adversity response). The two frameworks are not substitutes; they answer different questions. DeepMind's asks, "how close is this system to human median performance across ten core cognitive faculties?" HCQM asks, "what capability surface does this system cover, and where are the gaps?"

**Open evaluation questions.** HCQM v0.1 does not specify an integrated evaluation protocol, and this is a known gap (see Section 6). Several open questions bear on what such a protocol would look like:

1. *Construct-aligned comparability.* Naive comparisons (e.g., giving an IQ test unchanged to an LLM) do not control for differences in embodiment, context, and interaction modality. Construct-aligned alternatives (mapping an AI's "statistical induction ability" to a human's fluid intelligence, and comparing percentile ranks on analogous tasks) are more defensible but require careful instrument design.
2. *Dual benchmarks.* One possibility is to pair a human-designed test with an AI-appropriate interface, and an AI benchmark with a human-participant version (e.g., human-solved CAPTCHA as a perception benchmark).
3. *Item Response Theory (IRT) calibration.* For any unified instrument, IRT-style calibration of item difficulty to latent ability is a standard method in psychometrics and is increasingly applied to AI evaluation.
4. *Profile visualization.* A radar plot or profile chart over HCQM domains, with human normative distributions overlaid, would support the same kind of "cognitive profile" output the DeepMind framework produces, extended to HCQM's broader domain set.

These are sketched here only as open directions; an integrated HCQM evaluation protocol is future work.

---

## 6. Limitations and Future Work

HCQM has several significant limitations, which we state explicitly to bound the claims made in this paper.

### 6.1 HCQM is a synthesis, not an empirical instrument

HCQM itself has not been empirically validated as an integrated assessment framework. The component constructs have varying levels of validation in their original literatures: CHC-aligned cognitive abilities are among the most validated constructs in psychology; grit and mindset have been the subject of meta-analytic critique (Credé et al., 2017; Sisk et al., 2018); adversity quotient and adaptability quotient have thinner peer-reviewed support than grit and curiosity. HCQM inherits these asymmetric validation levels. A unified HCQM assessment battery does not exist, has not been constructed, and would require substantial psychometric work including factor-analytic validation, discriminant validity testing against related constructs, and cross-cultural validation.

### 6.2 Construct overlap and hierarchy ambiguity

Several HCQM capabilities overlap conceptually with others. Working Memory (1.6) is functionally related to but formally distinct from Cognitive Control (2.2) and Strategic Planning (2.4). Metacognitive Intelligence (2.1) overlaps with confidence calibration in Predictive Intelligence (8.4) and with self-correction in Learning Agility (6.1). Curiosity (5.1) interacts with but is distinct from learning-agility feedback uptake. The Working Memory indicator "resists losing track under interruption" overlaps in phrasing with the Cognitive Control indicator "stays focused despite noise or interruption"; these may need to be disambiguated in a future revision or explicitly annotated as the same underlying capacity captured at different hierarchical levels.

HCQM preserves distinctions where the source literatures preserve them, at the cost of some conceptual redundancy. A deliberate reduction of overlap between subcomponents (except where overlap is intentional and annotated) is identified as future work. Empirical work on the factor structure of an integrated HCQM instrument would clarify which distinctions survive and which collapse.

### 6.3 Human-baseline contamination risks (WEIRD bias and capacity asymmetry)

The operationalization of human baselines for HCQM-style evaluation presents two distinct risks.

**WEIRD-sample bias.** Securing a demographically representative sample of adults for capabilities such as Systems Intelligence, Metacognitive Intelligence, or Cultural Intelligence requires cross-cultural validation that the source literatures have only partially achieved. Failure to validate cross-culturally risks contaminating the baseline with WEIRD (Western, Educated, Industrialized, Rich, Democratic) socio-cognitive bias, a well-documented hazard in psychological measurement (Henrich, Heine, & Norenzayan, 2010). For Cultural Intelligence (3.3) specifically, the construct is by definition cross-cultural; baselining it on WEIRD samples would defeat the construct's purpose.

**Capacity asymmetry between humans and AI systems.** A second and distinct concern arises for capabilities where current AI systems and humans operate at very different capacity scales: for example, raw processing speed (HCQM 1.5), large-context verbatim retention (a function of context window in LLM-based systems), or symbol-search tasks. Comparing AI systems to human distributions on these capabilities can be uninformative or misleading: an AI system that scores at the human 99th percentile on processing speed may simultaneously score at the human 30th percentile on deliberate reasoning, and a single profile aggregating these would obscure both findings. Construct-aligned comparison and per-capability reporting (§5.3) partially mitigate this; full mitigation requires capability-specific scaling decisions that HCQM does not currently provide. This is distinct from the WEIRD-sample concern and reflects measurement scaling rather than cultural representativeness.

### 6.4 Scoping omissions

HCQM does not include, at the top level, several capabilities with defensible claims on inclusion:

- **Bodily-kinesthetic and musical intelligences** (Gardner, 1983) are excluded on parsimony and relevance grounds (weak link to general intelligence in AI systems; specialized measurement traditions).
- **Sensory perception and motor action.** Following the DeepMind 2026 framing, sensory perception and output generation are distinct cognitive faculties. HCQM treats them as boundary layers rather than as core domains; for embodied AI systems or for assessment contexts that require sensory and motor specification, HCQM would need to be extended at these boundaries. This includes CHC's Ga (auditory), Gh (tactile), Gk (kinesthetic), Go (olfactory), Gp (psychomotor), and Gps (psychomotor speed), none of which are currently represented as HCQM capabilities.
- **Alexithymia** (emotional blindness) is not represented as a subcomponent of Domain 3.1. This is relevant both as a clinical construct in human assessment and as a descriptor of current LLM systems' constrained emotional access.
- **Wisdom** as treated by Sternberg, Grossmann, and others (Grossmann et al., 2020) is not separately represented. Arguments could be made for including it as a top-level or ninth domain.
- **Aesthetic and philosophical reasoning** are not represented.
- **Embodied / motor / grounding capability.** CoALA's grounding action class (the capacity to translate between internal symbolic state and external environments via perception or actuation) is not currently captured in HCQM. This includes what Sumers et al. (2024) describe as *cross-modal translation* or *modality bridging*: the capacity to convert between perceptual, symbolic, and motor representations. No current HCQM construct covers this explicitly. The OECD (2025) inclusion of *manipulation* and *robotic intelligence* as first-class capabilities (Appendix H) is convergent evidence that this boundary should be reconsidered for embodied-AI use cases.
- **Memory, Perception, and Attention as standalone top-level domains.** The DeepMind (2026) and Hendrycks et al. (2025) taxonomies both treat memory, perception, and attention as first-class evaluation targets. In the current framework, memory is partially located inside Domain 1 (Working Memory 1.6, with episodic and procedural memory referenced under Domains 6 and 1 respectively); attention is folded into Domain 2.2 (Cognitive Control); perception is largely scoped out. A candidate future refinement is to promote each of these to standalone status, possibly splitting Domain 1 into a finer-grained set of basic-faculty domains aligned with CHC narrow abilities, the DeepMind 10 faculties, and the Hendrycks ten cognitive domains. The current 8-domain count is therefore explicitly provisional, not final.
- **Moral and ethical reasoning** (Kohlberg, 1969; Rest et al., 1999) is not treated as a separate top-level domain. The current handling distributes ethical reasoning across Strategic Intelligence (tradeoff evaluation) and Metacognitive Intelligence (reflection quality). This is plausibly inadequate for AI-alignment applications, where value-priority structure, deontological/consequentialist distinctions, and value-conflict resolution are central. A standalone moral-reasoning domain (or domain-level subcomponent of Domain 3) is a candidate for future work, particularly if HCQM is used for AI alignment evaluation.

These omissions are defensible but not final. Future versions of HCQM may expand coverage.

### 6.5 Indicator quality

The indicators listed in the HCQM tree (Appendix A) are behaviorally specific but not formally psychometrically tested. They are intended as anchor points for operationalization rather than as validated items. Moving from indicators to validated items requires standard psychometric work (item construction, pilot testing, reliability and validity analysis, differential-item-functioning analysis across cultures).

### 6.6 The dual-use claim is not symmetrically validated, and "prescriptive" is partial without a companion architecture document

HCQM's dual-use framing (that the same taxonomy can serve both human assessment and synthetic architecture specification) is a design claim, not an empirical one. It is plausible on the grounds that (a) cognitive architectures since Newell have drawn on human cognition, and (b) recent LLM-era work (CoALA; DeepMind 2026; Hendrycks et al., 2025) explicitly grounds AI evaluation in psychology. But the specific claim that HCQM's particular decomposition is well suited to both purposes has not been empirically tested, and there are reasons to expect asymmetries: human assessment prioritizes discriminant validity and individual differences, while architecture specification prioritizes module separability and implementation tractability.

The term *prescriptive* used elsewhere in this paper (§1.3, §2.11.3, §5.2) should be read as **partially prescriptive at the capacity layer only**. HCQM specifies *that* an architecture intended to be general in the human sense must cover the eight-domain capacity surface; it does not specify *how*: module interfaces, message formats, control flow, training regimes, or computational substrate are all outside HCQM's scope. Full architectural prescriptiveness requires a companion specification document that maps HCQM capabilities onto concrete module specifications, integration patterns, and evaluation harnesses. This companion document is identified as priority future work (see §6.9, item 7); until it is published, claims of prescriptiveness in the current paper should be read as setting the *target surface* rather than as a sufficient blueprint.

A related open question is whether all HCQM capabilities admit clean computational operationalization. The strong version of HCQM's architecture-readiness claim is that every human capability can be operationalized as a measurable algorithmic or behavioral attribute applicable to both humans and AI systems. This claim has not been tested. Capabilities involving subjective experience (for example, emotional awareness at the level of qualia) may admit only behavioral operationalization in synthetic systems, not phenomenal equivalence in the philosophical sense (Block, 1995; Chalmers, 1996). HCQM's position is that behavioral operationalization is sufficient for the taxonomy's *measurement* purposes; whether behavioral equivalence is also sufficient for moral, legal, or interpretive purposes is a separate philosophical question that this paper does not adjudicate. The dissenting view (qualia matter constitutively for emotional intelligence; behaviorally equivalent systems lack EQ in the same sense humans do) is recorded as a contested position rather than dismissed.

### 6.7 No integrated evaluation protocol

HCQM v0.1 does not include an integrated evaluation protocol comparable to the DeepMind 2026 three-stage protocol (cognitive assessment → human baselines → cognitive profiles; Burnell et al., 2026) or to the human-battery adaptation methodology of Hendrycks et al. (2025). This is a known structural gap and, alongside the empirical validation gap discussed in §6.1, is a priority blocker for any submission venue that expects a methodology section. This subsection sketches the protocol that future work should develop, without claiming the design here is final.

**Proposed three-stage structure.** An HCQM evaluation protocol would parallel the DeepMind protocol in its high-level structure (assessment → baseline → profile) while adapting each stage to HCQM's broader capability scope. Stage 1 establishes a capability-to-instrument mapping for each of the 33 HCQM constructs across the eight domains. Stage 2 collects human normative baselines (where instrument-level norms exist) and synthetic-system measurements (administered under conditions matched as closely as practicable to the human protocol). Stage 3 reports capability profiles in a format that makes coverage gaps visible and supports cross-system comparison.

**Stage 1: Capability-to-instrument mapping.** Domain 1 (General Cognitive Intelligence) inherits the strongest instrument support. Established CHC-aligned batteries (Wechsler series, Woodcock-Johnson IV, KABC-II; cf. §4.1) provide validated measurement at the broad-ability level, and the Hendrycks et al. (2025) battery adaptations are direct candidates for synthetic-system administration. Domain 2 (Executive/Self-Regulatory) maps to neuropsychological tasks (Stroop, Wisconsin Card Sorting Test, Trail Making, Go/No-Go) and to self-report or informant-report instruments (BRIEF; Schraw & Dennison Metacognitive Awareness Inventory). Domain 3 (Emotional & Social) draws on the MSCEIT for ability-model EQ and the CQS for cultural intelligence; Social Intelligence and Interpersonal Awareness rely on less standardized observational rubrics. Domain 4 (Creative) draws on the TTCT for divergent thinking and the RAT for associative thinking, with consensual-assessment rubrics for the composite Creativity Quotient. Domain 5 (Motivational & Adaptive) draws on the Grit-S, the Five-Dimensional Curiosity Scale, and applied-management instruments for Adaptability and Adversity (the latter with weaker peer-reviewed validation, as noted in §4.5 and §6.1). Domain 6 (Learning) draws on learning-agility instruments (LAAI, Learning Agility Architect™) and transfer paradigms. Domain 7 (Digital) draws on the DQ Institute instruments, ACRL-aligned information-literacy assessments (SAILS, TRAILS), and the Computational Thinking Test (Román-González et al., 2017). Domain 8 (Systems) draws on stock-flow distinction tasks and causal-loop diagramming for systems thinking, and on calibration tasks (Brier-scored forecasts) for predictive intelligence. A full capability-to-instrument mapping table is identified as future work.

**Stage 2: Human baselines and synthetic measurement.** For instruments with established norms (Wechsler, MSCEIT, Grit-S, CQS), normative distributions provide direct human baselines. For instruments without consolidated norms (Domains 5, 6, 8 in particular), supplementary normative work would be required, and the protocol should mark these gaps explicitly rather than papering over them. Synthetic measurement requires that AI systems be administered the same or analogous instruments under conditions that preserve construct validity. Item Response Theory (Embretson & Reise, 2000) provides a candidate framework for calibrating cross-population comparisons. Where direct cross-administration is not feasible (e.g., social-cognition tasks dependent on embodied interaction), dual-track measurement is proposed: a human battery for the human side and a construct-aligned synthetic benchmark for the AI side, with explicit acknowledgment that the two are construct-aligned rather than instrument-identical.

**Stage 3: Capability profiles and reporting.** Reporting formats should make coverage gaps visible. Candidate visualization is a radar plot over HCQM domains with normative distributions overlaid for the human case and benchmarked distributions for the synthetic case. Profiles should include per-construct scores, per-domain composites, and coverage flags marking constructs for which measurement was unavailable or weakly validated. Aggregation across capabilities with different scoring conventions (raw scores, percentiles, latent-trait estimates) requires explicit normalization choices; the protocol should report both the raw and the normalized values to support reanalysis.

**Near-term implementation priorities.** Three implementation priorities follow from the above. First, complete the capability-to-instrument table for all 33 constructs and identify constructs where measurement support is weak (initial inspection suggests these are concentrated in Domains 5, 6, and 8). Second, pilot the synthetic-administration adaptations on Domain 1 first, using the Hendrycks et al. (2025) battery as the starting point, before expanding to other domains. Third, develop the radar-plot reporting template with at least one fully populated example (human and synthetic side-by-side) to make the protocol output concrete rather than abstract.

A related open question is whether the protocol should incorporate non-traditional output signals as measurable manifestations of capability exercise. For humans, candidates include physiological correlates of effort or stress; for synthetic systems, candidates include computational indicators such as inference latency, retrieval frequency, or resource utilization under load. These are recorded here as candidate extensions rather than core protocol elements.

**Developmental capability profiling on a long-horizon learning task.** The most direct synthetic-side test of the dual-use claim is not a static benchmark but a *developmental* one: instrument an agent learning a long-horizon, open-ended task and track which HCQM capacities are acquired and expressed as learning proceeds. A long-horizon, open-ended progression environment (for example, a single-player role-playing video game of the kind used in recent long-horizon agent demonstrations) provides measurable signals that map onto HCQM constructs: world-coverage and exploration onto Curiosity (5.1) and Visual-Spatial/navigation (1.4); experience-driven growth onto Learning Agility (6.1) and Transfer (6.3); long-horizon goal progression onto Strategic Planning (2.4) and Grit/Persistence (5.4); and strategy revision under changing demands onto Adaptability (5.2) and Metacognition (2.1). The framing is deliberately task-agnostic: the testbed is one instantiation, and any long-horizon environment with progression, exploration, and failure-recovery structure would serve. In this framing, HCQM functions as a *developmental capability map for AI learning*, the synthetic analogue of its human-development use case (§5.1), rather than as a static scorecard. Characteristic agent failures (repeated catastrophic-failure states, looping, getting stuck, premature termination) are treated not as the primary measurement target but as *diagnostic readouts* that reveal which capacity is underdeveloped: a loop or a stuck state indicates an adaptability or metacognitive-monitoring gap (5.2, 2.1); repeated catastrophic failure without recovery indicates an adversity or learning-from-feedback gap (5.3, 6.1). This connects the reliability-and-autonomy layer of §5.2 to the learning process: the reliability capacities are precisely those that must *develop* for an agent to sustain long-horizon performance, and their absence is observable as a capability-profile gap during learning. Such a study is future work; it is not part of this draft, and the present paper makes no empirical claim from it.

Developing this protocol is a prerequisite for empirical HCQM validation (§6.1) and is the highest-priority future-work item (§6.9).

### 6.8 Positioning against the five comparison frameworks

HCQM is compared against five contemporary AI capability frameworks (§2.11.2–2.11.6 and Appendices D, E, G, H): CoALA (Sumers et al., 2024), DeepMind 2026 (Burnell et al., 2026), Hendrycks et al. (2025), the OECD AI Capability Indicators (OECD, 2025), and the Hernández-Orallo and Vold (2019) cognitive-ability catalogue (elaborated in Tolan et al., 2021). Each comparison carries caveats and a return obligation.

The comparison with DeepMind's cognitive taxonomy in Section 2.11 and Appendix D is based on the version of the DeepMind paper available at the time of this writing (Burnell et al., 2026; released March 17, 2026). DeepMind's framework is itself preliminary (it is paired with a Kaggle hackathon soliciting community-built evaluations for five capability areas) and may evolve. The HCQM-vs-DeepMind comparison should be revisited as DeepMind's framework matures and as community-built benchmarks accumulate.

The comparison with CoALA in Section 2.11 and Appendix E is based on Sumers et al. (2024) as published in *Transactions on Machine Learning Research*. CoALA's treatment of procedural memory (implicit weights vs. explicit code), grounding (physical/dialogue/digital), and metareasoning identifies specific refinements that future revisions of HCQM should consider incorporating at the subcomponent level.

The comparisons with Hendrycks et al. (2025) and the OECD (2025) indicators are based on the CHC-grounded ten-domain definition and the nine policy-facing ability domains, respectively (Appendices G and H). Both are cognitive-and-task-ability frameworks; the Hendrycks memory decomposition (storage vs. retrieval; hallucination/retrieval precision) and the OECD inclusion of manipulation and robotic intelligence are the specific elements HCQM should weigh, in future revisions, at its sensory-motor boundary (§6.4). The comparison with the Hernández-Orallo and Vold (2019) catalogue (elaborated in Tolan et al., 2021; associated with the ADeLe evaluation line) is reported in §2.11.6; because this work predates the other four and already includes emotion, social, and metacognitive abilities, it is credited as a predecessor on the move beyond purely cognitive evaluation, and its gradient-match is reported in full in Appendix I, for parity with the others.

### 6.9 Future work

Near-term future work on HCQM includes:

1. **Empirical status of Motivational & Adaptive constructs.** Construction of a preliminary self-report and informant-report instrument covering all eight domains, for pilot psychometric evaluation. Particular attention to AQ and adaptability-quotient validation, which have weaker peer-reviewed support than grit and curiosity.
2. **Formal concept-to-source mapping at the subcomponent level** (partially initiated in Appendix C). Distinguish theoretical sources from measurement-instrument sources; flag capabilities where the HCQM operationalization diverges from any single source.
3. **Evaluation protocol development**, as described in Section 6.7.
4. **Subcomponent refinements suggested by the CoALA comparison** (Appendix E):
   - Add explicit *episodic memory* and *procedural memory* constructs (or subcomponents) inside Domain 6 or Domain 1.
   - Add *cognitive resource allocation / reasoning budget control* as a subcomponent of 2.1 Metacognitive Intelligence, to cover metareasoning.
   - Add *modality bridging / embodied grounding* as a construct covering perception-to-symbol translation, perhaps as a new domain or as extensions to Domain 1 and Domain 7.
   - Distinguish *encoding* from *retrieval* in working memory and crystallized intelligence subcomponents.
   - Annotate each capability with both *static capacity* and *dynamic process* facets.
5. **Subcomponent refinements suggested by domain-level reviews:**
   - Add *alexithymia* as a reverse-scored subcomponent of Emotional Intelligence (3.1).
   - Resolve the overlap between Working Memory (1.6) "resists losing track under interruption" and Cognitive Control (2.2) "stays focused despite noise or interruption."
   - Consider whether morality/ethics warrants a standalone construct in Domain 3 or a new Domain 9.
6. **Cross-cultural validation** work, particularly on Domain 3.3 (Cultural Intelligence) and Domain 5 (Motivational & Adaptive Intelligence), where cultural moderators are likely substantial.
7. **Architecture case studies** translating HCQM domains into concrete AI system specifications, both for LLM agents (extending CoALA) and for non-LLM architectures. Particular focus on the reliability-and-autonomy layer (§5.2) and on Domain 5, which is the hardest to instantiate in current LLM agent frameworks, including the developmental capability-profiling study sketched in §6.7.
8. **Alignment studies** between HCQM and the DeepMind cognitive framework as community-built evaluations become available through the DeepMind/Kaggle hackathon.

---

## 7. Conclusion

Human capability research is fragmented, not because the constituent literatures are weak, but because integration has been deprioritized. The Human Capability Quotient Map is an attempt at integration: eight top-level domains, thirty-three capabilities, and a hierarchical structure of subcomponents and indicators drawn from foundational work in psychometrics, intelligence research, emotional and cultural intelligence, creativity, metacognition, motivational and adversity research, learning agility, digital intelligence, computational thinking, and systems thinking. HCQM does not claim to invent new capabilities; it claims to arrange existing ones in a way that is useful for holistic human assessment and for synthetic cognitive architecture.

The case for HCQM rests on three claims. First, the integration is itself valuable: researchers and practitioners gain a shared vocabulary and a coverage map across traditionally separate literatures. Second, there is a coverage asymmetry between the human-capability tradition and contemporary AI capability frameworks. The human-capability tradition treats motivational, affective, cultural, and adversity capability as first-class (contemporary CHC, for instance, includes emotional intelligence as the Gei broad ability; Schneider & McGrew, 2018), whereas the five AI frameworks compared here (the Hernández-Orallo and Vold (2019) catalogue, associated with the ADeLe evaluation line; CoALA, Sumers et al., 2024; DeepMind 2026; Hendrycks et al., 2025; OECD, 2025) largely do not. HCQM's role is to port that human-side coverage to the AI side as a capacity-layer specification. This is a scope claim about the AI frameworks, not a novelty claim against the human tradition: HCQM's emotional dimension is CHC-aligned, and the Hernández-Orallo and Vold (2019) work is credited as a partial predecessor that already included emotion, social, and metacognitive abilities. Third, the dual-use framing (the same taxonomy for humans and machines, at the capacity layer) is a deliberate design stance, not an accident of presentation. Its sharpest and most AI-relevant form is the reliability-and-autonomy layer (§5.2): the motivational, adaptive, and metacognitive capacities the AI frameworks omit are precisely those that govern whether a long-horizon autonomous agent is reliable, as distinct from merely capable. HCQM positions itself as a complement to structural frameworks like CoALA and evaluative frameworks like DeepMind's, not as a competitor; it addresses a different layer of the stack (capacity) and a different breadth (cognitive plus non-cognitive).

HCQM has significant limitations, most notably the lack of integrated empirical validation, the absence of a formal evaluation protocol, and specific subcomponent-level gaps identified by the CoALA and DeepMind comparisons. These are explicit in Section 6 and are the priority targets for future work. The framework is released openly to support independent critique, refinement, and instrument development.

---

## Acknowledgments

The author thanks Dr. Kevin McGrew (Institute for Applied Psychometrics) for substantive feedback on an early version of HCQM, particularly regarding the treatment of contemporary Cattell–Horn–Carroll theory. The author also thanks two anonymous reviewers for feedback on the cognitive-architecture and AI-evaluation sections, including the AI-capability-framework comparisons. Reviewer feedback informed the revisions in this version; responsibility for any remaining errors rests with the author.

---

## References

Amabile, T. M. (1982). Social psychology of creativity: A consensual assessment technique. *Journal of Personality and Social Psychology*, *43*(5), 997–1013. https://doi.org/10.1037/0022-3514.43.5.997

Anderson, J. R. (2007). *How can the human mind occur in the physical universe?* Oxford University Press.

AlKhamissi, B., ElNokrashy, M., Alkhamissi, M., & Diab, M. (2024). Investigating cultural alignment of large language models. In *Proceedings of the 62nd Annual Meeting of the Association for Computational Linguistics*. ACL. https://aclanthology.org/2024.acl-long.671

Ang, S., Van Dyne, L., Koh, C., Ng, K. Y., Templer, K. J., Tay, C., & Chandrasekar, N. A. (2007). Cultural intelligence: Its measurement and effects on cultural judgment and decision making, cultural adaptation and task performance. *Management and Organization Review*, *3*(3), 335–371. https://doi.org/10.1111/j.1740-8784.2007.00082.x

Ang, S., & Van Dyne, L. (Eds.). (2008). *Handbook of cultural intelligence: Theory, measurement, and applications*. M. E. Sharpe.

Association of College and Research Libraries. (2016). *Framework for information literacy for higher education*. American Library Association. https://www.ala.org/acrl/standards/ilframework

Atari, M., Xue, M. J., Park, P. S., Blasi, D., & Henrich, J. (2023). *Which humans?* PsyArXiv. https://doi.org/10.31234/osf.io/5b26t

Baddeley, A. D. (2000). The episodic buffer: A new component of working memory? *Trends in Cognitive Sciences*, *4*(11), 417–423. https://doi.org/10.1016/S1364-6613(00)01538-2

Baddeley, A. D., & Hitch, G. J. (1974). Working memory. In G. H. Bower (Ed.), *The psychology of learning and motivation* (Vol. 8, pp. 47–89). Academic Press.

Bagby, R. M., Parker, J. D. A., & Taylor, G. J. (1994). The twenty-item Toronto Alexithymia Scale: I. Item selection and cross-validation of the factor structure. *Journal of Psychosomatic Research*, *38*(1), 23–32. https://doi.org/10.1016/0022-3999(94)90005-1

Bar-On, R. (1997). *The Emotional Quotient Inventory (EQ-i): A test of emotional intelligence*. Multi-Health Systems.

Block, N. (1995). On a confusion about a function of consciousness. *Behavioral and Brain Sciences*, *18*(2), 227–247. https://doi.org/10.1017/S0140525X00038188

Barnett, S. M., & Ceci, S. J. (2002). When and where do we apply what we learn? A taxonomy for far transfer. *Psychological Bulletin*, *128*(4), 612–637. https://doi.org/10.1037/0033-2909.128.4.612

Benedek, M., & Neubauer, A. C. (2013). Revisiting Mednick's model on creativity-related differences in associative hierarchies: Evidence for a common path to uncommon thought. *Journal of Creative Behavior*, *47*(4), 273–289. https://doi.org/10.1002/jocb.35

Booth Sweeney, L., & Sterman, J. D. (2000). Bathtub dynamics: Initial results of a systems thinking inventory. *System Dynamics Review*, *16*(4), 249–286. https://doi.org/10.1002/sdr.198

Bransford, J. D., Brown, A. L., & Cocking, R. R. (Eds.). (2000). *How people learn: Brain, mind, experience, and school* (Expanded ed.). National Academy Press.

Burnell, R., Yamamori, Y., Firat, O., Olszewska, K., Hughes-Fitt, S., Kelly, O., Galatzer-Levy, I. R., Morris, M. R., Dafoe, A., Snyder, A. M., Goodman, N. D., Botvinick, M., & Legg, S. (2026). *Measuring progress toward AGI: A cognitive framework*. Google DeepMind. https://storage.googleapis.com/deepmind-media/DeepMind.com/Blog/measuring-progress-toward-agi/measuring-progress-toward-agi-a-cognitive-framework.pdf

Carroll, J. B. (1993). *Human cognitive abilities: A survey of factor-analytic studies*. Cambridge University Press.

Cattell, R. B. (1963). Theory of fluid and crystallized intelligence: A critical experiment. *Journal of Educational Psychology*, *54*(1), 1–22. https://doi.org/10.1037/h0046743

Chalmers, D. J. (1996). *The conscious mind: In search of a fundamental theory*. Oxford University Press.

Chi, M. T. H., & Ohlsson, S. (2005). Complex declarative learning. In K. J. Holyoak & R. G. Morrison (Eds.), *The Cambridge handbook of thinking and reasoning* (pp. 371–399). Cambridge University Press.

Credé, M., Tynan, M. C., & Harms, P. D. (2017). Much ado about grit: A meta-analytic synthesis of the grit literature. *Journal of Personality and Social Psychology*, *113*(3), 492–511. https://doi.org/10.1037/pspp0000102

De Meuse, K. P. (2017). Learning agility: Its evolution as a psychological construct and its empirical relationship to leader success. *Consulting Psychology Journal: Practice and Research*, *69*(4), 267–295. https://doi.org/10.1037/cpb0000100

De Meuse, K. P., Dai, G., & Hallenbeck, G. S. (2010). Learning agility: A construct whose time has come. *Consulting Psychology Journal: Practice and Research*, *62*(2), 119–130. https://doi.org/10.1037/a0019988

de Ruiter, B., & Kachergis, G. (2018). *The Mafiascum dataset: A large text corpus for deception detection*. arXiv. https://arxiv.org/abs/1811.07851

Diamond, A. (2013). Executive functions. *Annual Review of Psychology*, *64*, 135–168. https://doi.org/10.1146/annurev-psych-113011-143750

Duckworth, A. L., Peterson, C., Matthews, M. D., & Kelly, D. R. (2007). Grit: Perseverance and passion for long-term goals. *Journal of Personality and Social Psychology*, *92*(6), 1087–1101. https://doi.org/10.1037/0022-3514.92.6.1087

Duckworth, A. L., & Quinn, P. D. (2009). Development and validation of the Short Grit Scale (Grit-S). *Journal of Personality Assessment*, *91*(2), 166–174. https://doi.org/10.1080/00223890802634290

Dweck, C. S. (2006). *Mindset: The new psychology of success*. Random House.

Earley, P. C., & Ang, S. (2003). *Cultural intelligence: Individual interactions across cultures*. Stanford University Press.

Embretson, S. E., & Reise, S. P. (2000). *Item response theory for psychologists*. Lawrence Erlbaum Associates.

Engle, R. W. (2002). Working memory capacity as executive attention. *Current Directions in Psychological Science*, *11*(1), 19–23. https://doi.org/10.1111/1467-8721.00160

Flavell, J. H. (1979). Metacognition and cognitive monitoring: A new area of cognitive-developmental inquiry. *American Psychologist*, *34*(10), 906–911. https://doi.org/10.1037/0003-066X.34.10.906

Forrester, J. W. (1961). *Industrial dynamics*. MIT Press.

Gardner, H. (1983). *Frames of mind: The theory of multiple intelligences*. Basic Books.

Gardner, H. (1999). *Intelligence reframed: Multiple intelligences for the 21st century*. Basic Books.

Gibson, J. J. (1979). *The ecological approach to visual perception*. Houghton Mifflin. Reissued 1986 by Lawrence Erlbaum and 2014 by Psychology Press (Classic Editions).

Gioia, G. A., Isquith, P. K., Guy, S. C., & Kenworthy, L. (2000). *Behavior Rating Inventory of Executive Function*. Psychological Assessment Resources.

Goleman, D. (1995). *Emotional intelligence: Why it can matter more than IQ*. Bantam Books.

Gottfredson, L. S. (1997). Mainstream science on intelligence: An editorial with 52 signatories, history, and bibliography. *Intelligence*, *24*(1), 13–23. https://doi.org/10.1016/S0160-2896(97)90011-8

Grossmann, I., Weststrate, N. M., Ardelt, M., Brienza, J. P., Dong, M., Ferrari, M., Fournier, M. A., Hu, C. S., Nusbaum, H. C., & Vervaeke, J. (2020). The science of wisdom in a polarized world: Knowns and unknowns. *Psychological Inquiry*, *31*(2), 103–133. https://doi.org/10.1080/1047840X.2020.1750917

Guilford, J. P. (1950). Creativity. *American Psychologist*, *5*(9), 444–454.

Hendrycks, D., Song, D., Szegedy, C., Lee, H., Gal, Y., Brynjolfsson, E., McGrew, K., Marcus, G., Tegmark, M., Schmidt, E., & Bengio, Y., et al. (2025). *A definition of AGI* (arXiv:2510.18212) [Preprint]. arXiv. https://arxiv.org/abs/2510.18212

Henrich, J., Heine, S. J., & Norenzayan, A. (2010). The weirdest people in the world? *Behavioral and Brain Sciences*, *33*(2–3), 61–83. https://doi.org/10.1017/S0140525X0999152X

Hernández-Orallo, J., & Vold, K. (2019). AI extenders: The ethical and societal implications of humans cognitively extended by AI. In *Proceedings of the 2019 AAAI/ACM Conference on AI, Ethics, and Society* (pp. 507–513). Association for Computing Machinery.

Heuer, R. J. (1999). *Psychology of intelligence analysis*. Center for the Study of Intelligence, Central Intelligence Agency.

Horn, J. L., & Cattell, R. B. (1966). Refinement and test of the theory of fluid and crystallized general intelligences. *Journal of Educational Psychology*, *57*(5), 253–270.

Huang, J., Chen, X., Mishra, S., Zheng, H. S., Yu, A. W., Song, X., & Zhou, D. (2024). Large language models cannot self-correct reasoning yet. In *International Conference on Learning Representations (ICLR 2024)*. arXiv:2310.01798. https://arxiv.org/abs/2310.01798

Hudlicka, E. (2007). Reasons for emotions: Modeling emotions in integrated cognitive systems. In W. D. Gray (Ed.), *Integrated models of cognitive systems* (pp. 263–282). Oxford University Press. https://doi.org/10.1093/acprof:oso/9780195189193.003.0019

Jensen, A. R. (1998). *The g factor: The science of mental ability*. Praeger.

Ji, Z., Lee, N., Frieske, R., Yu, T., Su, D., Xu, Y., Ishii, E., Bang, Y., Dai, W., Madotto, A., & Fung, P. (2023). Survey of hallucination in natural language generation. *ACM Computing Surveys*, *55*(12), Article 248, 1–38. https://doi.org/10.1145/3571730

Jimenez, C. E., Yang, J., Wettig, A., Yao, S., Pei, K., Press, O., & Narasimhan, K. (2024). SWE-bench: Can language models resolve real-world GitHub issues? In *International Conference on Learning Representations (ICLR 2024)*. arXiv:2310.06770. https://arxiv.org/abs/2310.06770

Kashdan, T. B., Rose, P., & Fincham, F. D. (2004). Curiosity and exploration: Facilitating positive subjective experiences and personal growth opportunities. *Journal of Personality Assessment*, *82*(3), 291–305. https://doi.org/10.1207/s15327752jpa8203_05

Kashdan, T. B., Stiksma, M. C., Disabato, D. J., McKnight, P. E., Bekier, J., Kaji, J., & Lazarus, R. (2018). The Five-Dimensional Curiosity Scale: Capturing the bandwidth of curiosity and identifying four unique subgroups of curious people. *Journal of Research in Personality*, *73*, 130–149. https://doi.org/10.1016/j.jrp.2017.11.011

Kim, K. H. (2006). Can we trust creativity tests? A review of the Torrance Tests of Creative Thinking (TTCT). *Creativity Research Journal*, *18*(1), 3–14. https://doi.org/10.1207/s15326934crj1801_2

Kohlberg, L. (1969). Stage and sequence: The cognitive-developmental approach to socialization. In D. A. Goslin (Ed.), *Handbook of socialization theory and research* (pp. 347–480). Rand McNally.

Korbak, T., Balesni, M., Barnes, E., Bengio, Y., Chen, J., Cundy, C., Davidson, T., Denison, C., Fist, J., Hubinger, E., Jermyn, A., Leike, J., MacDiarmid, M., Marks, S., Mu, T., Nanda, N., Olah, C., Olsson, C., Phuong, M., … & Wood, D. (2025). *Chain of thought monitorability: A new and fragile opportunity for AI safety*. arXiv. https://arxiv.org/abs/2507.05246

Koriat, A. (1993). How do we know that we know? The accessibility model of the feeling of knowing. *Psychological Review*, *100*(4), 609–639. https://doi.org/10.1037/0033-295X.100.4.609

Laird, J. E. (2012). *The Soar cognitive architecture*. MIT Press.

Laird, J. E., Lebiere, C., & Rosenbloom, P. S. (2017). A standard model of the mind: Toward a common computational framework across artificial intelligence, cognitive science, neuroscience, and robotics. *AI Magazine*, *38*(4), 13–26. https://doi.org/10.1609/aimag.v38i4.2744

Larue, O., West, R., Rosenbloom, P. S., Dancy, C. L., Samsonovich, A. V., Petters, D., & Juvina, I. (2018). Emotion in the Common Model of Cognition. *Procedia Computer Science*, *145*, 740–746. https://doi.org/10.1016/j.procs.2018.11.045


Liedtka, J. M. (1998). Strategic thinking: Can it be taught? *Long Range Planning*, *31*(1), 120–129. https://doi.org/10.1016/S0024-6301(97)00098-8

Lin, S., Hilton, J., & Evans, O. (2022). TruthfulQA: Measuring how models mimic human falsehoods. In *Proceedings of the 60th Annual Meeting of the Association for Computational Linguistics* (pp. 3214–3252). ACL. https://doi.org/10.18653/v1/2022.acl-long.229

Lombardo, M. M., & Eichinger, R. W. (2000). High potentials as high learners. *Human Resource Management*, *39*(4), 321–330. https://doi.org/10.1002/1099-050X(200024)39:4<321::AID-HRM4>3.0.CO;2-1

Mayer, J. D., Roberts, R. D., & Barsade, S. G. (2008). Human abilities: Emotional intelligence. *Annual Review of Psychology*, *59*, 507–536. https://doi.org/10.1146/annurev.psych.59.103006.093646

Mayer, J. D., Salovey, P., & Caruso, D. R. (2002). *Mayer-Salovey-Caruso Emotional Intelligence Test (MSCEIT) user's manual*. Multi-Health Systems.

Mayer, J. D., Salovey, P., & Caruso, D. R. (2004). Emotional intelligence: Theory, findings, and implications. *Psychological Inquiry*, *15*(3), 197–215. https://doi.org/10.1207/s15327965pli1503_02

McGrew, K. S. (2009). CHC theory and the human cognitive abilities project: Standing on the shoulders of the giants of psychometric intelligence research. *Intelligence*, *37*(1), 1–10.

McGrew, K. S. (2022). The Cognitive-Affective-Motivation Model of Learning (CAMML): Standing on the shoulders of giants. *Canadian Journal of School Psychology*, *37*(1), 117–134. https://doi.org/10.1177/08295735211054270

McGrew, K. S., Schneider, W. J., Decker, S. L., & Bulut, O. (2023). A psychometric network analysis of CHC intelligence measures: Implications for research, theory, and interpretation of broad CHC scores "beyond g." *Journal of Intelligence*, *11*(1), 19. https://doi.org/10.3390/jintelligence11010019

Meadows, D. H. (2008). *Thinking in systems: A primer* (D. Wright, Ed.). Chelsea Green.

Mednick, S. A. (1962). The associative basis of the creative process. *Psychological Review*, *69*(3), 220–232. https://doi.org/10.1037/h0048850

Miyake, A., Friedman, N. P., Emerson, M. J., Witzki, A. H., Howerter, A., & Wager, T. D. (2000). The unity and diversity of executive functions and their contributions to complex "frontal lobe" tasks: A latent variable analysis. *Cognitive Psychology*, *41*(1), 49–100.

Morris, M. R., Altman, D., Belfield, H., Goemans, A., Iqbal, H., Burnell, R., et al. (2026). *Characterizing model jaggedness supports safety and usability* [Preprint]. https://cs.stanford.edu/~merrie/papers/jaggedness_preprint.pdf

Moshman, D. (2018). Metacognitive theories revisited. *Educational Psychology Review*, *30*(2), 599–606.

Newell, A. (1990). *Unified theories of cognition*. Harvard University Press.

Newell, A., & Simon, H. A. (1972). *Human problem solving*. Prentice-Hall.

OECD. (2025). *Introducing the OECD AI Capability Indicators*. OECD Publishing. https://doi.org/10.1787/be745f04-en

Park, Y. (Ed.). (2019). *DQ global standards report 2019: Common framework for digital literacy, skills and readiness*. DQ Institute. https://www.dqinstitute.org/wp-content/uploads/2019/03/DQGlobalStandardsReport2019.pdf

Ployhart, R. E., & Bliese, P. D. (2006). Individual adaptability (I-ADAPT) theory: Conceptualizing the antecedents, consequences, and measurement of individual differences in adaptability. In C. S. Burke, L. G. Pierce, & E. Salas (Eds.), *Understanding adaptability: A prerequisite for effective performance within complex environments* (pp. 3–39). Emerald Group Publishing.

Protzko, J., & Colom, R. (2021). A new beginning of intelligence research. Designing the playground. *Intelligence*, *87*, 101559. https://doi.org/10.1016/j.intell.2021.101559

Rest, J. R., Narvaez, D., Bebeau, M. J., & Thoma, S. J. (1999). *Postconventional moral thinking: A neo-Kohlbergian approach*. Lawrence Erlbaum Associates.

Román-González, M., Pérez-González, J.-C., & Jiménez-Fernández, C. (2017). Which cognitive abilities underlie computational thinking? Criterion validity of the Computational Thinking Test. *Computers in Human Behavior*, *72*, 678–691. https://doi.org/10.1016/j.chb.2016.08.047

Rosenbloom, P. S., Demski, A., & Ustun, V. (2016). The Sigma cognitive architecture and system: Toward functionally elegant grand unification. *Journal of Artificial General Intelligence*, *7*(1), 1–103. https://doi.org/10.1515/jagi-2016-0001

Runco, M. A., & Jaeger, G. J. (2012). The standard definition of creativity. *Creativity Research Journal*, *24*(1), 92–96. https://doi.org/10.1080/10400419.2012.650092

Ryan, R. M., & Deci, E. L. (2000). Self-determination theory and the facilitation of intrinsic motivation, social development, and well-being. *American Psychologist*, *55*(1), 68–78. https://doi.org/10.1037/0003-066X.55.1.68

Saarinen, E., & Hämäläinen, R. P. (2004). Systems intelligence: Connecting engineering thinking with human sensitivity. In R. P. Hämäläinen & E. Saarinen (Eds.), *Systems intelligence: Discovering a hidden competence in human action and organizational life* (pp. 9–37). Helsinki University of Technology, Systems Analysis Laboratory Research Reports A88.

Salovey, P., & Mayer, J. D. (1990). Emotional intelligence. *Imagination, Cognition and Personality*, *9*(3), 185–211.

Schneider, W. J., & McGrew, K. S. (2018). The Cattell-Horn-Carroll theory of cognitive abilities. In D. P. Flanagan & E. M. McDonough (Eds.), *Contemporary intellectual assessment: Theories, tests, and issues* (4th ed., pp. 73–163). Guilford Press.

Schraw, G., & Dennison, R. S. (1994). Assessing metacognitive awareness. *Contemporary Educational Psychology*, *19*(4), 460–475. https://doi.org/10.1006/ceps.1994.1033

Schraw, G., & Moshman, D. (1995). Metacognitive theories. *Educational Psychology Review*, *7*(4), 351–371. https://doi.org/10.1007/BF02212307

Senge, P. M. (1990). *The fifth discipline: The art and practice of the learning organization*. Doubleday/Currency.

Sisk, V. F., Burgoyne, A. P., Sun, J., Butler, J. L., & Macnamara, B. N. (2018). To what extent and under which circumstances are growth mindsets important to academic achievement? Two meta-analyses. *Psychological Science*, *29*(4), 549–571. https://doi.org/10.1177/0956797617739704

Spearman, C. (1904). "General intelligence," objectively determined and measured. *American Journal of Psychology*, *15*(2), 201–293.

Sterman, J. D. (2000). *Business dynamics: Systems thinking and modeling for a complex world*. Irwin/McGraw-Hill.

Sternberg, R. J. (1985). *Beyond IQ: A triarchic theory of human intelligence*. Cambridge University Press.

Sternberg, R. J. (1999). The theory of successful intelligence. *Review of General Psychology*, *3*(4), 292–316. https://doi.org/10.1037/1089-2680.3.4.292

Stoltz, P. G. (1997). *Adversity quotient: Turning obstacles into opportunities*. John Wiley & Sons.

Sumers, T. R., Yao, S., Narasimhan, K., & Griffiths, T. L. (2024). Cognitive architectures for language agents. *Transactions on Machine Learning Research*. arXiv:2309.02427. https://arxiv.org/abs/2309.02427

Tetlock, P. E. (2005). *Expert political judgment: How good is it? How can we know?* Princeton University Press.

Tolan, S., Pesole, A., Martínez-Plumed, F., Fernández-Macías, E., Hernández-Orallo, J., & Gómez, E. (2021). Measuring the occupational impact of AI: Tasks, cognitive abilities and AI benchmarks. *Journal of Artificial Intelligence Research*, *71*, 191–236. https://doi.org/10.1613/jair.1.12647

Tetlock, P. E., & Gardner, D. (2015). *Superforecasting: The art and science of prediction*. Crown.

Thorndike, E. L. (1920). Intelligence and its uses. *Harper's Magazine*, *140*, 227–235.

Torrance, E. P. (1974). *Torrance Tests of Creative Thinking: Norms–technical manual*. Personnel Press.

Törmänen, J., Hämäläinen, R. P., & Saarinen, E. (2016). Systems intelligence inventory. *The Learning Organization*, 23(4), 218–231. https://doi.org/10.1108/TLO-01-2016-0006

van der Maas, H. L. J., Savi, A. O., Hofman, A., Kan, K.-J., & Marsman, M. (2019). The network approach to general intelligence. In D. J. McFarland (Ed.), *General and specific mental abilities* (pp. 108–131). Cambridge Scholars Publishing.

Waterhouse, L. (2006). Multiple intelligences, the Mozart effect, and emotional intelligence: A critical review. *Educational Psychologist*, *41*(4), 207–225. https://doi.org/10.1207/s15326985ep4104_1

Wineburg, S., & McGrew, S. (2019). Lateral reading and the nature of expertise: Reading less and learning more when evaluating digital information. *Teachers College Record*, *121*(11), 1–40. https://doi.org/10.1177/016146811912101102

Wing, J. M. (2006). Computational thinking. *Communications of the ACM*, *49*(3), 33–35. https://doi.org/10.1145/1118178.1118215

Wing, J. M. (2008). Computational thinking and thinking about computing. *Philosophical Transactions of the Royal Society A*, *366*(1881), 3717–3725.

Wing, J. M. (2017). Computational thinking's influence on research and education for all. *Italian Journal of Educational Technology*, *25*(2), 7–14. https://doi.org/10.17471/2499-4324/922

Wray, R. E., Kirk, J. R., & Laird, J. E. (2025). Applying cognitive design patterns to general LLM agents. In *Proceedings of the 18th International Conference on Artificial General Intelligence (AGI 2025)*. Lecture Notes in Computer Science (vol. 16058). Springer. https://arxiv.org/abs/2505.07087

Yao, S., Shinn, N., Razavi, P., & Narasimhan, K. (2024). τ-bench: A benchmark for tool-agent-user interaction in real-world domains. arXiv:2406.12045. https://arxiv.org/abs/2406.12045

Zhou, L., Pacchiardi, L., Martínez-Plumed, F., Collins, K. M., Moros-Daval, Y., … Hernández-Orallo, J. (2026). General scales unlock AI evaluation with explanatory and predictive power. *Nature*. https://doi.org/10.1038/s41586-026-10303-2

Zhou, S., Xu, F. F., Zhu, H., Zhou, X., Lo, R., Sridhar, A., Cheng, X., Ou, T., Bisk, Y., Fried, D., Alon, U., & Neubig, G. (2024). WebArena: A realistic web environment for building autonomous agents. In *International Conference on Learning Representations (ICLR 2024)*. arXiv:2307.13854. https://arxiv.org/abs/2307.13854

---

## Appendix A. Full HCQM Hierarchical Structure

The following is the canonical HCQM tree (v0.1). Each entry specifies the definition, subcomponents, and behavioral indicators. This material is reproduced from the HCQM project repository (https://github.com/hgenix20/hcqm) as the definitional reference for the framework.

### Domain 1: General Cognitive Intelligence
*Definition: Raw mental power for reasoning, understanding, and manipulating information.*

- **1.1 IQ (General Intelligence).** Aggregate reasoning ability across cognitive tasks. *Subcomponents:* abstract, verbal, quantitative, inductive, deductive reasoning. *Indicators:* solves unfamiliar problems accurately; detects underlying rules quickly; understands complexity with limited explanation; handles multi-variable reasoning effectively.
- **1.2 Fluid Intelligence (Gf).** Ability to solve new problems without relying on prior learned knowledge. *Subcomponents:* novel problem solving, pattern abstraction, rule inference, relational reasoning. *Indicators:* performs well in unfamiliar environments; infers structure from sparse data; adapts reasoning when rules change; builds new mental models quickly.
- **1.3 Crystallized Intelligence (Gc).** Accumulated knowledge, vocabulary, and conceptual understanding. *Subcomponents:* vocabulary depth, domain knowledge, semantic memory, conceptual understanding. *Indicators:* explains concepts clearly; draws on relevant prior knowledge; uses terminology accurately; recognizes deep analogies from experience.
- **1.4 Visual-Spatial Intelligence.** Ability to perceive, imagine, rotate, and manipulate spatial relationships. *Subcomponents:* mental rotation, spatial visualization, navigation and orientation, structural mapping. *Indicators:* understands diagrams and layouts quickly; visualizes object movement in space; maps relationships between parts and wholes; excels in geometry, design, or 3D reasoning.
- **1.5 Processing Speed.** Speed of perceiving, comparing, and responding to information. *Subcomponents:* visual scanning speed, comparison speed, symbol recognition, mental throughput. *Indicators:* completes routine cognitive tasks rapidly; maintains pace under information density; quickly notices relevant differences; responds with low lag in structured tasks.
- **1.6 Working Memory Capacity.** Ability to hold and manipulate information in mind temporarily. *Subcomponents:* verbal working memory, visual-spatial working memory, updating capacity, interference resistance. *Indicators:* keeps track of multiple variables at once; holds steps in mind during complex reasoning; maintains context during long chains of thought; resists losing track under interruption. [OVERLAP FLAG: "resists losing track under interruption" overlaps with 2.2 indicator "stays focused despite noise or interruption"; see §6.2.]

### Domain 2: Executive / Self-Regulatory Intelligence
*Definition: Control layer for attention, behavior, goals, and thinking processes.*

- **2.1 Metacognitive Intelligence (MQ).** Awareness and regulation of one's own thinking. *Subcomponents:* self-monitoring, error detection, strategy selection, self-regulation of thinking, learning optimization, confidence calibration, reflection quality. *Indicators:* notices when understanding is weak; detects mistakes before external feedback; switches strategy when current approach fails; evaluates certainty realistically; improves performance through self-correction.
- **2.2 Cognitive Control.** Ability to direct attention toward task-relevant goals. *Subcomponents:* sustained attention, selective attention, focus maintenance, distractor suppression. *Indicators:* stays focused despite noise or interruption; maintains task direction over time; filters irrelevant stimuli effectively; avoids frequent context drift.
- **2.3 Cognitive Flexibility.** Ability to shift between mental models, rules, or perspectives. *Subcomponents:* task switching, rule switching, perspective shifting, reframing. *Indicators:* adapts quickly to changing demands; reframes problems productively; avoids rigid attachment to one model; handles exceptions without breaking down.
- **2.4 Strategic Planning.** Ability to sequence actions toward long-range objectives. *Subcomponents:* goal decomposition, sequencing, contingency planning, resource allocation, time horizon reasoning. *Indicators:* works backward from desired outcomes; anticipates dependencies and bottlenecks; allocates effort where leverage is highest; maintains coherence across multiple steps.
- **2.5 Inhibitory Control.** Ability to suppress impulses or incorrect default responses. *Subcomponents:* impulse inhibition, response suppression, emotional restraint, premature closure avoidance. *Indicators:* pauses before reacting; avoids low-quality quick answers; resists distraction or temptation; suppresses emotionally driven missteps.

### Domain 3: Emotional & Social Intelligence
*Definition: Capacity to understand emotions, relationships, and social systems.*

- **3.1 Emotional Intelligence (EQ).** Ability to perceive, understand, regulate, and use emotions effectively. *Subcomponents:* emotional awareness, emotional labeling, emotional regulation, empathy, emotional expression. *Indicators:* identifies emotional states accurately; manages emotional intensity under stress; responds rather than reacts; understands emotional signals in self and others.
- **3.2 Social Intelligence (SQ).** Ability to interpret and navigate social dynamics effectively. *Subcomponents:* social cue reading, status and role awareness, trust formation, influence, conflict navigation. *Indicators:* reads group dynamics accurately; adjusts communication to audience and context; recognizes hidden motives and incentives; navigates disagreement without unnecessary escalation.
- **3.3 Cultural Intelligence (CQ).** Ability to operate effectively across cultures and norm systems. *Subcomponents:* cultural awareness, norm interpretation, cross-context adaptation, perspective taking. *Indicators:* recognizes culture-bound assumptions; adapts behavior to different contexts appropriately; avoids misreading unfamiliar norms; communicates effectively across backgrounds.
- **3.4 Interpersonal Awareness.** Fine-grained understanding of others' needs, intentions, and boundaries. *Subcomponents:* listening depth, intention inference, boundary sensitivity, relational memory. *Indicators:* notices subtle shifts in tone or engagement; tracks relational context over time; detects unspoken needs or concerns; respects and navigates interpersonal limits well.

### Domain 4: Creative & Innovation Intelligence
*Definition: Capacity to generate useful novelty and transform it into workable ideas.*

- **4.1 Creativity Quotient.** Overall ability to generate original and valuable ideas. *Subcomponents:* originality, idea fluency, elaboration, usefulness. *Indicators:* produces ideas that are both novel and relevant; generates options under constraints; builds raw ideas into stronger concepts; avoids cliché solution patterns.
- **4.2 Divergent Thinking.** Ability to produce multiple possible answers or directions. *Subcomponents:* ideational fluency, flexibility, originality, possibility expansion. *Indicators:* generates many plausible alternatives; shifts angles without fixation; moves beyond first-obvious answers; produces broad option sets quickly.
- **4.3 Associative Thinking.** Ability to connect distant concepts into meaningful combinations. *Subcomponents:* analogical reasoning, cross-domain linkage, concept blending, metaphorical mapping. *Indicators:* connects ideas across unrelated domains; finds hidden structural similarities; creates coherent syntheses from distant concepts; produces unconventional but valid insights.

### Domain 5: Motivational & Adaptive Intelligence
*Definition: Capacity to sustain effort, adapt under change, and recover under stress.*

- **5.1 Curiosity Quotient.** Drive to explore, question, and seek understanding. *Subcomponents:* epistemic curiosity, question generation, novelty seeking, exploration persistence. *Indicators:* asks high-quality questions; pursues understanding beyond surface answers; explores new domains voluntarily; maintains inquiry despite ambiguity.
- **5.2 Adaptability Quotient.** Ability to adjust effectively to new demands, tools, and conditions. *Subcomponents:* change tolerance, rapid adjustment, context sensitivity, behavioral flexibility. *Indicators:* recovers quickly after change; learns new systems without extended resistance; modifies behavior to fit new constraints; operates effectively in ambiguity.
- **5.3 Adversity Quotient.** Ability to withstand setbacks, pressure, and difficulty. *Subcomponents:* frustration tolerance, stress endurance, recovery capacity, setback resilience. *Indicators:* continues functioning under pressure; bounces back after failure; does not collapse after setbacks; maintains effort despite discomfort. [UNIQUE COVERAGE FLAG: no direct equivalent in DeepMind (2026) or CoALA (Sumers et al., 2024); see Appendices D, E.]
- **5.4 Grit / Persistence.** Sustained effort and commitment toward long-term goals. *Subcomponents:* long-term consistency, effort maintenance, delayed gratification, goal commitment. *Indicators:* continues work across long time horizons; resists quitting during plateaus; maintains focus on valued goals; invests effort when rewards are delayed.

### Domain 6: Learning & Knowledge Intelligence
*Definition: Capacity to acquire, integrate, retain, and transfer knowledge.*

- **6.1 Learning Agility.** Speed and quality of learning from experience and feedback. *Subcomponents:* feedback uptake, rapid skill acquisition, experimentation, self-correction. *Indicators:* learns quickly from mistakes; improves performance after feedback; experiments without excessive hesitation; transfers lessons across attempts.
- **6.2 Knowledge Integration.** Ability to combine separate information into coherent mental models. *Subcomponents:* synthesis, schema formation, contradiction reconciliation, concept linking. *Indicators:* combines fragmented information into a whole; builds stable conceptual frameworks; resolves conflicts between ideas productively; understands relationships between concepts.
- **6.3 Transfer Intelligence.** Ability to apply knowledge from one context to another. *Subcomponents:* principle extraction, analogical transfer, context adaptation, abstraction. *Indicators:* applies lessons from one domain to another; recognizes reusable principles; adapts known methods to new problems; moves from examples to general rules.

### Domain 7: Digital & Technological Intelligence
*Definition: Capability to operate effectively in digital, informational, and computational environments.*

- **7.1 Digital Intelligence (DQ).** Broad digital fluency, judgment, and effectiveness. *Subcomponents:* digital fluency, platform navigation, digital identity awareness, cyber-risk awareness. *Indicators:* uses digital tools effectively; understands platform norms and risks; protects data and account integrity; learns software environments quickly.
- **7.2 Information Literacy.** Ability to find, assess, verify, and synthesize information. *Subcomponents:* source evaluation, credibility filtering, bias detection, search strategy, evidence synthesis. *Indicators:* distinguishes strong from weak sources; verifies claims before accepting them; handles conflicting evidence productively; avoids being misled by confidence alone.
- **7.3 Computational Thinking.** Ability to structure problems in logical, modelable, automatable ways. *Subcomponents:* decomposition, pattern recognition, abstraction, algorithmic reasoning. *Indicators:* breaks large problems into manageable parts; recognizes repeatable logic patterns; converts messy processes into structured flows; designs stepwise solutions that can be executed or automated.

### Domain 8: Systems & Strategic Intelligence
*Definition: Capacity to understand interdependent systems and act effectively across time.*

- **8.1 Systems Intelligence.** Ability to understand interacting parts within a larger whole. *Subcomponents:* causal mapping, feedback loop recognition, interdependence awareness, constraint recognition, leverage point detection. *Indicators:* sees root causes rather than just symptoms; understands second-order interactions; detects why local fixes may fail globally; identifies high-leverage intervention points.
- **8.2 Strategic Intelligence.** Ability to make effective long-range choices under competition and uncertainty. *Subcomponents:* objective clarity, positioning, tradeoff evaluation, sequencing, long-horizon reasoning. *Indicators:* chooses paths aligned to desired outcomes; manages tradeoffs consciously; anticipates downstream consequences; coordinates action over time rather than reacting moment to moment.
- **8.3 Pattern Intelligence.** Ability to detect recurring structures across data, behavior, and events. *Subcomponents:* signal extraction, trend recognition, anomaly detection, pattern compression. *Indicators:* notices repeat structures quickly; distinguishes signal from noise; detects meaningful deviations from baseline; compresses complexity into understandable patterns.
- **8.4 Predictive Intelligence.** Ability to anticipate probable outcomes from patterns and causal models. *Subcomponents:* forecasting, scenario modeling, probability judgment, confidence calibration. *Indicators:* anticipates likely next states accurately; models multiple possible futures; updates predictions with new evidence; assigns confidence with reasonable realism.

---

## Appendix B. Indicator Catalog

The complete set of indicators is embedded in Appendix A. Indicators are grouped by capability rather than enumerated separately here to avoid redundancy.

**Note on indicator extraction.** For final submission and for instrument development use, the indicators in Appendix A admit a flat tabular extraction (one row per indicator, with domain/capability/subcomponent codes). A canonical CSV will accompany a future release.

---

## Appendix C. Concept-to-Source Mapping

The table below maps each HCQM capability to its primary source literature. Where multiple sources apply, the most directly foundational is listed first.

| HCQM capability                    | Primary source(s)                                                        |
| ---------------------------------- | ------------------------------------------------------------------------ |
| 1.1 IQ                             | Spearman (1904); Carroll (1993); McGrew (2009)                           |
| 1.2 Fluid Intelligence (Gf)        | Cattell (1963); Horn & Cattell (1966); Carroll (1993)                    |
| 1.3 Crystallized Intelligence (Gc) | Cattell (1963); Horn & Cattell (1966); Carroll (1993)                    |
| 1.4 Visual-Spatial Intelligence    | Carroll (1993); Schneider & McGrew (2018)                                |
| 1.5 Processing Speed               | Carroll (1993); Schneider & McGrew (2018)                                |
| 1.6 Working Memory                 | Baddeley & Hitch (1974); Baddeley (2000); Engle (2002)                   |
| 2.1 Metacognitive Intelligence     | Flavell (1979); Schraw & Moshman (1995); Moshman (2018)                  |
| 2.2 Cognitive Control              | Miyake et al. (2000); Diamond (2013)                                     |
| 2.3 Cognitive Flexibility          | Miyake et al. (2000); Diamond (2013)                                     |
| 2.4 Strategic Planning             | Newell & Simon (1972); Diamond (2013)                                    |
| 2.5 Inhibitory Control             | Miyake et al. (2000); Diamond (2013)                                     |
| 3.1 Emotional Intelligence         | Salovey & Mayer (1990); Mayer, Salovey, & Caruso (2004); Goleman (1995)  |
| 3.2 Social Intelligence            | Thorndike (1920)                                                         |
| 3.3 Cultural Intelligence          | Earley & Ang (2003); Ang & Van Dyne (2008)                               |
| 3.4 Interpersonal Awareness        | [composite of social-cognition and theory-of-mind literatures; see §2.4] |
| 4.1 Creativity Quotient            | Guilford (1950); Runco & Jaeger (2012)                                   |
| 4.2 Divergent Thinking             | Guilford (1950); Torrance (1974)                                         |
| 4.3 Associative Thinking           | Mednick (1962); Benedek & Neubauer (2013)                                |
| 5.1 Curiosity Quotient             | Kashdan et al. (2004, 2018); Ryan & Deci (2000)                          |
| 5.2 Adaptability Quotient          | Ployhart & Bliese (2006)                                                 |
| 5.3 Adversity Quotient             | Stoltz (1997)                                                            |
| 5.4 Grit / Persistence             | Duckworth et al. (2007); Duckworth & Quinn (2009)                        |
| 6.1 Learning Agility               | De Meuse, Dai, & Hallenbeck (2010); Lombardo & Eichinger (2000)          |
| 6.2 Knowledge Integration          | Bransford, Brown, & Cocking (2000)                                       |
| 6.3 Transfer Intelligence          | Barnett & Ceci (2002)                                                    |
| 7.1 Digital Intelligence           | Park (2019); DQ Institute (2019)                                         |
| 7.2 Information Literacy           | Wineburg & McGrew (2019); ACRL Framework (2016)                          |
| 7.3 Computational Thinking         | Wing (2006, 2008, 2017)                                                  |
| 8.1 Systems Intelligence           | Senge (1990); Meadows (2008); Forrester (1961); Sterman (2000)           |
| 8.2 Strategic Intelligence         | Liedtka (1998); management-strategy literature                           |
| 8.3 Pattern Intelligence           | Heuer (1999); perception-research tradition                              |
| 8.4 Predictive Intelligence        | Tetlock (2005); Tetlock & Gardner (2015)                                 |

**Note on this mapping.** The mapping above is deliberately conservative. Where "[composite of …]" or reference to a broader literature appears rather than a single source, the capability in HCQM is assembled from multiple threads rather than inherited intact. Future revisions should (a) add secondary and tertiary sources where relevant, (b) distinguish theoretical sources from measurement-instrument sources, and (c) flag capabilities where the HCQM operationalization diverges from any single source.

---

## Appendix D. Comparison with DeepMind (2026) Cognitive Taxonomy

The DeepMind *Measuring Progress Toward AGI: A Cognitive Framework* (Burnell et al., 2026) identifies ten cognitive abilities: perception, generation, attention, learning, memory, reasoning, metacognition, executive functions, problem solving, and social cognition. Table D.1 shows the approximate mapping to HCQM domains.

**Table D.1. DeepMind 2026 faculty → HCQM location.**

| DeepMind (2026) ability | Approximate HCQM location |
|---|---|
| Perception | Not directly represented (scoping choice; HCQM omits sensory perception) |
| Generation | Not directly represented (output-layer property rather than capability) |
| Attention | Domain 2.2 (Cognitive Control) |
| Learning | Domain 6.1 (Learning Agility); Domain 6.2–6.3 (broader) |
| Memory | Domain 1.3 (Gc); Domain 1.6 (Working Memory) |
| Reasoning | Domain 1.1–1.2 (IQ, Gf); also Domain 8 (systems/strategic reasoning) |
| Metacognition | Domain 2.1 (Metacognitive Intelligence) |
| Executive functions | Domain 2 (entire domain: Control, Flexibility, Planning, Inhibition) |
| Problem solving | Domain 1 + Domain 2.4 + Domain 8 (distributed) |
| Social cognition | Domain 3.1–3.2 (EQ, SQ); partial overlap with 3.4 |

**HCQM capabilities *not* substantially represented in the DeepMind taxonomy:** Cultural Intelligence (3.3), Creative & Innovation Intelligence (Domain 4), Motivational & Adaptive Intelligence (Domain 5, particularly Grit and Adversity Quotient), Digital & Technological Intelligence (Domain 7), and Systems & Strategic Intelligence (Domain 8).

**DeepMind capabilities *not* substantially represented in HCQM:** Perception (sensory processing), Generation (output production). These omissions are deliberate in HCQM's scoping: HCQM focuses on cognitive and affective capability structure above the sensory and output levels. For embodied AI systems, HCQM would need to be extended at its boundaries with sensory-processing and action-generation layers.

The two frameworks are best understood as complementary rather than competing. DeepMind's is optimized for AGI progress measurement against human baselines in ten cognitive faculties. HCQM's is optimized for breadth of capability coverage and for dual-use human/synthetic application. The DeepMind evaluation protocol (cognitive assessment → human baselines → cognitive profiles) provides a methodological template that an eventual HCQM evaluation protocol could adapt (see §6.6).

The five DeepMind evaluation-gap areas (learning, metacognition, attention, executive functions, social cognition) all map to HCQM domains, so community-built evaluations developed through the DeepMind/Kaggle hackathon should be directly usable for HCQM assessment in those domains.

---

## Appendix E. Comparison with CoALA (Sumers et al., 2024)

Sumers, Yao, Narasimhan, and Griffiths (2024) introduced the CoALA framework (*Cognitive Architectures for Language Agents*) in *Transactions on Machine Learning Research*. CoALA organizes language agents along three dimensions: memory modules, structured action space, and decision-making procedure. This appendix reports a gradient-match analysis across all 14 CoALA sub-concepts.

**Gradient rubric:**
- **Full (1.0):** direct conceptual equivalence
- **Strong (0.75):** significant overlap; minor scope/emphasis differences
- **Partial (0.5):** meaningful but incomplete overlap
- **Weak (0.25):** tangential conceptual contact
- **None (0.0):** no HCQM equivalent present

### E.1 Memory modules (CoALA §4)

| CoALA construct | HCQM construct(s) | Match |
|---|---|---|
| Working Memory (persistence across LLM calls) | 1.6 Working Memory Capacity | Strong (0.75) |
| Episodic Memory (stored experience sequences) | 6.1 Learning Agility (feedback uptake) | Partial (0.5) |
| Semantic Memory (world and self knowledge) | 1.3 Crystallized Intelligence (Gc) | Strong (0.75) |
| Semantic Memory (self-knowledge subset) | 2.1 Metacognitive Intelligence (self-monitoring) | Partial (0.5) |
| Procedural Memory (LLM weights / implicit) | 1.2 Fluid Intelligence + 1.3 Crystallized | Weak (0.25) |
| Procedural Memory (agent code / explicit) | 7.3 Computational Thinking | Partial (0.5) |

**Notes:** HCQM does not cleanly represent episodic and procedural memory as distinct types. It currently folds episodic memory implicitly inside Learning Agility and procedural memory inside Computational Thinking. Section 6.9 flags this as a future refinement: consider promoting episodic and procedural memory to standalone constructs inside Domain 1 or Domain 6.

### E.2 Action space, internal actions (CoALA §5.1)

| CoALA construct | HCQM construct(s) | Match |
|---|---|---|
| Reasoning (read/write working memory; generate) | 1.1 IQ, 1.2 Fluid Intelligence, 2.1 Metacognitive, 6.2 Knowledge Integration | Strong (0.75) |
| Retrieval (read from long-term memory) | 1.3 Crystallized Intelligence; 7.2 Information Literacy | Partial (0.5) |
| Learning (write to episodic) | 6.1 Learning Agility | Partial (0.5) |
| Learning (write to semantic) | 6.2 Knowledge Integration | Partial (0.5) |
| Learning (write to procedural) | 6.3 Transfer Intelligence + 7.3 Computational Thinking | Weak (0.25) |

**Notes:** CoALA's read/write/generate trichotomy is architecturally useful but is not a capability distinction. A human who excels at encoding but struggles at retrieval is psychometrically describable, but HCQM does not currently capture this. Consider adding indicators for retrieval-specific capacity under 1.3 or 1.6. CoALA's "reasoning" also conflates what HCQM separates into Fluid (novel), Crystallized (applied), Metacognitive (monitored), and Knowledge Integration (synthetic) reasoning, a place where HCQM adds resolution that CoALA collapses for engineering tractability.

### E.3 Action space, external grounding (CoALA §5.2)

| CoALA construct | HCQM construct(s) | Match |
|---|---|---|
| Physical Grounding (sensors/actuators) | 1.4 Visual-Spatial Intelligence (perception side); 1.5 Processing Speed | Partial (0.5) |
| Dialogue Grounding (human-agent) | 3.1 EQ, 3.2 SQ, 3.4 Interpersonal Awareness | Strong (0.75) |
| Digital Grounding (APIs, code, websites) | 7.1 Digital Intelligence, 7.3 Computational Thinking | Strong (0.75) |

**Notes:** HCQM v0.1 lacks a construct for embodied motor action. CoALA's grounding concept exposes a potential new HCQM construct (**cross-modal translation** or **modality bridging**) covering the capacity to convert between perceptual, symbolic, and motor representations. No current HCQM construct covers this explicitly. See §6.8.

### E.4 Decision-making procedure (CoALA §5.3)

| CoALA construct | HCQM construct(s) | Match |
|---|---|---|
| Planning: Proposal | 4.2 Divergent Thinking; 2.4 Strategic Planning | Strong (0.75) |
| Planning: Evaluation | 8.4 Predictive Intelligence; 2.1 Metacognitive | Strong (0.75) |
| Planning: Selection | 8.2 Strategic Intelligence; 2.5 Inhibitory Control | Strong (0.75) |
| Execution | 2.2 Cognitive Control; 2.4 Strategic Planning (sequencing) | Partial (0.5) |
| Overall decision loop | 2.1 Metacognitive + 8.2 Strategic | Strong (0.75) |

**Notes:** CoALA's explicit propose → evaluate → select → execute decomposition is an architectural primitive not captured directly in HCQM. HCQM distributes decision-making across capacity-level constructs. The CoALA decision loop is a process-level abstraction; HCQM treats each step as a latent capacity. This motivates a future annotation that HCQM capabilities have two facets: **static capacity** (measurable at a point in time) and **dynamic process** (enacted within a decision loop). Metareasoning (adaptive allocation of reasoning compute), flagged in CoALA §6 as an open research direction, has no explicit HCQM construct; a new subcomponent under 2.1 (e.g., *cognitive resource allocation / reasoning budget control*) is proposed in §6.9. A design note on the metacognition row: the CMC is explicitly silent on metacognition (Laird et al., 2017), and Soar treats it as behavior emerging from general problem-space reasoning rather than as a dedicated module (Laird, 2012). HCQM's capacity-layer framing is consistent with this position: the mapping of "Planning: Evaluation" and "Overall decision loop" to 2.1 Metacognitive reflects a capacity target, not a claim that metacognition must be implemented as a distinct architectural slot.

### E.5 HCQM domains with no CoALA equivalent

| HCQM domain/construct | CoALA equivalent | Match |
|---|---|---|
| 3.1 Emotional Intelligence | (none) | None (0.0) |
| 3.3 Cultural Intelligence | (none) | None (0.0) |
| 4.1 Creativity Quotient | (none) | None (0.0) |
| 4.2 Divergent Thinking | CoALA "proposal" step | Weak (0.25) |
| 4.3 Associative Thinking | (none) | None (0.0) |
| 5.1 Curiosity Quotient | (none) | None (0.0) |
| 5.2 Adaptability Quotient | CoALA mentions adaptation in decision-making | Weak (0.25) |
| 5.3 Adversity Quotient | (none) | None (0.0) |
| 5.4 Grit / Persistence | (none) | None (0.0) |
| 8.3 Pattern Intelligence | (none) | None (0.0) |

**Notes:** CoALA is silent on motivational state, emotional regulation, cultural adaptation, creative generation, adversity response, and persistence. This is expected; CoALA describes architectural scaffolding, not the drive, affect, or persistence that initiates and sustains operation within that scaffolding. This reinforces HCQM's positioning: CoALA (like DeepMind's taxonomy) is an architectural or cognitive-faculty framework that omits motivational, emotional, cultural, creative, and adversity dimensions. HCQM's coverage of these is genuine differentiation.

### E.6 Summary

**Table E.1. HCQM coverage of CoALA concepts.**

| CoALA dimension | # sub-concepts | Full | Strong | Partial | None |
|---|---|---|---|---|---|
| Memory | 4 | 0 | 2 | 2 | 0 |
| Internal Actions | 3 | 0 | 1 | 2 | 0 |
| External Grounding | 3 | 0 | 2 | 1 | 0 |
| Decision-Making | 4 | 0 | 3 | 1 | 0 |
| **Total** | **14** | **0** | **8** | **6** | **0** |

**HCQM coverage of CoALA: 14/14 have at least partial mapping.** No CoALA concept is entirely absent from HCQM.

**Reverse coverage (CoALA coverage of HCQM):** 10 HCQM constructs have zero or weak CoALA equivalents, concentrated in Domains 3, 4, 5, and parts of 8. This asymmetry is the positioning claim: HCQM extends beyond what architectural frameworks like CoALA cover.

**Cross-framework intersection check.** The table in §E.5 shows that CoALA omits a wide range of HCQM constructs (EQ, CQ, Creativity Quotient, Associative Thinking, Curiosity Quotient, AQ, Grit, Pattern Intelligence). The AI frameworks omit motivational and affective constructs broadly rather than AQ specifically; AQ is distinctive only in being absent from the *intersection* of all five (the Hernández-Orallo and Vold (2019) catalogue, Tolan et al. 2021, §2.11.6; CoALA; DeepMind 2026, Appendix D; Hendrycks et al. 2025, Appendix G; OECD 2025, Appendix H). This intersection property is a coverage observation, scoped to AI frameworks and contingent on AQ being a meaningful capability; it illustrates the coverage asymmetry developed in §2.11.8 and is not a load-bearing differentiator of the paper (see §2.5 and §4.5).

---

## Appendix F. CHC Broad-Ability → HCQM Mapping

The Cattell–Horn–Carroll integrated model (McGrew, 2009; Schneider & McGrew, 2018) specifies a set of broad cognitive abilities. HCQM Domain 1 is a compressed representation of the most commonly invoked cognitive-ability broad abilities; HCQM Domain 3 corresponds to the emotional-intelligence broad ability formally added to CHC in Schneider and McGrew (2018). Table F.1 shows the mapping between the full contemporary CHC broad-ability set and HCQM.

**Table F.1. CHC broad ability → HCQM capability.**

| Code | CHC broad ability | HCQM capability |
|---|---|---|
| Gf | Fluid reasoning | 1.2 Fluid Intelligence |
| Gc | Comprehension-knowledge | 1.3 Crystallized Intelligence |
| Gwm | Short-Term Working Memory | 1.6 Working Memory Capacity |
| Gv | Visual processing | 1.4 Visual-Spatial Intelligence |
| Ga | Auditory processing | Not represented |
| Gl | Learning Efficiency | 6.1 Learning Agility (capacity-layer correspondence); 1.3 Crystallized Intelligence (partial, via semantic-memory overlap) |
| Gr | Retrieval Fluency | 1.7 Retrieval Fluency |
| Gs | Cognitive processing speed | 1.5 Processing Speed |
| Gt | Decision and reaction speed | 1.5 Processing Speed |
| Grw | Reading and writing | Not represented (partially absorbed into 1.3 and 7.1) |
| Gq | Quantitative knowledge | 1.1 IQ (partial, via quantitative reasoning subcomponent) |
| Gkn | General (domain-specific) knowledge | 1.3 Crystallized Intelligence |
| Gei | Emotional Intelligence | 3.1 Emotional Intelligence |
| Gh | Tactile abilities | Not represented |
| Gk | Kinesthetic abilities | Not represented |
| Go | Olfactory abilities | Not represented |
| Gp | Psychomotor abilities | Not represented (partial conceptual overlap with 1.4) |
| Gps | Psychomotor speed | Not represented (partial conceptual overlap with 1.5) |

**Notes.**

1. **Gwm replaces Gsm.** The short-term-memory broad ability was renamed and redefined from Gsm (McGrew, 2009) to Gwm (Schneider & McGrew, 2018) to reflect that working memory, temporary storage with active manipulation under attentional control, is the construct of interest, not passive short-term storage.

2. **Glr split into Gl and Gr.** The older Glr (long-term storage and retrieval) was split in Schneider and McGrew (2018, pp. 85, 100–105) into Gl (Learning Efficiency) and Gr (Retrieval Fluency). The two are functionally distinct: Gl is an encoding-rate / acquisition construct; Gr is a speed/fluency construct for retrieval of already-stored material. They have different correlates and developmental trajectories (Schneider & McGrew, 2018; McGrew et al., 2023).

3. **Gr placement resolved to Domain 1 (1.7).** Gr was initially considered for HCQM 4.2 Divergent Thinking on the basis that its narrow abilities (ideational, associational, word, expressional, and figural fluency) operationalize divergent production in the Guilford–Torrance tradition. McGrew confirmed (personal communication, 2026-05-29) that Gr should remain in Domain 1 as a standalone capability (1.7 Retrieval Fluency): the narrow fluency abilities facilitate creativity but are not its core essence as defined in the literature. Carroll (1993) tentatively included narrow creativity abilities in his three-stratum model, but these were dropped from CHC Gr in subsequent revisions. Domain 4's relationship to CHC is therefore an extension framing; HCQM 1.7 holds the Gr correspondence.

4. **Gei added in 2018.** Emotional Intelligence (Gei) was added as a CHC broad ability in Schneider and McGrew (2018, pp. 87–88, 140–141). HCQM 3.1 Emotional Intelligence corresponds directly; its sub-construct decomposition was cross-checked against the published Gei ability-model structure and found consistent (2026-06-09). Other Domain 3 capabilities (3.2 Social Intelligence, 3.3 Cultural Intelligence, 3.4 Interpersonal Awareness) are not represented as CHC broad abilities but are situated alongside the cognitive-ability layer in contemporary trilogy-of-mind frameworks (Snow's aptitude complexes; McGrew, 2022, CAMML).

5. **Not represented.** Ga, Grw, Gh, Gk, Go, Gp, and Gps are not represented as HCQM capabilities; these are the sensory and psychomotor layers HCQM scopes out (§6.3). HCQM Domain 1 definitions were cross-checked against the published CHC broad-ability definitions (Schneider & McGrew, 2018; Institute for Applied Psychometrics) and found consistent (2026-06-09); a final word-for-word cross-check against the WJ V Technical Manual Appendix A is recommended as a low-risk follow-up.

---

## Appendix G. Comparison with Hendrycks et al. (2025) "A Definition of AGI"

Hendrycks et al. (2025, arXiv:2510.18212) propose a CHC-grounded definition of AGI as a system that matches "the cognitive versatility and proficiency of a well-educated adult," decomposed into ten cognitive domains, each weighted equally (10%) in the aggregate AGI score. The authors report a "jagged" cognitive profile in current systems: GPT-4 scores 27% on the aggregate scale, GPT-5 scores 57%, and both score 0% on Long-Term Memory Storage and on Hallucinations/Retrieval Precision (a sub-faculty of Long-Term Memory Retrieval). Table G.1 maps each Hendrycks domain to its approximate HCQM location.

**Table G.1. Hendrycks et al. (2025) cognitive domain → HCQM location.**

| Hendrycks (2025) domain (weight) | CHC alignment | Approximate HCQM location | Match |
|---|---|---|---|
| General Knowledge (K) — 10% | Gc, Gkn | 1.3 Crystallized Intelligence | Strong (0.75) |
| Reading and Writing Ability (RW) — 10% | Grw | 1.3 Gc (partial) + 7.2 Information Literacy (partial) | Partial (0.5) |
| Mathematical Ability (M) — 10% | Gq, KM, A3, RG | 1.1 IQ (quantitative subcomponent) + 7.3 Computational Thinking (partial) | Partial (0.5) |
| On-the-Spot Reasoning (R) — 10% | Gf | 1.2 Fluid Intelligence; sub-faculties extend to 2.3 Cognitive Flexibility (Adaptation), 2.4 Strategic Planning (Planning), 3.2 SQ (Theory of Mind) | Strong (0.75) |
| Working Memory (WM) — 10% | Gwm | 1.6 Working Memory Capacity | Strong (0.75) |
| Long-Term Memory Storage (MS) — 10% | Gl (Learning Efficiency; encoding aspect of the former Glr) | Partial coverage in 1.3 Gc and 6.1–6.2 (Learning Agility, Knowledge Integration; capacity-layer Gl correspondence); no dedicated storage construct | Partial (0.5) |
| Long-Term Memory Retrieval (MR) — 10% | Gr (Retrieval Fluency; retrieval aspect of the former Glr) | 1.7 Retrieval Fluency; 7.2 Information Literacy (Hallucinations/Retrieval Precision sub-faculty) | Partial (0.5) |
| Visual Processing (V) — 10% | Gv | 1.4 Visual-Spatial Intelligence | Strong (0.75) |
| Auditory Processing (A) — 10% | Ga | Not represented (HCQM scoping; see §6.4) | None (0.0) |
| Speed (S) — 10% | Gs | 1.5 Processing Speed (Hendrycks decomposes into ten sub-faculties; HCQM treats as single construct) | Strong (0.75) |

**HCQM constructs not represented in Hendrycks (2025):**
- **2.1 Metacognitive Intelligence (MQ)** — partial coverage via MR retrieval-precision sub-faculty only; no Schraw-Moshman-style regulation-of-cognition construct
- **2.5 Inhibitory Control** — not represented; Hendrycks has no impulse-suppression or response-inhibition construct
- **3.1 Emotional Intelligence (EQ)** — partial via cognitive empathy under K (Commonsense) only
- **3.3 Cultural Intelligence (CQ)** — partial via Culture sub-faculty of K (cultural knowledge, not cross-cultural competence)
- **3.4 Interpersonal Awareness** — partial via Theory of Mind under R only
- **5.1 Curiosity Quotient** — not represented
- **5.3 Adversity Quotient** — not represented
- **5.4 Grit / Persistence** — not represented
- **6.1 Learning Agility** — partial; learning is distributed across MR, R, and adaptation rather than treated as a standalone domain
- **7.1 Digital Intelligence (DQ)** — not represented; no construct for platform fluency, digital identity, or cyber-risk awareness
- **8.1 Systems Intelligence** — not represented; no causal-systems or feedback-loop construct
- **Domain 4 (Creative & Innovation Intelligence)** — partial via MR Fluency sub-faculties only; no dedicated Creativity Quotient or composite

Six HCQM constructs have **zero** Hendrycks equivalent at any sub-faculty level: **2.5 Inhibitory Control, 5.1 Curiosity Quotient, 5.3 Adversity Quotient, 5.4 Grit / Persistence, 7.1 Digital Intelligence, 8.1 Systems Intelligence**. The other HCQM constructs listed above have at least partial Hendrycks coverage via sub-faculties even though they lack standalone domain status.

**Hendrycks (2025) domains and sub-faculties not represented in HCQM:**
- **Auditory Processing (A)** — phonetic coding, speech recognition, voice quality, rhythmic ability, musical judgment. HCQM scopes auditory out at §6.4.
- **Long-Term Memory Storage (MS) as a standalone domain** — Hendrycks decomposes into Associative Memory, Meaningful Memory, and Verbatim Memory. HCQM has no equivalent decomposition; this is the most actionable candidate for future adoption (already on §6.9 item 4).
- **Long-Term Memory Retrieval (MR) as a standalone domain** — Hendrycks separates Fluency from Hallucinations/Retrieval Precision. HCQM has no separate retrieval construct.
- **Hallucinations/Retrieval Precision as a measurable construct** — Hendrycks weights this at 4% of the aggregate AGI score. HCQM has no equivalent; candidate sub-component for 7.2 Information Literacy in a future version.
- **Visual Generation as a sub-faculty** — Hendrycks treats image/video synthesis as part of Visual Processing. HCQM has no generative or output-side construct.
- **Speed sub-faculty decomposition** — Hendrycks splits Speed into ten distinct sub-faculties (perceptual search, perceptual compare, reading, writing, number facility, simple reaction time, choice reaction time, inspection time, comparison speed, pointer fluency). HCQM treats Processing Speed as a single construct.
- **Reading and Writing as a standalone CHC-Grw domain** — HCQM folds reading and writing into Gc and Digital Intelligence.

**Coverage summary.** Hendrycks (2025) is the most CHC-faithful of the five contemporary frameworks compared in this paper and is therefore the natural anchor for HCQM Domain 1 evaluation in the §6.7 protocol. Its design intent is cognitive-only by construction; the absence of motivational, social-emotional, cultural, digital, and systems-thinking dimensions is a deliberate scope choice, not a defect. HCQM's contribution relative to Hendrycks parallels its contribution relative to CHC (§2.11) and DeepMind 2026 (Appendix D): the non-cognitive top-level domains are HCQM additions to the cognitive-ability surface, not refinements to it. The converse contribution from Hendrycks to HCQM is at the memory-decomposition and hallucination-measurement level, both of which HCQM should consider adopting, in future work, at the sub-component level.

**Joint findings (Hendrycks ∩ DeepMind ∩ Morris).** The "jagged" cognitive profile finding is now triangulated across three independent contemporary AGI-evaluation frameworks: Hendrycks et al. (2025), Burnell et al. (2026), and Morris et al. (2026). This convergence strengthens the broader HCQM position that uniform AGI-progress narratives are not supported by current evidence, and that per-construct cognitive-profile reporting is the appropriate evaluation posture. The CHC-grounded cognitive faculties common to Hendrycks, DeepMind, and CoALA (reasoning, memory, working memory, attention/control, learning, social cognition) are the most empirically mature evaluation targets and are the priority pilot areas for HCQM instrument development (see §6.9).

---

## Appendix H. Comparison with OECD AI Capability Indicators (2025)

The OECD (2025) *Introducing the OECD AI Capability Indicators* organizes AI capability measurement around nine human-grounded ability domains, each scored on a five-level scale. Table H.1 maps each OECD domain to its approximate HCQM location.

**Table H.1. OECD (2025) ability domain → HCQM location.**

| OECD (2025) domain | Approximate HCQM location | Match |
|---|---|---|
| Language | 1.3 Crystallized Intelligence; 3.2 SQ (dialogue) | Strong (0.75) |
| Social interaction | 3.2 Social Intelligence; 3.4 Interpersonal Awareness | Strong (0.75) |
| Problem solving | 1.1–1.2; 2.4 Strategic Planning; 8.2 Strategic Intelligence | Strong (0.75) |
| Creativity | 4.1 Creativity Quotient; 4.2 Divergent Thinking; 4.3 Associative Thinking | Strong (0.75) |
| Metacognition and critical thinking | 2.1 Metacognitive Intelligence; 7.2 Information Literacy | Strong (0.75) |
| Knowledge, learning and memory | 1.3 Gc; 1.6 WM; 6.1 Learning Agility; 6.2 Knowledge Integration | Strong (0.75) |
| Vision | 1.4 Visual-Spatial Intelligence (partial) | Partial (0.5) |
| Manipulation | Not represented (HCQM scoping; see §6.4) | None (0.0) |
| Robotic intelligence | Not represented (HCQM scoping; embodied AI boundary) | None (0.0) |

**HCQM domains not represented in OECD (2025):**
- Domain 2 (Executive / Self-Regulatory): partial coverage via metacognition, but not as a distinct control layer
- Domain 3.1 (Emotional Intelligence): separate from social interaction in HCQM, absent in OECD
- Domain 3.3 (Cultural Intelligence)
- Domain 5 (Motivational & Adaptive Intelligence): Curiosity, Adaptability, Adversity, Grit all absent
- Domain 7 (Digital & Technological Intelligence): covered only indirectly via knowledge
- Domain 8 (Systems & Strategic Intelligence): particularly Systems and Pattern subcomponents

**OECD (2025) domains not represented in HCQM:**
- Manipulation (embodied motor)
- Robotic intelligence (embodied platform-level capability)
- Vision as a top-level domain (HCQM treats visual-spatial as a Domain 1 subcomponent)

**Coverage summary:** The OECD framework includes manipulation and robotic intelligence as first-class abilities. Among the five compared frameworks, only the OECD and the Hernández-Orallo and Vold (2019) catalogue (Tolan et al., 2021; via its sensorimotor-interaction and navigation abilities, §2.11.6) treat the physical-action layer as first-class. This reflects the OECD's policy-facing scope, which must cover physical-AI deployment risks. For embodied-AI use cases, HCQM would need extension at the sensory and motor boundaries (a limitation already flagged in §6.4); the OECD and ADeLe inclusion of these dimensions is a useful comparison point for that future extension.

**Convergence with the other frameworks on the non-cognitive gap.** OECD (2025) does not include motivational, adaptive, cultural, adversity, or systems-strategic dimensions as first-class abilities, consistent with the same gap observed in DeepMind (2026), Hendrycks et al. (2025), CoALA (Sumers et al., 2024), and the Hernández-Orallo and Vold (2019) catalogue (Tolan et al., 2021). The convergence across one industrial-research framework (DeepMind), one academic-research framework (Hendrycks), one engineering-architecture framework (CoALA), one ability-oriented evaluation taxonomy (ADeLe), and one intergovernmental policy framework (OECD) supports the positioning claim that motivational, adaptive, cultural, and adversity capabilities are systematically under-treated in mainstream AI capability frameworks. Whether the omission is a defensible scoping choice across all five cases or an under-recognized capability gap is the open question §6 returns to.

---

## Appendix I. Comparison with the Hernández-Orallo and Vold (2019) Catalogue (Tolan et al., 2021)

Hernández-Orallo and Vold (2019) introduced a catalogue of 14 cognitive abilities for evaluating natural and artificial systems, more fully elaborated and applied to occupational AI exposure by Tolan et al. (2021) and associated with the ADeLe line of ability-oriented AI evaluation. It is the earliest of the five contemporary AI capability frameworks compared in this paper. This appendix reports the full gradient-match analysis summarized in §2.11.6, in parity with Appendices D (DeepMind 2026), E (CoALA), G (Hendrycks 2025), and H (OECD 2025).

**Gradient rubric:** Full (1.0) direct conceptual equivalence; Strong (0.75) significant overlap, minor scope differences; Partial (0.5) meaningful but incomplete overlap; Weak (0.25) tangential contact; None (0.0) no HCQM equivalent.

**Table I.1. Hernández-Orallo and Vold (2019) ability → HCQM location.**

| Catalogue ability | HCQM construct(s) | Match |
|---|---|---|
| MC Metacognition & confidence assessment | 2.1 Metacognitive Intelligence | Strong (0.75) |
| EC Emotion & self-control | 3.1 Emotional Intelligence; 2.5 Inhibitory Control | Strong (0.75) |
| MS Mind-modelling & social interaction | 3.2 Social Intelligence; 3.4 Interpersonal Awareness | Strong (0.75) |
| AS Attention & search | 2.2 Cognitive Control | Strong (0.75) |
| PA Planning & sequential decision-making | 2.4 Strategic Planning; 8.2 Strategic Intelligence | Strong (0.75) |
| CL Conceptualisation, learning & abstraction | 1.2 Fluid Intelligence; 6.1 Learning Agility; 6.3 Transfer Intelligence | Strong (0.75) |
| QL Quantitative & logical reasoning | 1.1 IQ; 1.2 Fluid Intelligence | Strong (0.75) |
| MP Memory processes (long-term + episodic) | 1.7 Retrieval Fluency; 6.1–6.2 Learning; partial 1.3 Crystallized | Strong (0.75) |
| CO Communication | 3.2 Social Intelligence; 3.4 Interpersonal Awareness | Partial (0.5) |
| CE Comprehension & expression | 1.3 Crystallized Intelligence (comprehension); expression/generation is an HCQM gap | Partial (0.5) |
| VP Visual processing | 1.4 Visual-Spatial Intelligence (perception side) | Partial (0.5) |
| SI Sensorimotor interaction | scoped out (§6.4); partial overlap with 1.4 | Weak (0.25) |
| AP Auditory processing | not represented (Ga scoped out, §6.4) | None (0.0) |
| NV Navigation | not represented (scoped out, §6.4) | None (0.0) |

**Coverage summary:** 0 full, 8 strong, 3 partial, 1 weak, 2 none; HCQM covers 12 of 14 abilities at partial-or-better. The two with no HCQM equivalent (Auditory processing, Navigation) and the one weak match (Sensorimotor interaction) fall on the sensory-motor boundary HCQM deliberately scopes out (§6.4), convergent with the perception and manipulation gaps noted for DeepMind (2026) and the OECD (2025).

**HCQM domains not represented in the catalogue:** Domain 4 (Creative & Innovation; creativity is explicitly excluded), Domain 5 (Motivational & Adaptive: curiosity, adaptability, adversity, grit; excluded as conative or personality constructs), Cultural Intelligence (3.3), Digital & Technological Intelligence (Domain 7), and Systems Intelligence (8.1) and Pattern Intelligence (8.3).

**Predecessor note.** The catalogue is the broadest of the five AI frameworks on the affective, social, and metacognitive axis: its EC, MS, and MC abilities included emotion, social cognition, and metacognition as AI-evaluable abilities in 2019, before the later frameworks did. HCQM's differentiation against it therefore does not rest on broadening beyond pure cognition, which the Hernández-Orallo and Vold work already did, but specifically on the motivational, creative, cultural, digital, and systems dimensions, the four-level hierarchical structure, and the architecture-specification form of its dual-use framing. The catalogue used the pre-2018 CHC codes (Gsm, Glr) current at its 2021 writing; HCQM adopts the Schneider and McGrew (2018) revision (Gwm; the Gl/Gr split) and is correspondingly more granular on the memory axis.
