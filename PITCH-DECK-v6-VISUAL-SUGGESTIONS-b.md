# Claims — Pitch Deck v6: Visual Slide Suggestions

**Source:** PITCH-DECK-v6-STORYLINE.md
**Design system:** Deck Design Spec v5 (May 2026)
**Total slides:** 13 (storyline's 13 with one strategic split — see scratchpad)
**Version:** -b · Slide 9 is the product centerpiece, bowtie/hourglass architecture (many miners → one canonical database → many enterprise ontologies → one answer for Simon). The Palantir-Foundry framing lives inside the top eyebrow of the bowtie diagram. Slide 2 is a three-tile metric row (no hero numeral). Cover footer-right eyebrow removed. Slide 11 (business model + moat) redesigned with symmetric grey shades + ink left borders progressing 4→5→6 px on both columns. Slide 6 buyer renamed Alex → Simon throughout. The former RAG vs. Claims Graph slide and the Traction + flywheel slide were both deleted in this revision: the first duplicated content already implicit in Slides 3 and 8; the second was scheduled to be replaced by a stronger traction artifact when the deck has named pilots to cite. All subsequent slides renumbered down accordingly; deck total now 13.
**Status:** Consolidated against spec v5 · ready for HTML build

---

## Scratchpad — narrative beats and pacing decisions

**Three-act flow:**
- **Act 1 — Pain & prize (Slides 1–4):** Hook with the broken state of scientific AI, the size of the locked prize, and the team's existing proof point. Land the purpose statement.
- **Act 2 — Buyer, market, demonstration (Slides 5–9):** Introduce the team, meet Simon (the buyer), frame the market, then show the RAG-vs-graph reveal and the computable-confidence layer.
- **Act 3 — Product, architecture, ask (Slides 10–15):** Show the product (open substrate + enterprise layer), explain why Bittensor, lay out the business model, traction, roadmap, close.

**One strategic split from the 13-slide storyline:**
1. **Storyline Slide 2 splits into visual Slides 2 + 3.** The "prize" (scale) and the "proof" (benchmark) are different emotional beats. Combined, they fight for attention. Apart, the $3T number lands and the 0% vs. 62% comparison lands. Three equal-weight tiles on Slide 2 carry the prize beat without a hero numeral fighting them.

The earlier second split — Storyline Slide 5's buyer narrative spread across visual Slides 6 (Meet Simon) and 8 (RAG vs. Graph reveal) — was collapsed in this revision. Slide 8 (the reveal) was deleted because it duplicated information already implicit in Slides 3 and the Computable-Confidence slide, and was adding more confusion than clarity. The buyer's question (Slide 6) now stands on its own and the speaker delivers the RAG-vs-graph distinction verbally rather than via a side-by-side card layout.

**Visual metaphors carrying weight in this deck:**
- Three equal numerical tiles → the size of the locked prize, with the punchline (0%) flagged in copper (Slide 2)
- Empty space / negative space → the missing structure in scientific knowledge (Slide 4)
- Bar chart with one bar at zero → the hallucination delta (Slide 3)
- Two stacked lead statements → the two dimensions of computable confidence (Slide 8)
- Two-tier stack → open substrate + enterprise ontology (Slide 9, the centerpiece)

**Archetype usage per spec v5:** Slide 2 uses the **metric tile row** of §4.5 (three equal tiles centered vertically — no hero numeral, no paired-hero pattern). Slide 3 is a chart-as-hero (§4.3 pure variant). Slide 6 uses the **display variant** of §4.10 quote card (single hero quote, oversized treatment). Slide 7 uses the **metric-tile composition** of §4.5 (two large numerals side by side with a converging-arrow connector — explicitly the metric-tile row, since spec v5 forbids paired hero-stats). Slide 9 is a custom two-tier stack diagram (architecture / centerpiece). Slide 10 uses the standard short-list of §4.4 with 1pt rules as bullets.

**Logos carry the trust and reputation signal on the Team slide (Slide 5). The founder pictures add a personal, professional appeal. The assets are in the `C:\Users\phili\Coding\Claims\Logos and pictures\` folder.**

---

## Slide 1: Cover — Claims

**Visual Concept:** Full-bleed hero render of the Claims subnet artwork — the geodesic dome on a floating tetrahedron platform, suspended in clouds. Source file: `Logos and pictures/cover-art.jpg`. The dome and the entire upper image stay completely clear. A single linear gradient along the bottom (transparent at 50% height → `rgba(11,18,32,0.45)` at 72% → `rgba(11,18,32,0.85)` at 100%) creates the high-contrast band where all text lives. Per spec v5 §4.1: no left-edge ink band on the cover (the image is the band), no CLAIMS wordmark in the corner (the image is the lockup), no footer-right eyebrow (the title carries the identity alone).

**Text on Slide** — all anchored to the bottom of the slide (`bottom: 100px`), inside a single block from `left: 160px` to `right: 160px`:
- **Title** (Inter Light, 112px / `type.title-xl`, `color.paper`): `Claims`
- **Subtitle**, directly beneath the title with `space.lg` margin (Inter Light Italic, 36px, `color.paper` at 90% opacity): *The canonical claim-evidence graph for science.*
- **Tagline only** on a single footer line (Inter Regular, 22px, `color.mist`): A Bittensor subnet. By the team that built *SciWeave*. Right side of the footer band intentionally empty — no eyebrow, no date, no venue stamp competing with the title.

**Key Figures:** none — this is the identity slide.

**Layout Notes:** Title baseline ~y=830. Subtitle baseline ~y=890. Tagline baseline ~y=965. Right cols stay empty above the tagline so the dome reads through cleanly. No page numeral on cover. No section tab.

**Speaker Notes:** Lead with the three-word identity. "Claims — a Bittensor subnet by the team that built SciWeave. The canonical claim-evidence graph for science." Pause. Don't elaborate yet. The next slide does the work.

---

## Slide 2: AI ate the internet. Science is what it can't digest.

**Visual Concept:** **Metric tile row (§4.5).** Three equal-weight numerical tiles in a row, vertically centered on the stage. No hero numeral. No eyebrow above the tiles. The slide reads as one sequenced argument — global R&D spend, the volume of published evidence, and the punchline that none of it is machine-readable. The third tile carries the only color accent (`color.copper`) because the 0% is the rhetorical payoff. Generous whitespace above and below the tile row — the stage breathes.

**Text on Slide:**
- Title (small, top, `type.title` 56px): `AI ate the internet. Science is what it can't digest.`
- Three metric tiles in a row, vertically centered (~y=540). Each tile: 2pt rule + numeral (Inter Light, 80px) + label (Inter Regular, 20px, `color.graphite`).
  - `$3T+` — R&D spending annually<sup>1</sup>
  - `300M+` — scientific articles exist
  - `0%` — structured as machine-readable data  *(numeral and 2pt rule both in `color.copper`)*
- Reference strip at the bottom of the slide (Nature numbered-superscript pattern per spec §5, Inter Regular 14px, `color.graphite`, hairline rule above):
  `¹ World Intellectual Property Organization (WIPO), 2025.`

**Key Figures:** $3T+, 300M+, **0%**

**Layout Notes:** Tile row spans cols 1–9 of the 12-col grid, vertically centered around y=540. Right cols 10–12 stay empty. Tiles are equal width with a `space.2xl` gap between them. The `0%` tile is set in `color.copper` to flag it as the punchline. The superscript `¹` on the first tile's label corresponds to a single `¹` line in the reference strip — Nature numbered pattern per spec §5, applied even though only one source is cited so the convention stays consistent with slide 3 and any other multi-reference slides. 1T+ ("words") is dropped from earlier drafts to keep the slide to three numbers and reserve the rhetorical payoff for 0%.

**Speaker Notes:** "Three trillion in global R&D spending annually. Three hundred million papers exist. Zero percent of that is structured as machine-readable data. The biggest pile of human intellectual capital ever assembled — and AI can't make sense of it."

---

## Slide 3: Frontier models hallucinate science

**Visual Concept:** Horizontal bar chart, three bars. Hallucination rate on the x-axis (0% to 70%). Claude Opus 4.6 and GPT-5.2 bars in `color.ink` and `color.atmosphere` — both competitors recede into the muted-twin look so the visual gap to SciWeave reads as one beat. The SciWeave bar at 0% is essentially absent — replaced by a thin `color.moss` rule at the baseline with a circled "0" floating where the bar would be. The visual gap between the frontier-model bars and the SciWeave non-bar IS the slide.

**Text on Slide:**
- Title (`type.title` 56px, `color.ink`): `Frontier models hallucinate science`
- Subtitle (`type.subtitle` 36px, `color.graphite`): Hallucinated references on ScholarQABench<sup>1,&nbsp;2</sup> — biomedical and neuroscience. (superscripts in `color.claims-blue`, Inter Medium, 60% size — Nature in-body citation style)
- Bar labels (Inter Medium 24px):
  - Claude Opus 4.6 — `62%`
  - GPT-5.2 — `59%`
  - *SciWeave* — `0%` (the product name italicized per spec rule)
- Bottom-strip takeaway (Inter Light 28px, `color.graphite`, pushed low to breathe): RAG eliminates fake citations. It still only parrots what authors said.

**Key Figures:** 62%, 59%, **0%**

**Layout Notes:** Chart occupies cols 1–9, bars right-justified so the 0% endpoint sits at the visual end of the chart for the SciWeave row, dramatizing the gap. The takeaway line lives at y=900, separated from the chart by 80px whitespace. Reference strip uses the **Nature numbered-superscript pattern** per spec §5 — anchored at `bottom: 110px` so it grows upward as references are added, with the last reference's distance to the footer preserved. 8px breathing-space gap between references. Two references:

`¹ Asai et al., 2026. Synthesizing scientific literature with retrieval-augmented language models, *Nature* (650), 857–863. https://doi.org/10.1038/s41586-025-10072-4`

`² DeSci Labs, 2026. Zero hallucinated citations: SciWeave's ScholarQABench results. https://www.desci.com/blog/zero-hallucinated-citations-sciweaves-scholarqabench-results`

**Speaker Notes:** "The frontier models hallucinate roughly 60% of biomedical references. SciWeave hallucinates zero. That's the team standing in front of you. But — RAG can only parrot what authors said. Contradictions, gaps, and missing links that drive scientific progress aren't visible to AI. The canonical claim-evidence graph for science is missing."

---

## Slide 4: Purpose

**Visual Concept:** Visual metaphor for "negative space." Left two-thirds: a sparse graph-network illustration — circular nodes (`color.ink`) connected by hairline edges, but with deliberate gaps and broken/contradicting edges shown in `color.copper`. Some nodes are filled, some are outlined-only (representing missing claims). The visual reads as scientific knowledge with its holes made visible.

**Text on Slide:**
- Slide title (`type.title` 56px, `color.ink`, standard top position at x=128, y=128): `Our Purpose.` Treated identically to every other content slide's title — no eyebrow above it, no custom position.
- Thesis statement, left column of the purpose-grid (`type.title` 56px Inter Light, `color.ink`, three explicit lines): The claim-evidence graph / that makes the negative / space of science computable. Each line is wrapped in a `<span class="line">` with `display: block; white-space: nowrap` — guarantees the three-line break pattern survives across browsers and Chrome's screen-vs-print font metric drift (the earlier `<br>`-only version broke to four lines in PDF output because the middle line soft-wrapped at a different point than on screen).
- Subtext below the thesis (Inter Regular 32px, `color.graphite`): Scientific AI needs structure,<br>not just scale.

**Key Figures:** none — this is a thesis slide.

**Layout Notes:** Slide title `Our Purpose.` sits in the standard slide-title slot (x=128, y=128, `type.title` 56px). Content area begins at y=240 like every other content slide. The purpose-grid is intentionally asymmetric — `grid-template-columns: 1.25fr 1fr` with a 140px gap — text column ~860px, graph column ~690px. This is the lever that lets `space of science computable.` fit on a single line at 56px Inter Light (with nowrap spans on each line as bulletproofing against font-metric drift between screen and PDF render) and also creates "plenty of padding" between the text and the graph. Vertical alignment is `center`: thesis + subtext sit as a single grouped block (subtext directly beneath thesis with a 32px gap) vertically centered in the content area, and the graph mirrors that centering on the right. The thesis uses `type.title` 56px Inter Light — lighter weight than the slide title (which is Inter Regular at the same size) so the two read as parallel-but-distinct registers rather than competing titles. The graph SVG uses `preserveAspectRatio="xMidYMid meet"`; SVG label font-size is **18 (up from 13)** so `contradicts` and `negative space` remain readable at presentation distance after the graph is rescaled down into the asymmetric column. The `contradicts` label is placed at x=420 (inside the SVG viewBox) — pulled west of its naive midpoint to sit closer to the dashed orange `contradicts` edge it annotates and clearly farther from the unrelated black dot to its right. The thesis block uses a 64px `margin-bottom` between thesis and subtext (not the default 32px) to give the WHAT/WHY pair visible breathing room. Broken-edge / gap motifs are highlighted in `color.copper`. The thesis leads with what we DO; the subtext supplies the WHY.

**Speaker Notes:** "We build the layer that makes gaps, contradictions, and missing links computable — the invisible negative space that drives scientific progress. Because scale alone keeps producing more confident, but not more verifiable outputs. The next reliability dimension is structure."

---

## Slide 5: Team

**Visual Concept:** Three-column founder layout. Each column is fully center-aligned — portrait, name, role(s), headline, and logos all centered horizontally. The grid is top-aligned (not vertically centered on the stage) so the portrait row sits high in the content area, giving the longer headlines room to breathe. Portraits are circular with a `color.ink` frame. Logos render in monochrome ink at small scale (greyscale filter + brightness drop + contrast). Portraits and logo files pulled from `C:\Users\phili\Coding\Claims\Logos and pictures\`.

**Text on Slide:**

- Title (`type.title` 56px, `color.ink`): The team.

- **Column 1 — Dr. Philipp Koellinger**
  - Role line 1: `CEO, DeSci Labs / *SciWeave*`
  - Role line 2: `Professor of Economics`
  - Headline (Inter Regular 22px, `color.ink`, no italic on the whole block): Led 300+ scientists in a GWAS consortium that fixed replication in behavioral genetics, building the data standard of that field. Published in *Nature* and *Science*. (Journal names italicized inline per the §5 citation convention; the rest of the sentence sits in Regular weight so the journal italics actually pop.)
  - Logo row 1: DeSci Labs · VU Amsterdam · UW–Madison
  - Logo row 2: *Science* · *Nature*

- **Column 2 — Sina Iman**
  - Role: `CTO, DeSci Labs / *SciWeave*`
  - Headline: ML, blockchain, cryptography. Early Palantir engineer.
  - Logo row 1: DeSci Labs · Palantir
  - Logo row 2: Booz Allen Hamilton · NSA

- **Column 3 — Dr. Christian Roessler**
  - Role: `Professor of Economics`
  - Headline (three explicit lines, breaks after sentence periods and after the second `incentives`): Game theory and mechanism design.<br>Generally optimal incentives<br>for Bittensor subnets.
  - Logo row 1: U. Melbourne · Brown · Rice
  - Logo row 2: U. Vienna · Cal State

**Key Figures:** none — the team itself is the figure. The earlier copper micro-stat (`300+`) is retired; the number is now embedded in Philipp's headline sentence at standard body weight rather than highlighted as a separate accent.

**Layout Notes:** Three strictly equal-width columns. CSS uses `grid-template-columns: repeat(3, minmax(0, 1fr))` rather than plain `1fr 1fr 1fr` — the `minmax(0, 1fr)` floor stops any single column from expanding past its share when its content tries to overflow (the failure mode that pushed Philipp's column wider than the others in the previous build). Gap between columns is `space.3xl` (64px). Portraits are 200×200 circles with a 3pt `color.ink` border. Names in Inter Medium 30px. Roles in Inter Regular 22px with `min-height: 62px` reserved so Philipp's two-line role and the other founders' single-line role still align at the headline-start position. Headlines in Inter Regular 22px (no italic) with `min-height: 168px` reserved to absorb Philipp's longer four-line headline without forcing Sina/Christian into excess whitespace below their shorter two-line headlines. Logo rows stack inside a `.logo-rows` flex column with `12px` gap; each logo at 36px height, max width `110px`, monochromed via greyscale filter + brightness drop + contrast bump for a uniform institutional palette. Entire grid `align-items: flex-start` so it sits at the top of the content area (y=240) rather than vertically centered.

Cross-column alignment: names align at the same y (single-line names everywhere). Roles align at the same y (`min-height: 62px` on `.team-role`). Headlines align at the same y (`min-height: 168px` on `.team-headline`). Logos start at the same y for all three founders, regardless of whether they have one or two rows of logos beneath.

**Speaker Notes:** "Three founders. Philipp is CEO of DeSci Labs and a Professor of Economics — he led the GWAS consortium that fixed replication in behavioral genetics, 300+ scientists, and built the data standard that field still runs on. Published in Nature and Science. Sina built ML and crypto infrastructure at Palantir from the early days. Christian is a mechanism-design economist — he owns the incentive layer for the subnet."

---

## Slide 6: Meet Simon.

**Visual Concept:** **Display variant of §4.10 quote card** — a single quoted question, set as a hero typographic statement. The question itself IS the visual. Light parchment quote-card behind the text gives it object weight without ornament. Small contextual eyebrow above identifies the buyer. The right third of the slide is empty.

**Text on Slide:**
- Title (`type.title` 56px, `color.ink`): Meet Simon.
- Quote-card (display variant — `color.parchment` fill, `radius.lg`, `space.2xl` padding):
  - Decorative opening quote mark (Inter Light, 120px, `color.claims-blue`)
  - Question (Inter Regular 44px, `color.ink`, line-height 1.4): Through which mechanisms does *5-MeO-DMT*<br>affect mental health outcomes?
- Context strip below the card (Inter Regular 24px, `color.graphite`, max-width 1560px so the third line fits without wrapping): Well-funded biotech startup. Thousands of papers to find and review.<br>An FDA-relevant decision. Failing to vibe-code an AI research workflow himself.<br>Willing to pay us for a pilot. Two additional pilot customers in line. Three explicit lines, breaks only after a sentence-final period — never mid-clause.

**Key Figures:** none — the question is the figure.

**Layout Notes:** Quote-card occupies cols 1–8, vertically centered around y=480. Context strip sits 80px below the card, also constrained to cols 1–8. Right cols 9–12 empty. No bar chart, no diagram — the question carries the slide.

**Speaker Notes:** "Here's a real buyer with a real decision. They're already using SciWeave for first-pass exploration. They tried to vibe-code an AI research workflow on their own and gave up. They need something underneath. Watch what happens when they ask this question of two systems."

---

## Slide 7: Market.

**Visual Concept:** Three-element row, all three elements at parity. Two market tiles flank a centered **Claims** wordmark, with a polyhedron + converging-arrows motif sitting where a tile rule would normally sit. All three columns share a fixed-height top row (80px) — the 2pt rules in the side tiles and the arrow line in the hub are vertically centered in that row, so they align across the slide. Below the top row, all three columns carry the same hero element: `$20–50B`, `Claims`, `$5–9B` — Inter Light 80px, same y, same size, same font. The product name is no longer rendered as a brand-mark in letter-spaced uppercase; it sits as a typographic peer of the dollar numbers, which makes the slide read "Claims is what these two markets converge on, at the same weight as the markets themselves." Per spec v5 the hero-stat archetype is forbidden from pairing two heroes; the side tiles are explicitly metric-tile elements (§4.5), not hero stats.

**Text on Slide:**
- Title (`type.title` 56px, `color.ink`): Market.
- All three columns share a fixed-height **top row** (80px). The 2pt rule in each tile and the arrow line in the hub are vertically centered in that row, so they sit at the same y across the three columns.
- Left tile (Inter Light 80px tabular-nums, `color.ink`, `white-space: nowrap`): `$20–50B`
  - Supporting line, **left-aligned** (Inter Regular 22px, `color.graphite`): R&D intelligence and evidence work
  - Growth tag, left-aligned (Inter Medium 16px, `color.moss`): +5% / yr · R&D spending growth · OECD
- **Claims hub** (between the two tiles):
  - Top row (80px): two 2.5pt converging arrows in `color.claims-blue` flowing inward from the left and right edges of the SVG, with a centered polyhedron icon between them at the same y as the arrow line. The polyhedron is `color.ink` fill with hairline `color.graphite` internal facet lines and a tiny white vertex dot at the center — same six-vertex polygon used as a callback to the cover artwork's geodesic dome.
  - **Wordmark** beneath, Inter Light 80px, `color.ink`, `white-space: nowrap`, `letter-spacing: -0.02em`: `Claims`. Identical type to the side tiles' dollar numerals so all three hero elements read as equally weighted, equally tall, equally important. No tagline beneath.
- Right tile (Inter Light 80px tabular-nums, `color.ink`, `white-space: nowrap`): `$5–9B`
  - Supporting line, **left-aligned** (Inter Regular 22px, `color.graphite`): AI training data for scientific models
  - Growth tag, left-aligned (Inter Medium 16px, `color.copper`): +100% / yr  *(format mirrors the left tile's "+5% / yr"; mathematically equivalent to the earlier "~2× year over year" but parallel in grammar so the two markets read as comparable growth figures rather than "one is a percentage and the other is a multiplier")*

**Key Figures:** $20–50B, $5–9B, +5%/yr, ~2× YoY

**Layout Notes:** Flex row, `justify-content: space-between`, `align-items: flex-start`. Each tile and the hub are `flex: 0 0 auto` so they size to their content; the remaining horizontal slack distributes evenly into two equal gaps — one between the left tile and the hub, one between the hub and the right tile. This is **load-bearing**: with the earlier `grid-template-columns: 1fr auto 1fr` layout, each side column was forced to the same fixed width (~610px), and the left-aligned content inside the left column left ~170px of empty space *between the left tile content and the hub*, while the right tile content sat flush against the hub on its side — so the visual whitespace around the hub was ~266px on the left and ~96px on the right, and "Claims" read as off-center to the right. Switching to flex + space-between collapses the in-column emptiness into the inter-tile gap on both sides, so the whitespace around the hub is symmetric.

All three columns top-align so the rules and the arrow line meet at the same y, and the dollar numerals and the `Claims` wordmark meet at the same y. The hub SVG is **deliberately narrow (300px wide, polyhedron at 22-unit radius)** so the supporting lines "R&D intelligence and evidence work" and "AI training data for scientific models" each fit on a single line. The hub has no internal horizontal padding. Both side tiles are **internally left-aligned** (rule, numeral, label, delta all flush-left within the tile), which the user explicitly requested; the hub still ends up centered because flex space-between distributes the slack symmetrically rather than partitioning it into fixed columns. The hub's wordmark is rendered in the same Inter Light 80px type as the dollar numerals — explicitly NOT the letter-spaced UPPERCASE brand-mark style used in the slide footer. The earlier brand-mark treatment + italic tagline were dropped because they out-shouted the markets they were supposed to converge on; making "Claims" a peer of the dollar figures (same type, same height, same weight) lets the slide read as one balanced equation. Reference strip at the bottom: *WIPO 2025 · Labelbox (Cognitive Revolution podcast, Jul 2025) · Sacra (Surge AI, Scale AI) · TechCrunch (Mercor, Oct 2025)*.

**Speaker Notes:** "Two large, growing markets converge on the same product. Literature review and desktop research tasks — $20 to 50 billion a year, 5% R&D budget growth in OECD countries. AI training data — $5 to 9 billion in 2025, doubling year over year. Both pools need the same thing: structured, verifiable claims at scale."

---

## Slide 8: Computable confidence — the missing layer.

**Visual Concept:** Type-driven slide, no diagrams. Two lead statements stacked vertically at `type.title` size (Inter Light 56px, `color.ink` — same size as the slide title, slightly lighter weight to keep them as peers rather than competitors). A smaller `type.body` (Inter Regular 32px, `color.graphite`) subtext sits beneath each lead. The two statements are the two dimensions of uncertainty the substrate measures — extraction and source — and they're sized as content-level peers of the slide title so the slide reads as one structural argument: "here is the missing layer, and here are its two dimensions." The earlier 84px Light treatment was reduced because lead text *larger* than the title competed with the title for visual primacy and felt off-balance. Title fits on a single line. Content uses the full content width.

**Text on Slide:**
- Title (`type.title` 56px Regular, `color.ink`, single line, no `<br>`): Computable confidence — the missing layer.
- Lead statement 1 (Inter Light 56px, `color.ink`, letter-spacing -0.005em): Extraction uncertainty.
  - Subtext (Inter Regular 32px, `color.graphite`): Many extractors. Calibrated against gold data.
- Lead statement 2, separated from the first by `space.4xl` (96px): Source uncertainty.
  - Subtext (Inter Regular 32px, `color.graphite`): Replication, p-hacking, file drawer.<sup>1–4</sup>  *(in-body en-dash range superscript in `color.claims-blue` per spec §5 — three or more consecutive references collapse to the range form `1–4`, not the comma list `1,2,3,4`. This is the official Nature reference format.)*

**Key Figures:** none — the two lead statements are the slide's structural content.

**Layout Notes:** Two stacked blocks in the content area, vertically centered within `padding-bottom: 160px` (a deliberate asymmetric padding that shifts the visual center of the hero content upward by ~80px). Without that padding the hero blocks centered too low — gap from title to hero (~262px) was much larger than gap from hero to reference strip (~72px). With the padding-bottom, the gaps roughly equalize (~150px on each side), and the slide reads as title → hero → references with symmetric vertical rhythm. Each block: lead at 56px Light, 16px gap, subtext at 32px Regular. Between blocks: 96px vertical gap. Block width: full content width (~1712px).

**Reference strip** (4 references, Nature numbered-superscript pattern per spec §5, anchored at `bottom: 110px` so the strip grows upward as references are added — distance from the last reference to the footer is preserved):

`¹ Open Science Collaboration (2015): Estimating the reproducibility of psychological science. *Science* 349(6251). https://www.science.org/doi/10.1126/science.aac4716`

`² Prinz et al. (2011): Believe it or not: how much can we rely on published data on potential drug targets? *Nature Reviews Drug Discovery* 10(712). https://www.nature.com/articles/nrd3439-c1`

`³ Baker (2016): Biotech giant publishes failures to confirm high-profile science. *Nature* 530(141). https://www.nature.com/articles/nature.2016.19269`

`⁴ Ioannidis (2005): Why most published research findings are false. *PLoS Medicine* 19(8), e1004085. https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.0020124`

`8px` margin-top between consecutive references for breathing space, matching Slide 3.

**Speaker Notes:** "Humans are too slow and too expensive to generate a complete claims-evidence graph. AI has to assist to scale this. But AI is probabilistic, so two sources of uncertainty have to be measured. Extraction uncertainty — AI outputs vary by run, prompt, model. We address it by running many independent extractors and calibrating against gold-data curated by domain experts. Source uncertainty — roughly half of published findings don't replicate (Open Science Collaboration, Prinz, Baker, Ioannidis). We address it by ranking sources for design quality, sample size, and replication record. Every claim ships with a confidence interval. That's the statistical artifact nobody else in this space produces."

---

## Slide 9: Inner loop.

**Visual Concept:** Clock-as-cycle diagram. Two role labels (`Miners` and `Validators`) sit at the 9 o'clock and 3 o'clock positions of an implicit clock face. Two **true circular** half-arcs span the space between them — one curving over the top from Miners → 12 → Validators, one curving under the bottom from Validators → 6 → Miners — producing a clockwise rotation that reads as an ongoing two-party cycle. The two arcs are **separated by an 80px vertical gap at each role-label position so they never touch**; the role-name text sits centered in that gap, so visually each arrow approaches or departs the role from above OR below the label, not through it. Beneath each role label, a short vertical list of qualifying terms describes that party's contribution to the loop. No text in the middle of the cycle, no rotating dial gimmick, no shaded clock face — the arcs alone do the work.

**Text on Slide:**
- Title (`type.title` 56px Regular, `color.ink`, standard slide-title slot at x=128, y=128): `Inner loop.`
- **Miners role** (Inter Light 56px, `color.ink`, letter-spacing -0.005em, horizontally centered in a 360px block anchored at `left: 60px`, vertically positioned with `top: calc(50% - 80px)` and `transform: translateY(-50%)` — role-name center at content y=280, i.e., 80px above the content midline, creating more whitespace between the role block and the attrs below it): `Miners`
  - Qualifying terms beneath the role label (Inter Regular 32px, `color.graphite`, centered, anchored at `top: calc(50% - 10px)` so the first attribute baseline sits 70px below the role-name center, 1.5 line-height between attributes): `Source` / `Claim-evidence` / `Concept binding` / `Judgment`
- **Validators role** (same typographic treatment, anchored at `right: 60px`): `Validators`
  - Qualifying terms beneath: `Assign` / `Verify` / `Gold set` / `Calibrate`

**Key Figures:** none — this is a process diagram, not a metric slide.

**Layout Notes:** SVG layer fills the full content area (viewBox `0 0 1712 720`, 1:1 with the content pixel dimensions, `preserveAspectRatio="xMidYMid meet"`, **`overflow: visible`** in CSS so the top half-circle can extend above the viewBox into the area between the slide title and the SVG box). Two `<path>` elements draw **true circular half-arcs** via SVG's elliptical-arc command with `rx=ry`:
- Top arc: `M 632,240 A 224,224 0 0 1 1080,240` — half-circle with chord 448 (= 2 × radius, so the chord IS the diameter and the arc is exactly 180°). Circle diameter was tuned through two iterative reductions: original 800 → 560 (-30%) → 448 (-20%), total ~44% reduction from the starting size. The smaller diameter places the circle's top extent at slide y≈256 — comfortably below the title at slide y≤192 — and gives the loop visual the proportions of a contained clock symbol rather than a structural element that fills the slide. Endpoints sit at content y=240, which is 40px above the role-name axis at y=280. The arc peaks at viewBox y=16 (just inside the SVG viewBox top edge). `large-arc-flag=0`, `sweep-flag=1` (positive-angle direction in SVG's y-down coordinate system = visually clockwise = via 12 o'clock). The endpoint tangent at (1080, 240) is perpendicular to the radius, pointing straight down, so the arrowhead aligns vertically and lands cleanly into the Validators label area below the arc endpoint.
- Bottom arc: `M 1080,320 A 224,224 0 0 1 632,320` — mirror of the top. Endpoints at content y=320 (40px below the axis), peak at content y=544 (well inside the content area). Endpoint tangent at (632, 320) points straight up; arrowhead arrives at Miners from below.

Stroke is `color.ink` 2.5px. Arrowheads are simple triangles (12×12 viewBox marker, `refX=10` so the tip sits at the path endpoint, `orient="auto"` so each arrowhead rotates to match its arc's tangent direction).

`z-index: 2` on the role blocks, `z-index: 1` on the SVG layer — the role labels render on top of the arc endpoints, but because the endpoints are vertically offset 40px from the role-name center, the arcs don't intersect the text in the first place. The 80px gap between top-arc endpoint (y=240) and bottom-arc endpoint (y=320) is what the user explicitly asked for — the arcs don't touch each other at any point, with the role-name text occupying the central strip in between.

Section label in the footer-tab: `06 · INNER LOOP`. Subsequent sections bump by one: `07 · PRODUCT`, `08 · WHY BITTENSOR`, `09 · BUSINESS MODEL`, `10 · ROADMAP`.

**Speaker Notes:** "How does the subnet actually produce the canonical claim-evidence graph? A two-party loop. Miners do four things in sequence: source the literature, extract claim-evidence pairs, bind those claims to concepts in the ontology, and attach a judgment — a calibrated probability. Validators do four things back: assign extraction tasks to specific miners, verify the work, cross-check it against the gold set curated by domain experts, and calibrate the scoring function that translates miner output into Bittensor rewards. The loop turns continuously — each pass tightens the calibration. That tightening is what produces the confidence intervals you saw on the previous slide. This is the mechanism. The next slide shows the full architecture this loop plugs into."

---

## Slide 10: Incentive mechanism.

**Visual Concept:** The reward function. A single equation — the miner's channel-based reward `R_m` as a sum of gate-dependent channel scores minus penalties — sits as the load-bearing visual on the left, with a variable legend on the right. No icons, no flowchart, no chart. The equation IS the slide; the legend is the decoder ring. This is the slide that buys the deck its technical credibility with Bittensor-aware investors and miner candidates — the people who will register a subnet, run a miner, or stake against the validator have all seen reward functions and want to see ours.

The equation is rendered with **KaTeX** (loaded from CDN in `<head>`) so it appears in true math typography (Computer Modern italic variables, properly stacked aligned terms, real subscripts) — not faked with HTML italic tags. KaTeX's auto-render scans the document for `\[ ... \]` (display math) and `\( ... \)` (inline math) delimiters and replaces them with rendered math on page load. The deck previously had no math rendering — this is the first slide that needs it, so KaTeX is added as a small CDN dependency alongside the Inter webfont link already in `<head>`.

**Text on Slide:**
- Title (`type.title` 56px Regular, `color.ink`, standard slide-title slot at x=128, y=128): `Incentive mechanism.`

- **Left half — the reward function** (KaTeX-rendered display math, vertically centered in the left column of a 1fr-1fr grid with 100px gap, parent font-size 36px so KaTeX scales the equation accordingly):

  ```
  R_m = λ_A · S_A
      + λ_B · G_A · S_B
      + λ_C · G_A · G_B · S_C
      + λ_D · G_A · G_B · G_C · S_D
      − P_spam − P_collusion − P_reset.
  ```

  Source LaTeX (verbatim from whitepaper §7, *Dependency Gates and Payout Aggregation*):
  ```latex
  \[
  \begin{aligned}
  R_m ={}& \lambda_A S_A \\
  &+ \lambda_B G_A S_B \\
  &+ \lambda_C G_A G_B S_C \\
  &+ \lambda_D G_A G_B G_C S_D \\
  &- P_{spam} - P_{collusion} - P_{reset}.
  \end{aligned}
  \]
  ```

  The recursive gating structure is the load-bearing pedagogical content: `λ_B S_B` is multiplied by `G_A` (downstream payment only when upstream source integrity passes), `λ_C S_C` is multiplied by `G_A · G_B` (and so on). A miner can't farm late-stage rewards by skipping the work upstream — fabricated source anchors zero out everything downstream. This is what differentiates Claims's mechanism from naive "many extractors, average their scores" subnets, and it's what makes the math worth showing.

- **Right half — variable legend** (vertically centered, 30px Inter Regular for the descriptions, KaTeX-rendered inline math for each variable symbol so it matches the equation's typography exactly):

  | Symbol | Definition |
  |---|---|
  | `R_m` | Reward for miner `m` |
  | `A` | Source integrity and coverage |
  | `B` | Atomic extraction |
  | `C` | Claim graph construction |
  | `D` | Evidence judgment and prediction |
  | `λ` | Task weight |
  | `G` | Gate weight |
  | `S` | Task score |

  The legend lists `R_m` first (the left-hand side of the equation), then the four channel labels (A–D), then the three operator symbols (λ/G/S). All variable symbols are wrapped in `\(...\)` so KaTeX renders them in the same math italic typography as the equation on the left — `R_m` in the legend matches `R_m` in the equation, glyph for glyph.

**Inconsistencies flagged against the whitepaper:**
The user-supplied legend is faithful to the channel definitions (A/B/C/D match whitepaper §6 subsection titles verbatim). Two pieces of terminology are loosened from the whitepaper's precise definitions for pitch-readability:

1. **`λ` is called "task weight" on the slide; the whitepaper calls it "score intensity".** Functionally λ_j is the rate at which channel `j`'s validated score gets converted into reward (whitepaper §10.2.1 and §10.4.1 use the launch values λ = (0.95, 0.95, 0.90, 0.85) — these are intensities, not fixed allocation shares). The whitepaper distinguishes λ (intensity) from `q` (the channel allocation vector, `q^launch = (0.35, 0.35, 0.20, 0.10)`). "Task weight" on the slide conflates the two; technically correct only at the level "more λ = more reward for that task". For a pitch deck this elision is fine — but in Q&A with a Bittensor mechanism designer, say "score intensity" if asked.
2. **`G` is called "gate weight" on the slide; the whitepaper calls it a "dependency gate".** G_A, G_B, G_C are data-dependent multipliers in [0, 1] that gate downstream payouts based on upstream channel quality. "Weight" connotes a fixed coefficient, which is misleading — these are run-time values that close (toward 0) when upstream work is unreliable. More accurate slide wording would be "Dependency gate" or "Upstream gate". Again, fine for the pitch register.

Penalty terms `P_spam`, `P_collusion`, `P_reset` are not defined in the legend. They are subtractive penalty terms; brief gloss in Q&A: "spam, collusion, identity-reset gaming — standard Bittensor abuse vectors that we explicitly subtract from the channel sum."

**Key Figures:** none — the equation is the figure.

**Layout Notes:** Content area is divided into a `1fr 1fr` grid with a 100px gap, vertically centered. Left cell holds the KaTeX-rendered display math; right cell holds the variable legend as a `display: grid` two-column layout (`max-content 1fr`) so the variable symbols right-align in a tight first column and the descriptions left-align in a wider second column. Column gap 36px between symbol and description, row gap 14px between variables. A 1px `color.fog` divider spans both columns between the A/B/C/D group and the λ/G/S group, signalling that "channels" and "mechanism" are two different categories of variable. KaTeX uses its own font stack (KaTeX_Math italic, KaTeX_Main upright); the surrounding Inter typography is preserved for the descriptions and the legend chrome.

**Speaker Notes:** "Here's the actual reward function. Four channels — source integrity, atomic extraction, claim graph construction, evidence judgment and prediction. Each channel pays a miner a weighted score `λ S`. The interesting part is the recursive gating. Channel B's payment is gated by `G_A` — you only get paid for atomic extraction if your sources passed. Channel C is gated by `G_A · G_B`. Channel D by `G_A · G_B · G_C`. A miner who fabricates source anchors gets zero downstream credit — not partial credit, zero, because every later term has `G_A` as a factor. This is what gives Claims a fabrication-resistant mechanism by construction, not by hoping validators catch every cheat. The penalty terms — spam, collusion, identity reset — are the standard Bittensor abuse vectors, subtracted explicitly. Full derivation is in the whitepaper, section seven."

---

## Slide 11: The Product.

**Visual Concept:** A bowtie / hourglass architecture diagram that encodes the actual data flow through the three-layer subnet: **many miners → one canonical database → many enterprise ontologies → one specific answer for one specific buyer.** The diagram occupies most of the slide; below it sits a single concrete output ("Answer for Simon") that shows what the architecture actually produces.

The three layers, read bottom-up:

1. **Miner claim-evidence streams (bottom).** Twelve ink dots evenly spread across the full content width, with a small `color.graphite` UPPERCASE eyebrow on the left reading `MINER STREAMS`. These represent the open substrate — anyone can run a miner, anyone can watch the stream. Twelve `color.mist` lines fan upward from the dots, converging onto the bottom edge of the central database band. The dots-and-fan visual is deliberately diffuse: the bottom layer is *many*.

2. **Validators · Canonical claim-evidence database (middle).** A horizontal `color.parchment` rectangle (`color.ink` border, `radius.md`), centered, 640 SVG units wide, labeled `Canonical claim-evidence database` in Inter Medium 20px ink. A `VALIDATORS` eyebrow sits at the left of the band; `API · MCP` sits at the right edge — the access plane. This is the bowtie's *waist*: many miner streams converge here, and many ontologies branch out of here.

3. **Enterprise · Subnet owners (top).** Three `color.claims-blue` dots, each with a label above it: `Drug discovery`, `Defense R&D`, `Regulatory dossiers`. Three `color.claims-blue` lines fan upward from the database band to each ontology endpoint — these lines are heavier and brand-colored (vs. the bottom's lighter mist lines) because the top layer is the proprietary value layer. The top eyebrow on the left reads `ENTERPRISE · SUBNET OWNERS · PALANTIR-FOUNDRY PATTERN FOR SCIENCE` — the Palantir-Foundry framing now lives inside the diagram's own description, not as a separate bottom-strip tagline.

Beneath the diagram, anchored at the bottom of the content area, sits **Answer for Simon** — a small `color.claims-blue` UPPERCASE eyebrow, then a 28px italic line: *5-MeO-DMT has an 80% probability to reduce depressive symptoms for >3 months after a single dose.* This is the architecture's concrete output: the buyer from Slide 6, who walked in with a question, now walks out with a calibrated answer.

The visual narrative reads bottom-up exactly as the user described the architecture: open streams (many, free, watchable) → validators (one consolidated graph, gated by API/MCP) → enterprise ontologies (many specialized, high-touch) → one specific answer for one specific buyer.

**Text on Slide:**
- Title (`type.title` 56px, `color.ink`, standard slide-title slot at x=128, y=128): The Product. No eyebrow above the title — the title carries the slide identity alone.

- **Inside the SVG** (viewBox 0 0 1600 480, full content width):
  - Top eyebrow (Inter Medium 14px UPPERCASE 0.14em tracking, `color.graphite`, x=0, y=18): `ENTERPRISE · SUBNET OWNERS · PALANTIR-FOUNDRY PATTERN FOR SCIENCE`
  - Top ontology labels (Inter Medium 22px, `color.ink`, baseline y=80, three across at x=300, 800, 1300): `Drug discovery` / `Defense R&D` / `Regulatory dossiers`. Labels sit **above** their dots (line endpoints) so the diverging lines never cross any label text.
  - Top ontology dots (`color.claims-blue` filled, r=6, at y=104).
  - Diverging lines (Inter `color.claims-blue` stroke 1.5px) from middle band top (y=200) to each dot bottom (y=110) — three lines, one per ontology endpoint.
  - Middle band (rect x=480, y=200, w=640, h=60, `color.parchment` fill, `color.ink` stroke 1.5px, `radius.md`): centered text `Canonical claim-evidence database` (Inter Medium 20px ink).
  - Middle-left eyebrow (Inter Medium 14px UPPERCASE 0.14em, `color.graphite`, x=0, y=237): `VALIDATORS`.
  - Middle-right access tag (Inter Medium 14px UPPERCASE 0.14em, `color.ink`, x=1140, y=237): `API · MCP`.
  - Converging lines (Inter `color.mist` stroke 1px) — twelve lines from each miner dot (y=430) up to a corresponding point on the middle band bottom edge (y=260), fanning so leftmost miners reach the left side of the band and rightmost reach the right side.
  - Bottom miner dots (`color.ink` filled, r=5, at y=430) — twelve dots spaced evenly across the width.
  - Bottom eyebrow (Inter Medium 14px UPPERCASE 0.14em, `color.graphite`, x=0, y=470): `MINER STREAMS`.

- **Answer for Simon block** (below the SVG, anchored at the bottom of the content area):
  - Eyebrow (Inter Medium 14px UPPERCASE 0.14em, `color.claims-blue`): `ANSWER FOR ALEX`
  - Body (Inter Regular Italic 28px, `color.ink`, max-width 1500px, with the compound name *5-MeO-DMT* italicized inline): *5-MeO-DMT has an 80% probability to reduce depressive symptoms for >3 months after a single dose.*

**Key Figures:** 80% (the calibrated probability the architecture produced for Simon's question).

**Layout Notes:** The content area is positioned `top: 200px; bottom: 80px;` (instead of the default `240 / 120`) and uses `display: flex; flex-direction: column; justify-content: space-evenly;`. This places three equal vertical gaps inside the content area — one above the SVG, one between the SVG and the Simon block, and one below the Simon block — which makes the slide read with symmetric vertical rhythm: title → figure → answer → footer, each separated by roughly equal whitespace.

`space-evenly` was chosen over `space-between` because `space-between` puts *all* the slack between the two items (SVG and Simon) and zero slack at the edges of the content area. The result of `space-between` was a slide where the SVG hugged the title (small top gap) and Simon hugged the footer (small bottom gap) but a large empty band sat between them. `space-evenly` distributes the slack across both edges and the middle, producing the symmetric "figure-floats-in-the-middle, answer-anchored-near-bottom" rhythm the user asked for.

Top eyebrow + label spacing inside the SVG was widened from y=58 → y=80 for the ontology label baseline so the `ENTERPRISE · SUBNET OWNERS · PALANTIR-FOUNDRY PATTERN FOR SCIENCE` eyebrow has visible breathing room above the label row. Labels sit *above* the dots (not below) so the diverging lines never cross any label text — a regression we hit in an earlier iteration when labels were beneath the dots.

The earlier two-tier stack design (substrate slab + three ontology cards with fabricated entity-relation sketches) was retired. Two reasons. First, the entity-relation sketches looked fake — `target / compound / pathway` etc. were placeholder schema that didn't carry meaning. Second, the "canonical claim-evidence graph" slab carried no information beyond what its label already said. The bowtie diagram replaces both: the three-layer architecture is encoded structurally (convergence at the waist, divergence at the top), and no fake schema is invented. The Palantir-Foundry framing line was removed from the bottom of the slide and absorbed into the top eyebrow inside the SVG, where it sits beside `Enterprise · Subnet owners` as a descriptor of the top layer.

**Speaker Notes:** "Three layers. The bottom is the open substrate — anyone can run a miner that extracts claim-evidence pairs from the literature, anyone can watch the stream, anyone can verify. The middle is the validators — they consolidate the miner streams into one canonical claim-evidence database. Access to that database is gated through an API and an MCP server; that's where the metered revenue lives. The top is the enterprise layer — we co-develop customer-specific ontologies that turn the canonical graph into decision-grade outputs for one industry at a time. That's the Palantir-Foundry pattern, for science. Bottom is wide and open; middle is one consolidated artifact; top is wide again and customized — many → one → many. And the architecture's job is to produce specific, calibrated answers for specific buyers. Simon asked us how 5-MeO-DMT affects mental-health outcomes. The architecture produced this — an 80% probability of greater than three months of depressive-symptom reduction from a single dose. That's the deliverable. Not a literature review. A decision-grade probability."

---

## Slide 12: Why Bittensor

**Visual Concept:** **Short-list archetype (§4.4)** with three rows. Each row uses the spec-standard 1pt rule (32px wide) as the bullet device — restrained, academic, consistent with every other short-list in the deck. A one-line headline sits next to each rule in Inter Regular 32px `color.ink`, and a supporting callout sits beneath in Inter Light 28px `color.graphite`. Three rows are separated by 40px vertical spacing.

**Text on Slide:**
- Title (`type.title` 56px, `color.ink`): Why Bittensor
- Row 1: **Sharper signal.** Extractor diversity → calibrated confidence per claim.
- Row 2: **Capital efficiency.** Token-funded vs. centrally-funded data curation.
- Row 3: **Open competition compounds quality.** Incentive design.
- Bottom takeaway (Inter Light 28px, `color.graphite`, single line, no bold, matching the Slide 3 takeaway formatting): Data quality is the only thing that matters. Bittensor is where it compounds.

**Key Figures:** none on the slide — the three reasons are the figures.

**Layout Notes:** Items sit in a column occupying cols 1–8 per §4.4. Right cols 9–12 stay empty. Bottom takeaway separated by 96px whitespace from the row block.

**Speaker Notes:** "Three reasons. One — diverse extractors produce sharper signal *and* the calibrated confidence interval a single-model run cannot. Two — token-funded distributed labor is structurally more capital-efficient than payroll-funded extraction; Ridges and Chutes are precedent. Three — miners adopt new models the day they're released because their rewards depend on quality. The incentive structure runs the improvement cycle continuously, in public."

---

## Slide 13: Business model + moat

**Visual Concept:** Symmetric two-column comparison. Left column shows the three-tier revenue stack; right column shows three moat layers stacked compoundingly. Both columns use the **same three grey shades** (lightest at top → darker at bottom) and **the same three ink-stroke left-borders** (4 → 5 → 6 px top-to-bottom) so the rows align horizontally and read as parallel arguments. Black ink text on every box maintains strong contrast against the greys. The earlier blue/copper/ink moat-layer treatment was retired because the asymmetric color palette (greys on left, blues on right) made the two columns read as different objects rather than as two parts of the same compounding argument. A vertical hairline rule sits between the two columns, **trimmed to the height of the box stack** so it doesn't extend past the boxes into the takeaway area beneath.

**Text on Slide:**
- Title (`type.title` 56px, `color.ink`): How we monetize. How we keep it.
- Left column header (Inter Medium 20px, uppercase, `color.graphite`, 0.14em): `REVENUE · THREE TIERS`
  - Block 1 (top, lightest grey `#ECEEF2`, 4px ink left border): **Free.** Researchers, students. Discovery channel.
  - Block 2 (middle grey `#D8DBE0`, 5px ink left border): **Metered API / MCP.** AI companies and R&D teams.
  - Block 3 (bottom, darkest grey `#C0C4CB`, 6px ink left border): **Enterprise.** Custom ontology. Pharma · biotech · defense.
- Right column header (Inter Medium 20px, uppercase, `color.claims-blue`, 0.14em): `MOAT · THREE LAYERS`
  - Layer 1 (top, lightest grey `#ECEEF2`, 4px ink left border): **Uncertainty as signal.** Diverse extractors + gold-data.
  - Layer 2 (middle grey `#D8DBE0`, 5px ink left border): **Data quality.** Miners and validators compete continuously.
  - Layer 3 (bottom, darkest grey `#C0C4CB`, 6px ink left border): **Ontologies.** Switching cost · data-network effect.
- Bottom takeaway (Inter Light 28px, `color.graphite`, centered, single line — same formatting as the Slide 3 / 10 takeaways): Layers 1 and 2 compound automatically. Layer 3 is built one enterprise at a time.

**Layout Notes:** All six boxes share identical `padding: var(--space-lg) var(--space-xl)` (24/32) and `white-space: nowrap`, so each row sits at the same y across both columns and text fits on a single line per box. The grid uses `grid-template-columns: 1fr 1px 1fr` with `gap: var(--space-3xl)` — the 1px middle column is the divider, given `margin-top: 72px` so its top edge starts where the first row of boxes starts (below the column headers) and its bottom ends where the last row of boxes ends. `height: 100%` was removed from `.bm-grid` so the grid shrinks to its content, preventing the divider from extending into the takeaway band below. The content container uses `padding-top: 100px` to push the whole block down enough that the gap title-to-block (~165 stage px) is comparable to the gap block-to-takeaway (~127). Takeaway is anchored at `bottom: 220px` with the standard `.takeaway` class — moved up from the default 130 to give it more presence and to keep clear separation between the divider's end and the takeaway's top.

The earlier "blocks ascend in height" treatment on the revenue side was dropped along with the moat-color treatment on the right — uniform box height is what makes the symmetric horizontal alignment readable. The shade-and-border progression (light/4 → medium/5 → dark/6) replaces the height progression as the visual signal that "compounding density increases as you go down the stack."

**Speaker Notes:** "Three revenue tiers — free for discovery, metered API for self-serve, enterprise for retention. Three moat layers — uncertainty as signal, miner-validator quality competition, customer ontologies. The first two compound automatically. The third is built one enterprise at a time — see Slide 9. High-touch, high-switching-cost, high-retention."

---

## Slide 14: Roadmap

**Visual Concept:** Roadmap archetype (§4.11) — single horizontal 1pt `color.ink` rule across the content area, with three quarter-grouped milestone columns. Each phase has 3 milestones beneath the time axis and a small go/no-go badge below the milestones in `color.copper`. Phase boundaries marked by 2pt vertical ticks in ink.

**Text on Slide:**
- Title (`type.title` 56px, `color.ink`): Roadmap.
- Horizontal time axis (y=440), quarter codes per §4.11 (Inter Medium UPPERCASE 18px, 0.14em tracking, `color.graphite`): `Q2 26` ━━━━━━ `Q3 26 — Q4 26` ━━━━━━ `2027+`
- Phase 1 column (under Q2 26): **Centralized prototype**
  - Build customer solution in-house
  - First paid R&D pilot.
  - Beat client's internal baseline
  - Pill (copper): *Signed pilot + benchmark win*
- Phase 2 column (under Q3 26 → Q4 26): **Subnet launch**
  - Register Claims subnet on Bittensor
  - Open-source miner & validator reference
  - API + MCP integrations
  - Pill (copper): *50+ miners · 1M+ claims · first external API*
- Phase 3 column (under 2027+): **Platform**
  - Scale beyond biomedicine
  - Customer-specific ontologies
  - Token buyback-and-burn live
  - Pill (copper): *Revenue + customer milestones*
- No bottom takeaway — the three phase pills carry the rhythm; the earlier `By Q4: subnet live. By 2027: enterprise customers compounding.` line was removed as redundant with the timeline + pills.

**Key Figures:** 50+ miners · 1M+ claims (Phase 2 pill).

**Layout Notes:** Milestones use 8px `color.claims-blue` filled-dot bullets per spec §4.11. Phase pills rendered as small pill-shaped badges in `color.copper` with white type, sitting below each phase column. The literal word `Gate:` was dropped from the pill labels — the copper pill styling makes the gate role visually obvious without the prefix. Phase headers in Inter Medium 28px.

**Speaker Notes:** "Three phases. Phase one is centralized — we de-risk the product before we ever touch the subnet. Phase two is the subnet launch, gated on real coverage and external integrations. Phase three is the platform — buyback engaged, customer ontologies compounding. The mechanism design risk is contained to phase two, and phase two doesn't ship until phase one wins."

---

## Slide 15: Close — Frankly, we're skeptical

**Visual Concept:** Per spec v5 §4.12. Full-bleed hero render from the sibling-not-twin Claims artwork piece: the inverted-tetrahedron platform with the dome-and-DNA-helix on top, suspended in dramatic clouds with a reflective water surface beneath. Source file: `Logos and pictures/finish-art.jpg`. A single radial pool of darkness anchored at the lower-left (ellipse ~55% × 45% at 20% / 78%, `rgba(11,18,32,0.70)` at center fading to transparent at 100%) gives the contact block contrast against the cloud. The tetrahedron, dome, and right half of the render stay completely clear.

**Text on Slide:**
- **Closing quote card** anchored to the upper-left (`top: 90px`, `left: 160px`, `max-width: 1280px`). Reuses the §4.10 display quote card archetype but stripped of the parchment fill and padding — **fully transparent background, zero padding** — so the qbody text starts at `left: 160px` exactly and column-aligns with the contact block below. The opening quotation mark (Inter Light, 120px, `color.claims-blue`) sits flush above the body text as a normal block element (not absolutely positioned), 12px of breathing space between qmark baseline and body. Body text (Inter Regular, 44px, `color.ink`) — black so it reads against the pale sky in the upper-left of the artwork. A faint 1px white text-shadow at 35% opacity prevents the type from disappearing into any locally-bright cloud highlight. Two lines with a forced break after the period:
  > "Frankly, we're skeptical that 42 is the answer.<br>Claims will know."
- **Contact block** anchored to the lower-left (`bottom: 100px`, `left: 160px`) — left-aligned with the quote card above:
  - **Name** (Inter Light, 32px, `color.paper`): `Prof. Dr. Philipp Koellinger`
  - **Email**, immediately below name (Inter Light, 32px, `color.mist`): `philipp@desci.com`

**Key Figures:** none — the slide is a closing line + contact card.

**Layout Notes:** Quote card occupies the upper-left quadrant of the slide, sitting in the empty sky above the cloud line and well clear of the floating dome/tetrahedron arc in the center of the artwork. Contact block sits in the lower-left. Both share the `left: 160px` gutter so the qbody text and the contact name share a single hard left edge — the eye drops in a straight column from quote to name. No CLAIMS wordmark, no left-edge ink band — the image is the lockup, same logic as the cover. No page numeral. No footer tab. Hitchhiker's Guide reference in the quote is deliberate — the joke lands with technical investors and reads as confident humility rather than salesmanship.

**Speaker Notes:** "That's the pitch. Same team that took scientific reference hallucination from sixty percent to zero. Now building the layer underneath. Frankly, we're skeptical that the answer is 42 — but Claims will know. What we need: the subnet itself, early validator and miner partners, and introductions to Bittensor-aware capital. My contact is on the slide. Questions."

---

## Production notes for the HTML build

**Slide count:** 15 visual slides. Strategic splits from the original storyline:
- Slide 2 → 2+3 for the prize/proof beat separation (the $3T market beat lands on Slide 2; the 0% vs. 62% hallucination chart lands on Slide 3).
- The storyline's buyer narrative is split across Slides 6 + 8 with Market interleaved at Slide 7.
- The miner–validator mechanism is extracted into Slide 9 (Inner Loop) so the product architecture (Slide 11) doesn't have to carry both the mechanism and the architecture story in one frame.
- The **reward function** is extracted into its own Slide 10 (Incentive Mechanism) — this is the mathematical articulation of the Inner Loop, sitting between the loop diagram (9) and the bowtie architecture (11). It's the slide that buys the technical credibility with Bittensor-aware investors.

**Archetype usage:**
- **Pure hero-stat (§4.3):** Slide 3 (chart-as-hero — the 0% bar IS the hero).
- **Metric tile row (§4.5):** Slide 2 (three equal tiles, $3T+ / 300M+ / 0%, vertically centered) and Slide 7 (two large tiles with a converging-arrow connector — explicitly the metric-tile archetype, not the hero-stat archetype, since the spec forbids paired heroes).
- **Display quote card (§4.10 display variant):** Slide 6.
- **Short-list (§4.4):** Slide 12 (three rows, 1pt rules as bullets per spec — not icons).
- **Roadmap (§4.11):** Slide 14 (quarter codes, no months).
- **Closing (§4.12):** Slide 15 (lower-left contact + upper-left transparent quote card, finish-art.jpg, no manifesto).
- **Custom cycle archetype:** Slide 9 (Inner loop — two half-circle arrows forming a clockwise miner–validator cycle, true circular SVG arcs).
- **Custom math archetype:** Slide 10 (Incentive mechanism — KaTeX-rendered LaTeX reward function on the left, variable legend on the right; first deck to require a math rendering dependency).
- **Custom architecture archetype:** Slide 11 (bowtie/hourglass — many miners → one canonical DB → many ontologies → one answer).

**Centerpiece slide:** Slide 11 (The Product) — the bowtie architecture. Preceded by a three-slide technical buildup: Slide 8 (Computable confidence — WHAT the system measures: extraction + source uncertainty), Slide 9 (Inner Loop — HOW it measures it: miner–validator cycle), Slide 10 (Incentive Mechanism — HOW it's PAID FOR: reward function with recursive gates). The three preparatory slides each carry one piece of the technical story so Slide 11 can be read at architecture level without back-explanation.

**Visual-anchor compliance:** Every content slide has a visual anchor per §0 Rule 5 — chart, hero numeral, diagram, comparison structure, metric tiles, cycle arcs, equation, bowtie architecture, or two type-driven lead statements. No slide is text-only except Slide 1 (cover) and Slide 15 (close), which use the full-bleed render. Slide 8 (Computable confidence) is type-driven: its two 56px Light lead statements ARE the visual anchor. Slide 10 (Incentive mechanism) is math-driven: the KaTeX-rendered reward function IS the visual anchor.

**Color discipline:** `color.copper` is reserved for emphasis flags — the 0% tile (Slide 2), gate badges (Slide 14). `color.moss` only for positive deltas (growth tag on Slide 7, the 0% baseline rule on Slide 3). `color.signal` is currently unused after the RAG vs. Claims Graph slide was removed — reserved for negative variance / risk flags if a later slide needs one. `color.atmosphere` carries the muted-competitor treatment on Slide 3 and the bottom moat layer on Slide 13. `color.claims-blue` is the primary value-layer accent: in-body citation superscripts, the bowtie's enterprise-side lines (Slide 11), and the in-body Answer-for-Simon eyebrow.

**External dependencies (added during this session):**
- **KaTeX 0.16.9** loaded from `cdn.jsdelivr.net` with SRI hashes — used to render the reward function on Slide 10. Auto-render scans for `\[...\]` and `\(...\)` delimiters on `DOMContentLoaded` and replaces them with rendered math. Loads ~28KB of CSS and ~280KB of JS (gzipped). Same connectivity assumption as the already-loaded Inter webfont from Google Fonts. For air-gapped presentation, both dependencies would need to be inlined.

**Typography:** Inter only per spec v5 §2.2. Hero numerals use Inter Light at the new v3 sizes (`type.display-xl` 220px). All eyebrow / metadata labels use Inter Medium UPPERCASE tracked 0.14em. All tabular figures use `font-variant-numeric: tabular-nums`.

**Title voice:** Per spec v5 §6, narrative title voice is permitted for the pitch register. Several slides carry sentence-style titles (`AI ate the internet. Science is what it can't digest.`, `Frontier models hallucinate science.`, `How we monetize. How we keep it.`) — each earns its place as the speaker's opening line for that slide.

**Print pass:** Cover and close render at 15% opacity in print mode per §8. Left-edge band collapses to 1.5pt rule on content slides only (cover and close already have no band). Three-bar hallucination chart on Slide 3 prints cleanly — Ink and Atmosphere are distinguishable in greyscale. Slide 9's miner–validator cycle arcs print as crisp ink strokes against white. Slide 10's KaTeX-rendered equation prints natively as long as KaTeX has loaded before "Save as PDF" — verify in Chrome's print preview that the math renders before saving. Slide 11's bowtie prints well — convergence-at-the-waist structure is preserved; `color.claims-blue` ontology lines reduce to mid-grey but stay visually heavier than the `color.mist` miner lines so the bottom-vs-top contrast survives.

**Storyline elements deliberately omitted from slides (per Information Asymmetry Strategy):** Full mechanism design, customer ontology methodology, identities of the three R&D prospects, full token economics, M&A workstream, the internal "compute cost is not the argument" admission. All sit in Q&A or the data room.
