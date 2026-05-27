# Claims Subnet — Pitch Deck v5 Storyline

**Date:** 2026-05-16 *(original v5)* / 2026-05-26 *(post-session update — see "Changes since v5" below)*
**Audience (single deck, three contexts):** (1) Chris Zacharia / Bitstarter, Tuesday next week. (2) Proof of Talk Paris, Bittensor pitch competition, June 2–3, 3–5 minute spoken pitch. (3) Bittensor-aware investors over the summer.
**Goal:** by end of summer 2026, know whether the subnet is real. If yes, build in fall, launch in winter.
**Length:** ~~13~~ **15 slides** post-session. Phone-readable. Print-to-PDF clean.

---

## Changes since v5 (session log, 2026-05-26)

The v5 storyline was the strategic outline for a 13-slide deck. The deck has since evolved to 15 slides through the visual design and build process. This section logs the structural deltas. Slide-by-slide content under the original v5 headings below remains the strategic intent — the visual realization is documented in `PITCH-DECK-v6-VISUAL-SUGGESTIONS-b.md`.

### Slide-count change: 13 → 15

Two new slides added between the original v5 narrative and the technical product slides; one slide deleted; one slide split.

| v5 storyline slide | v6 deck slide | Change |
|---|---|---|
| 1 — Title | 1 — Cover | Cover subtitle reverted to *"The canonical claim-evidence graph for science."* after a brief experiment with *"The Deep Blue for research."* (rejected: worn "X for Y" pattern, weak Deep Blue analogy). |
| 2 — AI ate the internet | 2 — Hero with three tiles ($3T, 300M, 0%) | Split: prize beat (Slide 2) and proof beat (Slide 3) separated. |
| — | 3 — Hallucination chart | NEW (split from old Slide 2). Bar chart showing frontier-model hallucination rates on ScholarQABench. |
| 3 — Purpose | 4 — Our Purpose | Renamed. Thesis text changed from *"We build the substrate that makes the negative space of science computable."* to *"The claim-evidence graph that makes the negative space of science computable."* |
| 4 — Team | 5 — Team | Renamed Sina/Christian/Philipp picture treatment, added Science/Nature logos on Philipp's row. |
| 5 — Meet the Buyer | 6 — Meet Simon | Renamed buyer from "Alex" to "Simon". |
| 6 — Market | 7 — Market | Layout: two-tile composition with Claims-hub connector. |
| 7 — Technical Edge | 8 — Computable confidence | Renamed. Two type-driven lead statements: *"Extraction uncertainty"* + *"Source uncertainty"* with citation references. |
| — | **9 — Inner Loop** *(NEW)* | **Mechanism slide.** Two half-circle arrows form a clockwise miner–validator cycle. Qualifying terms under each role describe what each party does. See "SLIDE 9 — INNER LOOP" section below for the strategic narrative. |
| — | **10 — Incentive Mechanism** *(NEW)* | **Reward function slide.** LaTeX-rendered (KaTeX) `R_m` equation from whitepaper §7 on the left; variable legend on the right. See "SLIDE 10 — INCENTIVE MECHANISM" section below. |
| 8 — Solution | 11 — The Product | Reframed. Was a single ClaimRecord example next to a pipeline diagram; now a bowtie/hourglass architecture diagram showing many miners → one canonical DB → many ontologies → one specific answer for Simon. The Palantir-Foundry framing now lives inside the bowtie's top eyebrow. |
| 9 — Why Bittensor | 12 — Why Bittensor | Minor refinements to the three rows (Sharper signal / Capital efficiency / Open competition). Bottom strip text retained. |
| 10 — Business Model + Moat | 13 — Business Model + Moat | Redesigned with symmetric grey-shaded three-tier blocks on the left (revenue tiers) and matching three-tier moat blocks on the right (claim graph / ontologies / network effects). |
| 11 — Traction + Flywheel | — | **DELETED.** No real traction yet; the flywheel diagram added more confusion than clarity and was redundant with the inner loop. |
| 12 — Roadmap | 14 — Roadmap | Phase gates restructured: "First paid R&D pilot" (Q3 26) / "Subnet launch" (Q4 26) / "Platform" (2027+). Cleaned up gate language ("API + MCP integrations" instead of "External API + MCP integrations"). |
| 13 — Close | 15 — Close | Redesigned. Removed *"Let's talk."* headline. Added a transparent quote card in the upper-left: *"Frankly, we're skeptical that 42 is the answer. Claims will know."* Contact block remains in the lower-left. |

### Visual / mechanical changes that touched every slide

- **Citation system codified** (Nature numbered-superscript style; full reference format with italicized journal name; en-dash range form `¹⁻⁴` for three+ consecutive references). Asterisk markers deprecated.
- **PDF print pipeline fixed.** Print CSS now uses `@page size: 1920px 1080px` (matching the native stage size) so the PDF renders pixel-for-pixel identical to the browser. Previous A4-landscape print broke many slides.
- **Mobile portrait rendering fixed.** CSS-based `@media (orientation: portrait)` rule rotates `.stage-wrap` so the deck fills mobile screens. JS scaling kept separate.
- **KaTeX dependency added** (CDN, with SRI hashes) for Slide 10's reward function. This is the first slide to require math rendering.

---

## What changed from v4

- **Slide 6 (Market):** AI training data anchor rebuilt on three named primary sources (Labelbox CEO Manu Sharma on Cognitive Revolution podcast; Sacra revenue estimates for Surge AI and Scale AI; TechCrunch on Mercor's $75M→$500M ARR in 8 months).
- **Slide 7 (Structural Problem):** Completely rewritten. Rows 1 and 3 in v4 repeated Slide 2; deleted. New slide focuses on the *technical depth* — the statistics analogy (point estimates without confidence intervals are dangerous), AI's probabilistic nature, the flawed-corpus reality, gold-data anchoring, and customer-specific ontologies as the differentiating moat layer.
- **Slide 8 (Solution):** SGLT2 example verified against PubMed. According to PubMed, Hanlon et al. 2025 JAMA network meta-analysis (n = 309,503, [DOI: 10.1001/jama.2024.27402](https://doi.org/10.1001/jama.2024.27402)) and Li et al. 2018 (reported HbA1c reduction of −0.71% in SGLT2+DPP-4 combination therapy, [DOI: 10.1111/dom.13294](https://doi.org/10.1111/dom.13294)) anchor the effect-size claim. ClaimRecord updated with real DOI.
- **Slide 9 (Why Bittensor):** Three reasons rewritten per battle-test (details inline). Reason 1 reframed around uncertainty calibration; Reason 2 renamed to "Capital efficiency" with Ridges/Chutes precedent; Reason 3 reframed as "open competition compounds quality."
- **Slide 10 (Business Model + Moat):** Visual elements added — revenue funnel + moat stack diagrams replace the bullet-list text walls.
- **Slide 11 (Traction + Flywheel):** Flywheel battle-tested. The 4-node loop in v4 is correct but incomplete — replaced with a two-interlocking-loops diagram (supply-side automatic loop + demand-side deliberate loop) meeting at the canonical graph.
- **Critical review section added at the end** — ten weaknesses investors will probe and how to address each.

---

## SLIDE 1 — TITLE: Claims

**Core message:** Serious infrastructure. Credible team. Memorable identity in three words.

**Content:**
- Big, bold, central title (**Claims**)
- One-line descriptor underneath: **The canonical claim-evidence graph for science.**
- Sub-tag (small, mono): A Bittensor subnet. By the team that built SciWeave.

**Visual approach:** Black background, single accent color. Empty slide except the title, descriptor, and sub-tag. The first impression should communicate the restraint and seriousness of science — the opposite of the typical Web3 deck.

**Depth available in Q&A:** "Canonical claim-evidence graph" — every claim sourced, every effect weighted, contradictions preserved, programmable through an API/MCP layer. Decision-grade, not summary-grade.

---

## SLIDE 2 — AI ate the internet. Science is what it can't digest.

**Core message:** Scale of the locked-up prize, paired with proof the team has already moved the needle on the benchmark that matters. Two-part hook.

**Content — two zones on one slide:**

**Top zone — the prize (scale, large monospace, stacked):**

> **$3T spent on R&D annually.**
> **300M+ scientific publications.**
> **1T+ words.**
> **Zero of it structured as machine-readable data.**

**Bottom zone — the proof (benchmark comparison, vertical stack):**

> **Hallucinated references on ScholarQABench — biomedical and neuroscience queries**
>
> Claude Opus 4.6 — **62%**
> GPT-5.2 — **59%**
> **SciWeave — 0%**

**Mid-line, smaller, italic — the connective tissue:**

*Frontier models are not grounded in science. RAG systems like SciWeave eliminate hallucinated references, but they can only parrot what authors said.*

Source attribution, small monospace at the bottom:
*World Intellectual Property Organization (WIPO), 2025. ScholarQA Benchmark: Asai et al., Nature 2026.*

**Visual approach:** Two-zone slide divided by a thin horizontal rule. Top zone in large JetBrains Mono. Four lines, each a single fact, stacked. Bottom zone is the hallucination comparison: Claude and GPT-5.2 rows in muted rust, SciWeave row in the accent color, slightly larger and bolder. Mid-line descriptor is small body type, almost a whisper, sitting on the dividing rule.

---

## SLIDE 3 — PURPOSE

**Core message:** What we exist to build, in language a non-technical investor can repeat.

**Content (centered, large):**

> **Scientific AI needs structure, not just scale.**
>
> **We are building the substrate that makes the negative space of science computable (gaps, contradictions, missing links).**

**Visual approach:** Pure typography. Two sentences, stacked, generous breathing room. Nothing else on the slide.

**Depth available in Q&A:** The "structure, not just scale" line is the load-bearing claim — defend it with: (a) the SciWeave/ScholarQABench result on Slide 2 already shows what well-engineered RAG does to hallucinations, so the next bottleneck is structure not size; (b) Asai et al. and the broader retrieval-augmentation literature both point to grounding and structure as the next reliability dimension; (c) compute-scaling alone keeps producing more confident but not more verifiable outputs.

---

## SLIDE 4 — TEAM

**Core message:** Three founders with the specific credentials this build requires.

**Content — three columns, portrait headshot on top, role, headline, logos:**

**Dr. Philipp Koellinger** — CEO DeSci Labs (SciWeave). Professor of Economics & Statistical Genetics. Headline: Led 300+ top scientists in consortia he founded. Key role in fixing the replication crisis in behavioral genetics.
Logos: DeSci Labs, Vrije Universiteit Amsterdam, UW Madison, Science, Nature.

**Sina Iman** — CTO DeSci Labs (SciWeave). Headline: Computer Scientist. ML, blockchain, and cryptography. One of Palantir's early employees.
Logos: DeSci Labs, Palantir, BoozAllen, NSA.

**Dr. Christian Roessler** — Professor of Economics. Headline: Game theory and mechanism design. Director, Smith Center for Private Enterprise Studies.
Logos: University of Melbourne, Brown, Rice, University of Vienna, California State University.

**Visual approach:** Three columns, equal weight. Name + portrait on top + function + headline + logos for credentials. The logos carry the credibility signal.

**Depth available in Q&A:** Specific Koellinger publications (educational-attainment GWAS, cognitive-performance GWAS, the entrepreneurship-genomics line of work), DeSci Labs founding history, SciWeave product trajectory. Sina's Palantir / defense-tech shipping record. Christian's prior mechanism-design work.

---

## SLIDE 5 — MEET THE BUYER

**Core message:** Real buyer, real pain — visualized. One concrete query, asked of two systems, side by side. The audience judges the outputs directly. No bullet list explaining what we do; the demonstration does the work.

**Layout — three zones, top to bottom:**

---

**TOP STRIP — buyer context, one sentence (small, monospace, almost a footnote):**

*A well-funded drug-discovery startup. Thousands of papers per compound class. An FDA-bound decision. Using SciWeave for first-pass exploration — they need a substrate.*

---

**MIDDLE — the question both systems answer (centered, large, italic):**

> *"Does this SGLT2 inhibitor class reduce HbA1c in adults ≥65 with renal impairment?"*

---

**BOTTOM — two-pane comparison, side by side, the visual centerpiece of the slide:**

**Left pane** — muted rust, labeled `TODAY: RAG OUTPUT`, document icon:

```
"SGLT2 inhibitors reduce HbA1c in type 2
diabetes. Effects vary in elderly and renal-
impaired populations. Several studies report
attenuation at lower eGFR. Caution advised."

  — 12 papers summarized
```

*Caption directly below:* **Useful for a lit review. Not enough to commit a budget.**

**Right pane** — accent color, labeled `WITH CLAIMS GRAPH`, structured-data icon:

```
Claim: SGLT2i reduces HbA1c in T2D
  → Effect: significant; n = 309,503 (Hanlon 2025)
  → Age: AR −0.24% per 30-yr increment ↓
  → Renal subgroup: ⚠ heterogeneous
       • 3 RCTs support
       • 2 RCTs show attenuation at eGFR <45
  → Confidence: high (RCT consensus)
  → Negative space: no RCT in ≥75 + eGFR <30
  → Contradictions: [2 linked claims]
```

*Caption directly below:* **Programmable. Auditable. Decision-grade.**

---

**BOTTOM STRIP (accent color):** *RAG drafts a first lit review. The graph steers a multi-million-dollar R&D pipeline.*

---

**Visual approach:** Three vertical zones with strong typographic hierarchy. Top strip in small monospace, almost a footnote — the buyer context registers without competing with the centerpiece. Middle question centered, large, italic, in the accent color — it frames the two panes that answer it. Bottom occupies ~two-thirds of the slide: two panes side by side, equal width, with strong color separation (left pane muted rust on a slightly darker card; right pane accent color on a card that visually dominates). Each pane has a header chip (`TODAY: RAG OUTPUT` / `WITH CLAIMS GRAPH`), the example output in monospace, and a one-line caption directly below. Final accent-color strip across the bottom carries the closing line.

**Why this works:** the audience does not need a bullet list explaining what we do. They see the same question asked of two systems and judge the outputs. The RAG pane is plausible-sounding paragraph prose — exactly what RAG returns in production, and exactly what is *not enough* to commit a real R&D decision against. The Claims pane shows structured fields the audience cannot fake their way through: a real effect size with N, an age-attenuation caveat, a heterogeneous renal subgroup decomposition, an explicit confidence rating, and — the line that does the most work — a *negative space* entry naming a gap in the literature ("no RCT in ≥75 + eGFR <30"). That last line is the operational definition of decision-grade evidence that no RAG output can produce, and the audience sees it directly.

**Depth available in Q&A:**
- The structured output anchors on Hanlon et al. 2025 JAMA ([DOI: 10.1001/jama.2024.27402](https://doi.org/10.1001/jama.2024.27402)) — verifiable; the age-attenuation finding (AR 0.24% per 30-yr increment) is in the paper, not invented for the slide.
- The renal-subgroup decomposition is the kind of structured evidence work that drives real go/no-go decisions in drug-discovery workflows; replace with a more accurate decomposition once the pilot's specific compound class is finalized.
- Customer-specific ontology layer (the buyer's specific compound class modeled as an entity type, their internal validation screens layered on top) is covered on Slide 7.
- Why not name the buyer? Pilot is in motion; no signed contract. Anonymized in the deck; named once an LOI is signed.

---

## SLIDE 6 — MARKET

**Core message:** Two large, growing, independently-validated demand pools converge on the same product. Both anchors cite named primary sources.

**Content — two anchored TAM estimates:**

**Anchor 1 — Global R&D intelligence and evidence work.**
Global R&D spend is approximately 2% of GDP — **$3T annually** ([WIPO 2025](https://www.wipo.int/en/web/global-innovation-index/w/blogs/2025/end-of-year-edition)). Pharma alone runs ~$250B in R&D. Intelligence, lit-review, and evidence-synthesis work is conservatively 2–5% of R&D budgets in evidence-intensive sectors (pharma, biotech, defense, semiconductor research, regulated industries).
**Conservative TAM line: $20–50B annually. Growing ~5%/yr in OECD countries.**

**Anchor 2 — AI training data for scientific & frontier models.**
Frontier AI labs have exhausted clean general web text; the next constraint is high-quality structured domain data. **Aggregate Western frontier-lab spend on training data: ~$5–9B annually in 2025, growing ~2× year over year.** Triangulated from three primary sources:

- **Labelbox CEO Manu Sharma** (on the [Cognitive Revolution podcast, July 2025](https://www.cognitiverevolution.ai/the-data-factory-inside-the-100b-race-for-post-training-supremacy-with-labelbox-ceo-manu-sharma/)): *"each of the frontier labs is probably spending over $1,000,000,000 a year on data."* With 5–7 frontier Western labs, this implies $5–7B+ in direct lab spend on data alone.
- **Sacra revenue estimates** for two vendors who serve frontier labs: Surge AI hit **~$1.2B annualized revenue in 2024** with ~12 frontier-lab customers ([Sacra Surge AI profile](https://sacra.com/c/surge-ai/)); Scale AI revenue grew from $870M to $2B over the same period ([Sacra Scale AI profile](https://sacra.com/c/scale-ai/)). Two vendors alone clear $2.5–4B in 2025 revenue.
- **Mercor's reported trajectory:** $75M ARR (Feb 2025) → $500M ARR (Oct 2025), a 6.7× run in 8 months, confirmed by named institutional investors at a $10B valuation ([TechCrunch, October 2025](https://techcrunch.com/2025/10/27/mercor-quintuples-valuation-to-10b-with-350m-series-c/)).

**Emerging TAM line: $5–9B annually in 2025, ~2× YoY growth.** *Scientific claim-level evidence is among the highest-value categories in this market — verifiable, domain-specialized, expensive to produce manually.*

Bottom strip: *Two demand pools. One product.*

**Visual approach:** Two horizontal bars indicating TAM ranges, with Claims as the convergence point at the right edge. Sources in small monospace beneath each bar, hyperlinked in the PDF.

**Depth available in Q&A:**
- **Honest confidence assessment.** The R&D-intel line is moderate confidence at the $20–50B range; the AI-training-data line is moderate confidence at $5–9B in 2025 specifically. The 2× YoY growth rate is moderate-high confidence for 2024→2025 and lower confidence beyond, as synthetic data and market maturation eat some growth.
- **Bottom-up R&D math.** If 1% of pharma R&D-intel budgets buys a Claims API at $50K/year, that is $125M ARR; <10% gets to unicorn revenue at SaaS multiples.
- **What I cannot defend.** The widely-cited "Time Magazine: $1B per frontier lab" figure circulates secondhand; the Labelbox CEO statement at primary venue is the verifiable substitute. Packaged market-research reports (Grand View, Fortune Business Insights, MarketsandMarkets) disagree by 2–3× and have opaque methodology — useful only for directional ~20–30% CAGR consensus, not for absolute numbers.

---

## SLIDE 7 — THE TECHNICAL EDGE: UNCERTAINTY, MADE COMPUTABLE

**Core message:** Two technical claims that together describe what we actually do and what nobody else does. (1) Scientific knowledge requires *calibrated uncertainty*, not point estimates — for both the AI extraction layer and the underlying corpus. (2) Customer-specific ontologies on top of the substrate are the differentiating moat.

**Content — two zones, top half is the technical depth, bottom half is the moat layer:**

---

**TOP ZONE — Why surfacing uncertainty is the missing layer.**

**The statistics analogy.** A point estimate without a confidence interval is dangerous. The same is true for scientific claims: knowing *what* a paper says is not enough; you need to know *how robust* that finding is, where it has been replicated or contradicted, and how the underlying methods affect confidence. Today, RAG tools return summaries — point estimates with no variance. The substrate is missing the confidence interval.

**Two sources of uncertainty in scientific knowledge, both must be measured:**

- **Extraction uncertainty.** AI extraction is probabilistic — outputs vary by model, prompt, and run. Without measuring this variance, every extracted claim is a point estimate dressed up as a fact.
- **Source uncertainty.** ~50% of published findings do not replicate (Ioannidis 2005; Open Science Collaboration 2015; Prinz et al. 2011; Baker 2016). The corpus itself is noisy — even a perfectly-extracted claim can be from a paper that won't survive replication.

**How the substrate surfaces both:** many independent extractor runs against the same source (variance over extractors → calibrated confidence), anchored on gold-standard datasets curated by domain experts (anchor against ground truth → calibrated bias). The result: every claim ships with a confidence interval that reflects both AI uncertainty and source uncertainty. *That is the statistical artifact nobody else in this space produces.*

---

**BOTTOM ZONE — Customer-specific ontologies are where the moat lives.**

On top of the structured graph, each enterprise customer co-develops their own ontology — the entities, relationships, methods, and validation screens specific to their R&D problem. What this enables:

- **Domain-native queries.** "Which compounds in our target class have shown adverse cardiac signatures in trials over n = 500?" — not "summarize the SGLT2 literature."
- **Domain-specific validation screens.** Catches the failure modes the customer cares about (e.g. drug-class-specific replication failures, regulatory-relevant trial-design flaws).
- **Substrate enrichment across customers.** Each ontology extends the canonical schema; future customers in adjacent domains start from a richer base.

**The moat.** Switching costs are high (each ontology represents months of co-development with the customer's scientific team — non-transferable, off-chain). A data-network effect compounds over time: every new ontology engagement enriches the substrate for future customers in adjacent domains. *This is the layer Palantir's Foundry built its commercial moat on — the ontology is the technical artifact; the moat is the deep co-development around it.*

**Bottom strip:** *Calibrated uncertainty + customer ontologies = the data nobody else can produce.*

**Visual approach:** Two-zone slide, thin horizontal divider between. Top zone has the statistics-analogy framing followed by the two-source-of-uncertainty block (left/right or stacked). Bottom zone has the three ontology enables as a tight list, then the moat closing line. Less text than v4 Slide 7; more conceptual weight.

**Depth available in Q&A:**
- **On the Palantir-ontology analogy specifically (not "Palantir for Science" as a whole company analogy):** Palantir Foundry's commercial moat is built on customer-specific ontologies + forward-deployed engineering + deep integration. The *ontology* portion of that moat is precisely what we are building. We are not claiming to replicate Palantir's full stack (we don't do FDEs at the same scale, we don't carry the defense brand). We are claiming the ontology layer behaves the same way — high switching cost, non-transferable, schema-enriching across deployments.
- **On "data network effects" vs. classical network effects.** These are not Metcalfe's-law network effects (more users → quadratically more value). They are *data network effects* — each customer ontology improves the substrate for future customers in adjacent domains. Honest framing: closer to switching-cost moat + cumulative-improvement moat than to a viral network effect.
- **On gold-data curation as the proprietary layer.** This is the off-chain part of the validator/owner role. Domain experts curate calibration datasets; validators use them to score miners. The methodology and the gold sets are the company's IP, not the subnet's.

---

## SLIDE 9 — INNER LOOP (new, added during 2026-05-26 session)

**Strategic position in the deck:** Sits between Slide 8 (Computable Confidence — *what the system produces*: calibrated uncertainty on every claim) and Slide 10 (Incentive Mechanism — *how the work is paid for*). The Inner Loop slide answers the implicit follow-on question after Slide 8: "you say you produce calibrated uncertainty by running many extractors and validating against gold data — *how does that actually work as a two-party system?*"

**Core message:** The subnet is a continuous two-party cycle. Miners produce; validators check; the loop turns; each pass tightens calibration.

**Content:** A clockwise rotation diagram. *Miners* sits at the 9 o'clock position, *Validators* at the 3 o'clock position. Two half-circle arrows form a clockwise loop between them. Under each role label, four qualifying terms describe what that party does in the cycle:

- **Miners**: Source / Claim-evidence / Concept binding / Judgment
- **Validators**: Assign / Verify / Gold set / Calibrate

The four terms map directly to the four whitepaper channels (A/B/C/D), foreshadowing the channel-based reward function on Slide 10.

**Why the loop matters narratively:** Investors trained on Web3 are used to "decentralized" being a vibe. The Inner Loop slide is the operational answer. Two roles, eight verbs, one cycle. The reward function on Slide 10 then formalizes the loop as a mathematical object — but the loop has to be intuitive before the math lands.

**Depth available in Q&A:**
- Each verb maps to one full whitepaper channel section (§5.1–§5.4). "Source" is whitepaper Channel A (source integrity and coverage). "Claim-evidence" is Channel B (atomic extraction). "Concept binding" is Channel C (claim graph construction). "Judgment" is Channel D (evidence judgment and prediction). On the validator side, the four terms are operational: assigning extraction tasks to miners, verifying their work, maintaining the curated gold-data corpus, and calibrating the scoring function that translates miner output into reward.
- The loop turns continuously — each pass tightens the calibration. That tightening produces the confidence intervals advertised on Slide 8.

---

## SLIDE 10 — INCENTIVE MECHANISM (new, added during 2026-05-26 session)

**Strategic position in the deck:** Comes immediately after the Inner Loop diagram and immediately before the Product / Bowtie architecture. It is the mathematical formalization of the loop. The slide buys technical credibility with Bittensor-aware investors who have seen many subnet pitches and want to see the reward function before they take the rest of the deck seriously.

**Core message:** The reward function is not hand-wavy. It pays miners channel-by-channel, with recursive upstream gates so fabrication zeros out downstream credit.

**Content — two-pane layout:**

**Left pane — the reward function (whitepaper §7, verbatim):**

```
R_m =  λ_A · S_A
     + λ_B · G_A · S_B
     + λ_C · G_A · G_B · S_C
     + λ_D · G_A · G_B · G_C · S_D
     − P_spam − P_collusion − P_reset.
```

Rendered in true math typography via KaTeX (the deck's first math dependency).

**Right pane — variable legend:**

| Symbol | Definition |
|---|---|
| `R_m` | Reward for miner `m` (the LHS of the equation) |
| `A` | Source integrity and coverage |
| `B` | Atomic extraction |
| `C` | Claim graph construction |
| `D` | Evidence judgment and prediction |
| `λ` | Task weight (whitepaper terminology: "score intensity") |
| `G` | Gate weight (whitepaper terminology: "dependency gate") |
| `S` | Task score |

**Why the recursive gate structure is the load-bearing detail:** Channel B's payment is multiplied by `G_A`. Channel C's by `G_A · G_B`. Channel D's by `G_A · G_B · G_C`. A miner who fabricates source anchors fails Channel A's gate, which zeros out every downstream term. This is what gives the mechanism fabrication-resistance by construction, not by hoping validators catch every cheat. Sophisticated investors will spot this; less sophisticated ones will trust that the equation looks real. Either way, the slide pays for itself.

**Penalty terms** (`P_spam`, `P_collusion`, `P_reset`) are subtractive — the standard Bittensor abuse vectors are explicitly priced into the reward.

**Depth available in Q&A:**
- Launch parameter values (from whitepaper §10.2.1): channel allocation vector `q^launch = (0.35, 0.35, 0.20, 0.10)` (front-loaded toward source integrity and atomic extraction); score intensities `λ = (0.95, 0.95, 0.90, 0.85)`; baselines `φ = (0.05, 0.05, 0.10, 0.15)`.
- Why "evidence-substrate-first": at launch the subnet over-weights the lower-level extraction work (Channels A + B) so the substrate cleans up before high-level synthesis (Channels C + D) is rewarded heavily. As reliability thresholds are met, the mature allocation shifts toward C and D.
- Gates are typically *soft* for ordinary errors and *hard* for fabrication. Modest coverage defects discount downstream credit smoothly; fabricated source anchors zero downstream credit completely. This is the deliberate asymmetry — small mistakes degrade payout, fraud collapses it.

**Terminology note for the slide vs. the whitepaper:** "Task weight" and "Gate weight" on the slide are pitch-readable substitutes for the whitepaper's more precise "score intensity" and "dependency gate". In Q&A with a Bittensor mechanism designer, use the whitepaper terms — they're not weights in the fixed-coefficient sense (especially G, which is data-dependent and ranges 0–1 at runtime).

---

## SLIDE 8 — THE SOLUTION (verified example)

**Core message:** Here is what we produce. Concrete, structured, programmable. The thing that does not exist yet and is required for the next phase of AI for science.

**Content — two-pane layout:**

**Left pane — the pipeline:**
`Papers → Claims + Evidence → API / MCP → R&D teams · Regulators · AI agents · Researchers`
The middle node ("Claims + Evidence") is the product, visually emphasized.

**Right pane — one ClaimRecord, shown in full (anchor citation now verified):**

```
ClaimRecord
───────────
"SGLT2 inhibitors reduced HbA1c versus placebo in adults
 with type 2 diabetes."

Evidence type   Network meta-analysis (592 RCTs)
Effect / N      Significant HbA1c reduction; n = 309,503
Anchor source   Hanlon et al., JAMA 333(12), 1062–1073 (2025)
DOI             10.1001/jama.2024.27402
Confidence      ● High
Entities        SGLT2i, HbA1c, T2D
Relations       reduces → measured_by
Contradicts     [null]
Replications    Effect smaller in older adults
                (AR 0.24% per 30-yr increment)
```

Bottom strip: *Every claim sourced. Every effect weighted. Disagreement preserved. Programmable.*

**Visual approach:** Keep the pipeline diagram and claim card from v4. Middle pipeline node brighter and larger than the others. Claim card on the right is the proof that the product is real. The age-interaction "replications" line is included specifically because it surfaces a *quantitative caveat* — exactly the kind of structure RAG cannot produce.

**Depth available in Q&A:**
- According to PubMed, the Hanlon et al. 2025 JAMA paper ([DOI: 10.1001/jama.2024.27402](https://doi.org/10.1001/jama.2024.27402)) is a network meta-analysis of 592 trials covering 309,503 participants, finding SGLT2 inhibitors significantly reduce HbA1c with an absolute reduction that diminishes by ~0.24% per 30-year increment in age. The Li et al. 2018 paper ([DOI: 10.1111/dom.13294](https://doi.org/10.1111/dom.13294)) reports a specific HbA1c reduction of −0.71% for SGLT2+DPP-4 combination therapy in T2DM.
- A second ClaimRecord example from a non-biomedical domain (materials science, climate, semiconductors) can be shown to demonstrate the architecture generalizes.

---

## SLIDE 9 — WHY BITTENSOR 

**Core message:** The economics, the quality dynamics, and the adaptability all converge on a decentralized architecture. A centralized incumbent cannot match this on the dimension that matters — data quality.

**Content — three reasons, each one-line headline plus body. All three reframed per battle-test:**

---

**1. Sharper signal with extractor diversity.**

Claim extraction is probabilistic — one model run produces a point estimate; consensus across many independent miners produces both a sharper signal *and* a calibrated confidence interval. A single-team pipeline collapses extraction to one model's view. A subnet runs a market for pipelines, where variance across extractors is itself signal. **The deeper the subnet, the more precise the uncertainty estimate per claim.**

---

**2. Capital efficiency.**

A Bittensor subnet delivers a state-of-the-art digital commodity at a fraction of the investor capital a centralized company would require. Miners bear their own compute costs and are paid in the subnet's token — supply-side spend tracks demand-side value, not headcount. **Ridges and Chutes are precedent: real production-grade outputs running at unit costs centralized competitors cannot match.** Token-funded distributed labor is structurally more capital-efficient than payroll-funded extraction at scale.

---

**3. Open competition compounds quality.**

Miners and validators compete in the open, continuously. As new AI models are released, miners adopt them because their rewards depend on quality. As coverage gaps appear, miners chase them because rewards depend on coverage. A centralized team has to plan, fund, and execute every improvement cycle. We do not — the incentive structure runs the improvement cycle continuously, in public. **Bittensor turns competition into the engine of data quality.**

Bottom strip: *Data quality is the only thing that matters in this business. Bittensor is the architecture where it compounds.*

**Visual approach:** Three vertical panels, each with a one-line bold headline and a 2–3 sentence body. No icons. Bottom strip in the accent color. This slide should feel like a fist.

**Depth available in Q&A:**
- **"Why won't Google / OpenAI / Elsevier just do this?"** Three layers:
  (a) the extractor-diversity argument above — diverse extractor consensus structurally beats single-vendor extraction *and* gives calibrated uncertainty no single-model run can;
  (b) the capital-efficiency argument — incumbents cannot match token-funded distributed labor without diluting their own equity to a large contributor base;
  (c) a secondary trust argument: for high-stakes R&D customers (defense, sensitive pharma pipelines, regulatory dossiers), an open multi-party substrate is more defensible than depending on a single vendor that also competes in the customer's downstream market. This is not a universal moat — pharma buys from competitors all the time — but it is a defensible advantage in specific buyer segments.
- **The honest counter to be ready for:** compute cost is *not* the reason. Open-source LLMs extract a paper for cents; the full literature is single-digit millions at hyperscaler rates. We do not lean on compute scarcity. We lean on quality dynamics, capital efficiency, and continuous open competition. A sophisticated audience will catch any cost-scarcity claim.

---

## SLIDE 10 — BUSINESS MODEL + MOAT (visual)

**Core message:** Two revenue lines that scale independently. A moat that hardens with scale. Visual, not text wall.

**Content — two diagrams, not bullet lists:**

---

**Left pane — Revenue funnel (three horizontal bands, widest at top):**

```
┌──────────────────────────────────────────────┐
│  FREE TIER                                   │  ← researchers, students, public-interest
│  High-latency, low-volume                    │     low revenue per user, high volume
│                                              │
└──────────────────────────────────────────────┘
   ┌──────────────────────────────────────┐
   │  METERED API / MCP                   │  ← R&D teams, scientific AI builders
   │  Low-latency, per-call billing       │     standard SaaS unit economics, >80% margin
   └──────────────────────────────────────┘
      ┌────────────────────────────────┐
      │  ENTERPRISE                    │  ← pharma, biotech, defense R&D
      │  Custom ontology + validation  │     six-to-seven-figure ACV, services-anchored
      │                                │
      └────────────────────────────────┘
```

Funnel narrative: the free tier feeds discovery; metered API is the self-serve commercial layer; enterprise integrations are the high-ACV retention layer.

---

**Right pane — Moat stack (three horizontal layers, bottom to top):**

```
┌──────────────────────────────────────────────┐
│ LAYER 3: CUSTOMER-SPECIFIC ONTOLOGIES        │  switching cost + data-network effect
│                                              │  (Palantir Foundry pattern)
├──────────────────────────────────────────────┤
│ LAYER 2: CAPITAL EFFICIENCY                  │  token-funded supply, structurally
│                                              │  un-replicable by payroll competitors
├──────────────────────────────────────────────┤
│ LAYER 1: QUALITY-COMPOUNDING SUBSTRATE       │  diverse extractors + gold-data
│                                              │  validation; hard to replicate
└──────────────────────────────────────────────┘
```

Bottom strip: *Layers 1 and 2 compound automatically. Layer 3 is built one enterprise at a time.*

**Visual approach:** Two clean schematic diagrams replace v4's bullet lists. Revenue funnel on the left, moat stack on the right. Each layer labeled with one descriptor on the right. No paragraph text on the slide itself — the diagrams carry it.

**Depth available in Q&A:** Gross margin assumptions on API revenue (>80%, infrastructure cost only). Enterprise pricing precedent in pharma intel / defense R&D ($1–5M ACV typical). Token economics — buyback-and-burn at ~20% of gross revenue, fixed-supply alpha, emission curve and treasury policy in the data room, not on the slide.

---

## SLIDE 11 — TRACTION + FLYWHEEL (battle-tested)

**Core message:** Consumer wedge is live and benchmark-leading. First R&D pilot is in motion. The flywheel is not one loop but two — supply-side automatic and demand-side deliberate — meeting at the canonical graph.

**Content — left/right split:**

**Left — Live today:**
- **SciWeave** — Live MCP server (sciweave.com/web/mcp), web app, iOS, Android. 0% hallucinated references on ScholarQABench biomedical and neuroscience queries (vs. 62% Claude Opus 4.6, 59% GPT-5.2). Grounded in 300M+ scientific works via OpenAlex.
- **Infrastructure relationships.** OpenAlex, CrossRef, ORCID — the three core providers of academic infrastructure.
- **First R&D pilot in motion.** A privately-held drug-discovery startup building an FDA-relevant decision workflow on top of structured evidence. Prototype in active development; first prototype demo to their leadership pending.
- **Additional pipeline.** Two further enterprise prospects (biotech and defense R&D) gated on the first pilot's performance.

**Right — Two-loop flywheel diagram (interlocking circles):**

**Supply loop (left, automatic):**
miners → extractor diversity → calibrated quality → token value → miner rewards → more miners

**Demand loop (right, deliberate):**
enterprise customers → customer ontologies → richer substrate → more customer use cases → more enterprise demand

**Meeting point:** the canonical claim-evidence graph. Both loops feed it; it feeds both.

**Visual approach:** Left pane is a tight four-line list of what's live. Right pane is two interlocking circles meeting at a central node labeled "Canonical claim-evidence graph." Each circle has 3–4 arrowed nodes. Left circle: supply-side. Right circle: demand-side. Color-coded.

---

## SLIDE 12 — ROADMAP

**Core message:** A sequenced bet with clear go/no-go inflection points.

**Content — three phases on a horizontal timeline:**

**Phase 1 — Centralized prototype (now → fall 2026).**
Build the customer-facing solution in-house. Land the first paid R&D pilot. Prove the extraction + validation pipeline beats internal manual workflows on a head-to-head benchmark. Use SciWeave as the consumer distribution channel.
*Go/no-go criterion:* signed pilot contract + prototype beats client's internal baseline.

**Phase 2 — Subnet launch (winter 2026).**
Register the Claims subnet on Bittensor. Migrate the extraction layer to miners. Operate the proprietary validation layer through the company's validator. Open-source the miner reference implementation. Onboard the first wave of independent miners.
*Go/no-go criterion:* 50+ miners onboarded, 1M+ structured claims in the canonical graph, first external API integration.

**Phase 3 — Platform (2027+).**
Scale the canonical graph across domains beyond biomedicine. Add enterprise customers on customer-specific ontologies. Open the API to scientific AI builders. Engage buyback-and-burn.
*Go/no-go criterion:* revenue and customer milestones in the financial model.

**Visual approach:** Horizontal timeline with three phases as columns. One headline + two supporting lines per phase. Accent color on Phase 2 (the inflection point).

---

## SLIDE 13 — CLOSE

**Core message:** The substrate belongs on Bittensor. We are the team to build it. Help us launch.

**Content (very short slide):**

Top, smaller:
*Scientific AI needs structure, not just scale.*

Middle, large:
**A canonical claim-evidence graph for science is missing.**
**A Bittensor subnet is the architecture that can produce it.**
**We are the team that should run it.**

Bottom, small mono:
`philipp@desci.com`

**Visual approach:** Title-slide aesthetic. Mostly empty. The three middle lines stack as a single thought. Contact in the bottom corner.

---

## CRITICAL REVIEW — What investors will probe, and how to address each

A sharp pre-mortem on the v5 deck. Ten weaknesses in descending order of importance.

### 1. The mechanism design is unproven (HIGH RISK)

**The probe:** "Most Bittensor subnets fail because the mechanism design doesn't produce honest miner behavior. Yours isn't tested. Why won't this go the same way?"

**The honest answer:** mechanism design takes months and most subnets don't fully solve it. Christian's specific innovations (interpretive-question testing, adversarial-claim testing, gold-data calibration) are reasoned but not validated.

**Mitigation:** Lean on Phase 1 as the de-risking step. The product works centralized first; the subnet is added when it can demonstrably improve quality, not as a binary launch dependency. Frame the mechanism work as "we will not migrate until the centralized baseline is beaten." This converts the risk from existential to comparative.

### 2. The "first paid pilot" is not signed (HIGH RISK)

**The probe:** "'In motion' is fundraising language for 'nothing yet.' What is the actual probability this signs in the next 60 days?"

**Mitigation:** Push hard for an LOI before June 2. If Mindstate signs even a non-binding LOI, Slide 11 changes from "in motion" to "signed pilot with a [stage] drug-discovery startup." This single change materially upgrades the deck. If unsignable by Paris, the speaker note should preemptively address: "We're at handshake stage; CEO meeting next week; deliverable / payment / IP terms in active negotiation." Sophisticated investors will respect honesty more than puffery.

### 3. TAM construction is challengeable (MODERATE-HIGH RISK)

**The probe:** "Your $20–50B R&D-intel TAM is top-down with a 2–5% assumption. Your $5–9B AI-training-data TAM is a synthesis of three primary sources you triangulated yourself. What's the *real* near-term addressable revenue?"

**Mitigation:** Have a bottom-up SAM ready. *If* the first 50 mid-size R&D-intensive companies each pay $100K/year for the API, that's $5M ARR. *If* one frontier lab pays $5M/year for verified scientific training data, that's another $5M. The path to $50–100M ARR within 5 years routes through ~500–1000 mid-market R&D customers + 3–5 frontier-lab contracts. Make the bottom-up numbers small and concrete; let the top-down TAM justify the *upside*, not the *path*.

### 4. Competitive landscape is underplayed (MODERATE RISK)

**The probe:** "Why won't Scite, Elicit, Consensus, SciSpace, Undermind do this? They have headstart and capital."

**Mitigation:** The honest answer is structural, not feature-level. They all return *paragraphs near a query*. None of them produces *structured claim records with calibrated uncertainty and customer-specific ontologies*. Adding "claim extraction" as a feature to a RAG product does not produce a substrate — it produces another summary. The substrate requires a different architecture (extractor diversity, gold-data validation, ontology layer). This is a one-line in Slide 5 or Slide 7 ready for Q&A.

### 5. The team has zero Bittensor track record (MODERATE RISK)

**The probe:** "None of you has shipped on Bittensor before. Subnet economics is its own discipline. How do you de-risk this?"

**Mitigation:** Frame as "bringing an existing business *to* Bittensor, not learning Bittensor from scratch." SciWeave exists. The 0% hallucination benchmark exists. The first pilot exists. Bittensor adds a capability to a working product. We are not betting the company on subnet mechanics; we are augmenting a working product with a substrate it needs. Also: Christian is the dedicated mechanism-design hire precisely because we recognize this risk.

### 6. The "structure, not just scale" thesis is contestable (MODERATE RISK)

**The probe:** "Frontier labs would argue scale + better RAG + better tool use will eventually solve this without a structured graph. Why are you sure they're wrong?"

**Mitigation:** Two-part answer. (a) Even with infinite scale, you cannot compute *negative space* (gaps, missing replications, unexplored adjacencies) without explicit structure — scale-only systems can only retrieve what's been said, not characterize what hasn't. (b) Asai et al. and the broader retrieval-augmentation literature both empirically point to grounding and structure as the next reliability axis, not scale. Have these papers ready.

### 7. Customer-specific ontologies imply services revenue (MODERATE RISK)

**The probe:** "Co-developed enterprise ontologies sound like FDE-style services revenue. Slow scale, lower multiples. Is this really a SaaS?"

**Mitigation:** Be honest. The enterprise tier IS services-anchored. The metered API tier is pure SaaS. Slide 10's revenue funnel makes this explicit: free + metered API does the unit-economics scaling; enterprise is the high-ACV retention layer. Compare to Palantir's mix (Foundry vs. Apollo vs. AIP) — the ontology layer creates retention and ACV uplift even if it doesn't scale like pure SaaS.

### 8. Token economics is unspecified on the deck (LOW-MODERATE RISK)

**The probe:** "What's the supply cap? Emission schedule? Owner/validator/miner split? Burn rate at $X revenue?"

**Mitigation:** Data room. Do not put on slides — the level of detail crypto investors want here doesn't fit a 13-slide deck and creates more pickable surface area than it justifies. Slide 10 mentions the buyback-and-burn concept; the full economics live in the appendix.

### 9. "Why now?" is implicit but not stated (LOW-MODERATE RISK)

**The probe:** "Why couldn't this have been built in 2023?"

**Answer to have ready:** Four factors converging in 2025-26 that didn't in 2023:
(a) Frontier LLMs are now reliable enough to do extraction at near-zero cost per paper.
(b) ScholarQABench-class benchmarks now make extraction quality measurable.
(c) Bittensor's subnet model has matured enough to host real-world products (Ridges, Chutes as precedent).
(d) AI training-data demand has created a new buyer class for structured scientific data that didn't exist at scale before.

Could be a "Why now" callout on Slide 6 or 7 if it fits. If not on the deck, definitely in Q&A.

### 10. Defense (Anduril-class) customer adds long-cycle uncertainty (LOW RISK)

**The probe:** "Defense procurement is multi-year. Why mention it?"

**Mitigation:** Keep defense in pipeline language only. Don't anchor on it. The deck already does this correctly — Slide 5 stays drug-discovery-focused; defense is one of "two further enterprise prospects" in Slide 11.

---

## Is the storyline punchy enough?

**Strong:** Slides 1, 2, 3, 4, 5, 9, 13. These carry the deck.

**Improved in v5:** Slide 6 (anchored primary sources), Slide 7 (technical-depth pivot), Slide 8 (verified citation), Slide 10 (visual diagrams), Slide 11 (battle-tested flywheel).

**Still weakest:** Slide 12 (roadmap). Timelines tend to be forgettable. Consider sharper language — "By fall: signed pilot. By winter: subnet live, 50 miners. By 2027: 5 enterprise customers, buyback engaged." — but this is a minor improvement.

**Single line audience should walk out repeating (revised):**
*Same team that took scientific reference hallucination from 60% to 0%. Now building the layer underneath. On Bittensor.*

Echoes Slide 2 and reinforces Slide 13. Memorable, asymmetric, concrete.

---

## INFORMATION ASYMMETRY STRATEGY (unchanged)

What stays out of the deck and goes into deeper conversations only:

1. **The full incentive-mechanism design.** Interpretive-question testing, adversarial-claim testing, consensus-on-diagnostics, gold-data calibration, publication-bias defense. Show the *shape* of the hard problems we solve; do not spell out the solutions.
2. **Customer-specific ontologies and validator-scoring methodology.** Off-chain moat. Data room only.
3. **Identities of the three R&D prospects.** Anonymized until contracts sign.
4. **Full token-economics model.** Buyback math, emission curve, owner/validator/miner split, treasury policy.
5. **Acquisition / M&A context** for DeSci Labs. Private workstream per project instructions.
6. **The internal admission that compute cost is not the Bittensor argument.** The deck argues quality dynamics, capital efficiency, and open-competition compounding — not cost.

---

## OPEN ITEMS BEFORE PARIS

- Push for a signed LOI on the first pilot before June 2 (single biggest deck-strength improvement available).
- Final sourcing pass on every number that appears on any slide — verify WIPO 2025 $3T R&D figure, lock the Hanlon 2025 JAMA citation for Slide 8, confirm Labelbox CEO quote / Sacra figures / Mercor TechCrunch citation for Slide 6.
- Confirm Christian Roessler's public record / publications to anchor the team slide.
- Tighten Slide 12 roadmap language.
- Decide whether to add a "Why now" callout (Slide 6 footer or Slide 7 sidebar).
