# Deck Design Spec — Claims Subnet Pitch Deck

**Version** 5 · May 2026
**Owner** Philipp Koellinger
**Status** Draft for review
**Audience** Investors and the Bittensor Proof of Talk audience (Jun 2026)
**Register** Pitch deck · **minimal text · maximum visual impact**. One slide, one idea. Large readable typography. Generous whitespace. Dense bullet lists are retired.

**Changelog**
- **v5** — Citation system tightened. Asterisk pattern deprecated entirely — every cited source uses a Nature numbered superscript regardless of count, so the convention is consistent across the deck. Added the en-dash range form (`¹⁻⁴`) for three or more *consecutive* sources at one citation point; comma-separated for non-consecutive (`¹,³,⁵`). Codified the scientific-article and web/blog citation formats in §5. Updated reference-strip example to use the proper journal-article format with italicized journal name, en-dash page range, and full DOI URL hyperlinked in `color.claims-blue`.
- **v4** — Removed the hero-with-supporting-tiles variant from §4.3; no current slide uses it, and the variant was bending the "one slide, one idea" rule. Slides that previously needed it now use the standard §4.5 metric tile row. Made the cover footer-right eyebrow optional rather than required — the title and footer-left tagline alone carry the identity when the eyebrow would otherwise compete with the dome render.
- **v3** — Added optional subtitle slot to the cover archetype to accommodate a multi-line positioning statement. Permitted a hero-with-supporting-tiles variant on §4.3 hero stat. Split §4.10 quote card into two variants (display / grid). Added pitch-register exception to the title-voice rule in §6.
- **v2** — Locked Inter as the only typeface (no Source Serif 4, no JetBrains Mono). Renamed `color.desci-blue` → `color.claims-blue`. Reduced `type.display-xl` 280 → 220px and `type.display` 252 → 200px. Retargeted from board-deck to investor-pitch register. Removed CLAIMS wordmark from cover and closing.

---

## 0. Five non-negotiable layout rules

These rules override anything else in the spec. Check every slide against all five before declaring it done.

**1. Line breaks go after a period or comma — never mid-sentence.** If a sentence wraps, it wraps at a natural clause boundary. No break between a noun and its verb, between a modifier and the word it modifies, or after a preposition. When forcing a break, use `<br>` only after punctuation. Always verify the natural CSS wrap doesn't split a clause — if it does, widen the container or split into two explicit lines.

**2. The presenter should never have to read verbatim from the slide.** Slides carry headlines, data, and structure. Details and narrative live in the presenter's voice. If a slide contains a full sentence the presenter would say anyway, cut the slide or cut the sentence. Bullet lists of four-or-five full phrases are a red flag — the presenter is being written a script, not a slide.

**3. Use the whole slide. Leave plenty of breathing space.** Never squeeze content into the upper-left corner. No artificial narrow columns that force wrapping when the right half of the slide is empty. Vertically center short content. Push takeaways lower to create space between them and the primary visual. When in doubt between "tighter" and "more spacious," choose more spacious.

**4. No content redundancy — within a slide or across slides.** A line that summarizes what just appeared is redundant. A second slide that restates the first's conclusion is redundant. Cut, don't double.

**5. No text-only content slides.** Section dividers are the only exception. Every content slide needs a visual anchor — a hero number, a chart, a metric tile row, a diagram, a logo grid, a before/after structure. A slide that is only a title plus a bullet list is a memo page, not a slide.

---

## 2. Design tokens

### 2.1 Color

Restrained palette. The cloud-strip's muted blue-grey becomes a specified brand blue. Black becomes a cooler near-black. Copper and moss are warm academic accents — not marketing primary colors.

| Token | Hex | Usage |
|---|---|---|
| `color.ink` | `#0B1220` | Primary text, logo, dark stage. Cooler than pure black — carries a hint of indigo. |
| `color.paper` | `#FFFFFF` | Default slide background. |
| `color.parchment` | `#F7F5F0` | Warm alt background. Section dividers, appendix. Carries more warmth than Fog. |
| `color.fog` | `#E7EAEF` | Table row fill, card backgrounds, subtle surfaces. |
| `color.graphite` | `#4A5160` | Secondary text, axis labels, captions. |
| `color.mist` | `#B5BAC4` | Tertiary text, disabled, gridlines. |
| `color.claims-blue` | `#2D4F8E` | Primary brand accent. Left-edge band, active chart series, data emphasis. |
| `color.atmosphere` | `#8FA4C4` | Secondary accent. Muted blue, stands down. Chart series 4, inactive states. |
| `color.copper` | `#B87333` | Warm accent. Positive/upside data, emphasis callouts. Reads academic, not marketing. |
| `color.moss` | `#3C6E47` | Positive financial data (revenue, runway extension), growth. |
| `color.signal` | `#C8451A` | Reserved for negative variance, risk flags, burn. Use sparingly. |

**Chart categorical sequence** (six-step, always in this order):
`ink → claims-blue → copper → atmosphere → moss → graphite`

Rationale: ordered, restrained, no rainbow. Works on paper and projector. Unambiguous print greyscale.

### 2.2 Typography

**Typeface — one family, full stop**

| Role | Family | Fallback stack | Weights used |
|---|---|---|---|
| Every text element | Inter | system-ui, -apple-system, Segoe UI, Arial | 300 Light · 400 Regular · 500 Medium · 600 SemiBold |

No serif. No monospace. No secondary family of any kind. Hierarchy comes from **size, weight, color, letter-spacing, and text-transform** — never from swapping typefaces.

For tabular alignment on numbers (page counters, metric values, axis labels), use `font-variant-numeric: tabular-nums` on Inter. Keeps columns aligned without switching families.

For labels that need a technical / metadata feel (`DECISION NEEDED`, `01 · PROBLEM · JUN 2026`), use Inter Medium at small size with `text-transform: uppercase` and `letter-spacing: 0.12em–0.16em`. Reads distinct without introducing a second typeface.

Why this rule: a pitch deck with three families reads as indecisive. One family, used with discipline across weight and scale, reads as intentional.

**Type scale** (16:9 slide, nominal 1920 × 1080 pixels. All sizes are native-px values. All in Inter.)

| Token | Size | Weight | Tracking | Usage |
|---|---|---|---|---|
| `type.display-xl` | 220px | Light (300) | -0.035em · tabular-nums | Hero-stat numeral |
| `type.display` | 200px | Light (300) | -0.02em · tabular-nums | Section divider numeral |
| `type.title-xl` | 112px | Light (300) | -0.015em | Cover title |
| `type.title-lg` | 84px | Light (300) | -0.01em | Section divider title, decision-slide question |
| `type.title` | 56px | Regular (400) | -0.005em | Standard slide title |
| `type.subtitle` | 36px | Regular (400) | 0 | Subtitle, chart titles |
| `type.body` | 32px | Regular (400) | 0 | Standard on-slide text |
| `type.body-sm` | 24px | Regular (400) | 0 | Secondary label |
| `type.meta` | 18–22px | Medium (500) | 0.14em · UPPERCASE | Footer section tab, cover eyebrow, decision eyebrow |
| `type.counter` | 18px | Regular (400) | 0.08em · tabular-nums | Page numerals, axis labels |
| `type.hero-numeral` | 96–180px | Light (300) | -0.025em · tabular-nums | Metric-tile values, hero-stat values |

**Why this scale.** On a laptop sharing slides over Zoom at half-screen (~720px viewport height), the 56px title renders at ~37px and the 32px body at ~21px. Both comfortably readable without squinting. At a projector or a 27-inch monitor, the type is commanding without being oversized. At A4 print, body text lands around 14pt — standard reading size.

**Pattern rules**

- **One typeface only: Inter.** For everything. Titles, body, hero numerals, section-divider numerals, eyebrow labels, footer metadata, page numerals, chart axis labels, tabular figures, UI chrome. If you are about to set `font-family` to anything else, stop — use weight, size, or letter-spacing instead.
- Italicize product names: `*SciWeave* — Growth`, `*Claims* — Roadmap`. Use Inter Italic, still one typeface.
- Titles are sentence case. Never Title Case. Never ALL CAPS. (One exception: metadata labels like `DECISION NEEDED` and `01 · PROBLEM · JUN 2026` — Inter Medium, UPPERCASE, 0.14em letter-spacing. Small and quiet.)
- Body text never goes below 18pt rendered.
- Numerical values get visual weight from **size**, not typeface. A $620K metric is huge because it's set in Inter Light at 96–180px, not because it's in a different font.
- Mono-like alignment (page counters, table numerals, axis labels) uses `font-variant-numeric: tabular-nums` on Inter. Keeps columns lined up without introducing a monospace family.

### 2.3 Spacing

Scale in pt (slide-native):

| Token | Value |
|---|---|
| `space.xs` | 4 |
| `space.sm` | 8 |
| `space.md` | 16 |
| `space.lg` | 24 |
| `space.xl` | 32 |
| `space.2xl` | 48 |
| `space.3xl` | 64 |
| `space.4xl` | 96 |

**Slide grid**

- Stage: 1920 × 1080 (16:9).
- Left edge band: 64px wide (constant). Content begins at x = 128px.
- Right safe margin: 80px.
- Top safe margin: 72px.
- Bottom safe margin: 56px (wordmark + numeral live inside this band).
- Content column: 12-col grid across the remaining 1712px, 24px gutters. Column width ≈ 119px. Rarely need the full 12 — most content uses 6, 8, or 10 cols.

### 2.4 Lines and radii

| Token | Value | Usage |
|---|---|---|
| `stroke.hairline` | 0.5pt, `color.mist` | Chart axis baselines, table rules |
| `stroke.rule` | 1pt, `color.graphite` | Section rules, emphasis dividers |
| `stroke.heavy` | 2pt, `color.ink` | Top of table header, underline for hero-metric |
| `radius.sm` | 2pt | Pills, small chips |
| `radius.md` | 4pt | Metric tiles, callout boxes |
| `radius.lg` | 8pt | Quote cards |

No shadows. No gradients except the one noted in §4.1. No glass, no blur. This is an investor pitch deck.

---

## 3. Slide frame (canvas)

### 3.1 The left-edge band (signature device)

**Dimensions**: 64px wide at 1920 native, full slide height (1080px), fixed on every content slide.

**Fill**: Solid `color.ink` (#0B1220). Flat. No imagery. No text on the band. Suppressed on the cover and closing slides (the hero render is the band on those).

### 3.2 Persistent elements (all content slides — excludes cover, closing, and section dividers)

| Element | Position | Spec |
|---|---|---|
| Slide title | x=128, y=128 | `type.title`, `color.ink`, left-aligned |
| Content area | below title, 64px gap | Grid-aligned |
| Section tab (footer, left) | x=128, y=1020 | `type.meta`, `color.graphite`. Format: `02 · TRACTION · JUN 2026` |
| Page numeral | centered, y=1024 | `type.counter`, `color.mist`. Format: `07 / 13` |
| CLAIMS wordmark | x=1840, y=1024 anchor right | Inter Medium 22px, letter-spacing 0.16em, UPPERCASE, `color.ink` |

The section tab carries the date metadata in the footer. It always reads cleanly and prints without issue.

### 3.3 Safe area rule

No content inside the left 64px band. No content below y=1000 except the persistent footer row. No content within 80px of the right edge. The stage is large; use it deliberately.

---

## 4. Slide archetypes

### 4.1 Cover

**Purpose** First impression. Sets register. Carries the single emotional beat of the deck.

**Layout**
- Full-bleed hero render as the background: the Claims subnet brand artwork — geodesic dome on a floating tetrahedron platform, suspended in clouds. Source file: `Logos and pictures/cover-art.jpg`.
- Overlay strategy: keep the entire upper image (dome, sky, clouds above the platform) completely clear. All text lives in the bottom band, so a single strong linear gradient handles contrast — transparent at 50%, `rgba(11,18,32,0.45)` at 72%, `rgba(11,18,32,0.85)` at 100%. No second gradient is needed because no text sits at the top anymore.
- All text is anchored to the bottom of the slide (`bottom: 100px`), inside a single block that runs `left: 160px` to `right: 160px`. The block holds **two required slots** plus **two optional slots**:
  - **Title at the top of the block** (Inter Light, 112px / `type.title-xl`, `color.paper`). Required. Example: `Claims`. Sits in the heavily-overlaid bottom band where white text holds maximum contrast against the dark cloud underside of the image.
  - **Optional subtitle, directly beneath the title** (Inter Light Italic, 36px / `type.subtitle` modified, `color.paper` at 90% opacity). Margin-top `space.lg`. Use this slot when the cover carries a positioning statement that doesn't fit on a single line in the footer row. Example: `The canonical claim-evidence graph for science.` Omit the slot entirely on covers where the title alone carries the identity (no italic, no placeholder).
  - **Footer row at the bottom of the block** (single line, baseline-aligned with `display: flex; align-items: baseline; justify-content: space-between`). Required at least on the left:
    - Footer-left, aligned x with the title (Inter Regular, 22px, `color.mist`). Carries either a tagline (when the optional subtitle is in use, example: `A Bittensor subnet. By the team that built SciWeave.`) or a date (when the optional subtitle is omitted, example: `Investor pitch · June 2026`).
    - **Footer-right is optional** (`type.meta`, `color.mist`). May carry a venue/eyebrow when one helps date or contextualize the deck (example: `BITTENSOR · SUBNET PROPOSAL · 2026`). Omit when the title and footer-left tagline alone carry the identity — a second mark in the corner competes with the dome render. The Claims cover ships without it.
  - When present, the eyebrow lives in the footer row, not at the top of the slide. Top-of-slide eyebrows wash out against the bright sky region of the image and lose all contrast.
- **No CLAIMS wordmark on the cover.** The image and title are the lockup. A second mark in the corner competes for attention with the hero render.
- No page numeral on cover.
- Left-edge band is suppressed on the cover (the image is the band).

**Do** Use the real render. Keep the dome and upper image visually clear — the overlay only darkens the bottom band where text actually sits. Use the optional subtitle slot when the cover needs to carry a thesis statement beyond the title.
**Don't** Place any text on the upper half of the image — even short uppercase metadata washes out against the bright sky. Center the title vertically — it lands on the bright dome interior and disappears. Caption the image. Add the CLAIMS wordmark in the corner. Use both the subtitle slot AND a long footer-left tagline if either alone would carry the work — pick one.

---

### 4.2 Section divider

**Purpose** Mark a top-level agenda transition. Quiet, parchment-warm, breathing room.

**Layout**
- Background: `color.parchment`.
- Eyebrow at x=160, y=320: `PART 02` (`type.meta`, `color.graphite`).
- Numeral at x=160, vertically centered around y=540: `02` (`type.display` — Inter Light 200px, `color.ink`). Sized to leave breathing room around the title beneath it.
- Title at x=160, y=720: `Traction.` (`type.title-lg`, `color.graphite`).
- CLAIMS wordmark bottom-right.

**Do** Use one divider per top-level agenda block. Three to five total in a 20-slide deck.
**Don't** Use a divider for every subsection. They become noise instead of punctuation.

---

### 4.3 Hero stat (primary archetype)

**Purpose** When one number IS the slide. Use for TAM, runway, user count, or any major number the audience should hear as a single beat.

**Layout**
- Title at standard position (small, secondary — sets context, doesn't compete).
- Optional contextual line above the numeral, 32px gap: `type.body-sm` Medium UPPERCASE tracking 0.14em, `color.graphite`. Example: `VS. $732K AT DECEMBER CLOSE`. Carries the comparison without competing with the numeral.
- Hero numeral anchored center-left, starting at x=160, vertically centered around y=580: single figure in **Inter Light at 220px** (`type.display-xl`). Examples: `$620K`, `Q1 2027`, `18.4K`. The numeral is large enough to dominate the slide but deliberately sized to leave generous breathing room above the context line and below the support line.
- Supporting line directly below the numeral, 48px gap: Inter Light at 48px, `color.graphite`. **Container max-width must be wide enough that no clause wraps mid-sentence.** Split into two explicit lines when needed (each as a separate `<span class="line">` block) rather than relying on natural CSS wrap, which will eventually split a noun from its verb.
- Right half of the slide intentionally empty. The whitespace is the message.

**Do** Use this archetype more than any other. When in doubt between a dense bullet slide and three hero-stat slides, choose three hero-stat slides.
**Don't** Pair two equal-weight hero numerals on one slide. Add a row of supporting tiles to "amplify" the hero — that pattern was tried in v3 and removed in v4; it bent the "one slide, one idea" rule and the supporting figures inevitably read as independent metrics. If multiple related numbers need to share a slide, use the metric tile row (§4.5) instead, with no hero numeral on top.

---

### 4.4 Short-list

**Purpose** When the audience needs a short enumeration — 3 to 5 short phrases.

**Layout**
- Title at standard position.
- Maximum 5 items, each a single short phrase (6–10 words). No sub-bullets. No nested structure. If nesting is needed, split across two slides.
- Each item: 1pt rule (32px wide) as the bullet, Inter Regular 32px body text, 40px vertical spacing between items.
- Items sit in a column occupying col 1–8 of the grid. Right 4 cols stay empty.
- The list block is vertically centered in the content area — never glued to the top.
- If an item needs emphasis: italicize a product name, OR set the line in `color.copper` for an attention beat.
- **Micro-stats are allowed only when (a) the number is meaningful in context, (b) it appears in the same column position on every item that has one, and (c) the units are unambiguous.** A bare `73%` floating mid-line with no comparison is not meaningful — drop it.

**Do** Keep phrases short enough that the audience reading at a glance gets the point.
**Don't** Write complete sentences. Use sub-bullets. Exceed 5 items. Drop solo micro-stats with no comparison.

---

### 4.5 Metric tile row

**Purpose** Hero numerals up front. Three or four side-by-side.

**Layout**
- Title at standard position.
- A row of 3 or 4 tiles. Each tile = 2pt rule at top (color.ink) + numeral + label + delta.
- Tile structure, top to bottom:
  - 2pt rule, color.ink, full tile width
  - `space.md` gap
  - Hero numeral: `$354,678` (Inter Light, 96px, `color.ink`, tabular-nums). Use thousands separator. Abbreviate at 6 figures: `$732K`, `13.8K`.
  - `space.sm` gap
  - Label: `Revenue, Jan–Nov 2025` (Inter Regular, 22px, `color.graphite`)
  - `space.xs` gap
  - Delta: `+42% vs. Sept forecast` (Inter Medium, 20px, `color.moss` for positive, `color.signal` for negative, `color.graphite` for neutral). Only if a meaningful comparison exists.

**Do** Three tiles if the numbers deserve equal weight. Four maximum.
**Don't** Use tiles for vanity metrics. Investor tiles are burn, runway, revenue, users, ARR — not "impressions."

### 4.6 Table (research-paper style)

**Purpose** Comparisons, allocations, competitor reviews.

**Layout**
- No background fill on header. No fill on rows.
- Header row: Inter Medium 22px, color.ink. 2pt rule, color.ink, below header.
- Body rows: Inter Regular 22px, color.ink. 0.5pt rule, color.mist, between rows.
- Final 1pt rule, color.ink, below last row.
- Numeric columns right-aligned, Inter Regular with `font-variant-numeric: tabular-nums`, for clean decimal alignment.
- Text columns left-aligned.
- If emphasis is needed, the entire row gets `color.fog` fill — never a colored text treatment.

**Do** Right-align numbers. Use tabular-nums. One subtle emphasis row max.
**Don't** Use PowerPoint's Blue-Accent-1 ribbon. It's the single biggest "this is a 2019 deck" tell.

### 4.7 Chart — bar

**Purpose** Growth over time, discrete comparisons.

**Layout**
- Chart title: `type.subtitle`, color.ink, top of chart area.
- Y-axis labels: Inter Regular 18px, `color.graphite`, tabular-nums.
- X-axis labels: Inter Medium 18px UPPERCASE tracking 0.14em, `color.graphite`, centered.
- Gridlines: hairline rules, color.mist, horizontal only.
- Bar width: 60% of category width.
- Series 1: `color.ink`. Series 2: `color.claims-blue`.
- Value labels above bars only if under 6 bars; otherwise read from gridlines.
- Legend: horizontal, below chart, 16px swatches with `type.meta` labels.

**Do** Ink + Claims Blue for two-series comparisons.
**Don't** Use 3D effects. Gradient fills. Drop shadows.

### 4.8 Chart — line

**Purpose** Retention curves, multi-series trends.

**Layout**
- Stroke weight: 2pt. Never thinner.
- Color sequence per §2.1 categorical order.
- Data points: 4pt filled circles at each measurement, matching line color.
- Y-axis: percentage or value labels at 4 tick marks max.
- Legend positioned inline at end of each line where space allows; else below chart.
- No area fills under lines.

**Do** Four series maximum in one chart. More = two charts.
**Don't** Embed dashboard screenshots. Rebuild charts in the deck's own system.

### 4.9 Chart — pie / donut

**Purpose** Compositional share (user segments, token allocation, payroll split).

**Layout**
- Use donut, not pie. 40% center hole. The hole carries a total in the center (e.g., `5,511` MAU).
- Six slices max. Aggregate anything below 4% into an "Other" slice.
- Slice order: largest clockwise from 12 o'clock.
- Labels: outside the donut with leader lines, color.graphite. Never inside slices.
- Colors: categorical sequence, muted by 15% lightness for donut rendering.

**Do** Donut-with-total-in-center. The total is the hero; the slices are context.
**Don't** Explode slices. Use more than six slices. Show percentages without showing the total.

### 4.10 Quote card

**Purpose** Qualitative evidence, handled with gravity. Two variants — pick by the slide's job.

**Variant A — Grid (multiple testimonials)**

When the slide carries multiple quotes as evidence, render each as a card in a 2×2 or 2×1 grid. The quote is one piece of evidence among several; it's sized to read clearly without dominating.

- Card: `color.parchment` fill, `radius.lg`, `space.xl` padding.
- Opening quote mark: Inter Light at 96px, `color.claims-blue`, top-left of card, decorative.
- Quote body: Inter Regular 24px, color.ink, line-height 1.5. No quotation marks in the text itself (the decorative mark handles it).
- Attribution: Inter Medium 18px, color.graphite. Format: `— First name, role/field, institution` (`— Maya, postdoc, genomics, ETH`). Anonymize if needed but keep the role.
- Max 4 cards in a 2×2 grid, or 2 cards side-by-side with more room each.

**Variant B — Display (single hero quote)**

When the slide IS the quote — a buyer's question, a customer's verdict, a moment that builds tension — render one card at hero scale. The quote dominates the slide and earns the room's attention.

- Card: same `color.parchment` fill, `radius.lg`, generous `space.2xl`–`space.3xl` padding.
- Opening quote mark: Inter Light at 120px, `color.claims-blue`, top-left of card, decorative.
- Quote body: Inter Regular 44px, color.ink, line-height 1.4. Sized as a hero element, not as testimonial evidence.
- Card occupies cols 1–8; right cols 9–12 stay empty. Vertically centered around y=480.
- Optional context strip below the card (Inter Regular 24px, color.graphite, constrained to the same column span as the card): one to three short lines describing who is speaking and why their question/statement matters. No attribution line — the context strip is the attribution.
- Use the display variant only when the quote earns the entire slide. If two of these stack in a row, you've over-used it.

**Do** Preserve line breaks from the original if meaningful. Use sentence-case attribution (grid) or contextual framing (display). Italicize product names inside the quote if mentioned (`Through which mechanisms does *5-MeO-DMT*…`).
**Don't** Bold random phrases inside the quote. Fabricate quotes. Ship a quote slide without real attribution (grid) or without clear context (display). Mix the two variants on adjacent slides — pick one for the moment.

### 4.11 Roadmap / timeline

**Purpose** Quarter-keyed plans.

**Layout**
- Horizontal time axis: one 1pt rule, color.ink, across the content area.
- Quarter markers: 12pt vertical ticks above the rule, labeled `Q3 26`, `Q4 26`, `Q1 27`, `Q2 27` in Inter Medium UPPERCASE 18px tracking 0.14em.
- Under each quarter, a column of 3–5 items.
- Each item: a filled `color.claims-blue` dot (8px) as bullet, followed by Inter Regular 22px body text.
- Use `color.copper` for cross-team items, `color.moss` for shipped/completed.
- Legend at bottom-right if multiple colors used.

**Do** Anchor to quarters. Keep one roadmap slide per product area when needed.
**Don't** Mix quarters and months. Use arrows or Gantt bars (too much visual noise for pitch density).

---

### 4.12 Closing slide

**Purpose** Close the loop. Return to the emotional beat from the cover with a sibling-not-twin image, and present the contact information at human scale — name and email together, treated as a business card embedded in the render.

**Layout**
- Full-bleed hero render from a different but stylistically matched piece of the Claims artwork family: an inverted-tetrahedron platform with the dome-and-DNA-helix on top, suspended in dramatic clouds with a reflective water surface beneath. Source file: `Logos and pictures/finish-art.jpg`.
- Overlay strategy: a single radial pool of darkness anchored at the lower-left where the text block sits. The tetrahedron + dome (upper-center) and the right side of the image stay completely clear.
  - Pool: radial gradient (ellipse ~55% × 45% at 20% / 78%) — `rgba(11,18,32,0.70)` at center, `rgba(11,18,32,0.25)` at 65%, transparent at 100%.
- Text — three lines, all left-aligned at x=160, the entire block anchored at `bottom: 100px` so it occupies the lower-left third of the slide:
  - **Headline** (~y=820–930 baseline): `Let's talk.` (Inter Light, 112px / `type.title-xl`, `color.paper`). Same size, weight, and tracking as the cover title — the two slides bookend each other typographically.
  - **Name** (32px below headline, 32px Inter Light, `color.paper`): `Prof. Dr. Philipp Koellinger`.
  - **Email** (immediately below name, 32px Inter Light, `color.mist`): `philipp@desci.com`. The colour drop from paper to mist gives the email a secondary read without forcing a font-size or weight change — the address is information, the name is identity.
- **No CLAIMS wordmark on the closing slide.** Same logic as the cover — the image is the lockup.
- No page numeral. No footer tab.
- Left-edge band suppressed (the image is the band).

**Do** Use the second piece of artwork (the inverted-tetrahedron / dome / water render) so the bookend reads as a sequel, not a duplicate. Keep the contact block on the lower-left, in the dark cloud pool — that region offers the highest contrast for white text in this image.
**Don't** Center the text. Add `Contact.`, `Questions?`, `Q&A`, or any decorative label. Drop the name and let the email stand alone — at the closing the presenter has a face and a title, and the slide should reflect that. Add the CLAIMS wordmark in the corner.

---

## 5. Reference and footnote system

A pitch deck that cites real research should look like it does.

**In-body citation — numbered (any number of sources)**: Superscript numeral in Inter, 60% size, `color.claims-blue` (not hyperlink-blue, not underlined). The asterisk pattern from earlier drafts is deprecated — even single-source slides use a numbered superscript so the convention is consistent across the deck.

- **One source:** single superscript number. Example: `978M addressable users¹`.
- **Two sources at one citation point:** comma-and-non-breaking-space separated. Example: `ScholarQABench¹,²`.
- **Three or more *consecutive* sources at one citation point:** en-dash range, per Nature style. Example: `file drawer.¹⁻⁴`. Use the en-dash `–` (U+2013), not a hyphen, and not the full comma-separated list — `¹,²,³,⁴` is wrong once the range reaches three; collapse it to `¹⁻⁴`.
- **Three or more *non-consecutive* sources at one citation point:** comma-and-non-breaking-space separated. Example: `¹,³,⁵`. Use the range form only when the numbers run sequentially.

**Reference strip**: Bottom of slide, above the footer row, a 0.5pt hairline rule, color.mist. Below the rule:

```
¹ UNESCO (2025). What you need to know about higher education.
² Haakenstad, A. et al. (2022). The Lancet, 399(10341), 2129–2154.
```

All in Inter Regular 14px, `color.graphite`, with `font-variant-numeric: tabular-nums`. Hanging indent at the numeral so wrapped lines align with the text after the marker. Max 4 references per slide; if more are needed, move them to the Appendix.

**Scientific article citation format**:

```
Author et al., Year. Title, *Journal* (Volume), Page–Page. DOI-URL
```

Concrete example (Nature numbered-superscript pattern, in-body marker is `<sup>1</sup>` in `color.claims-blue`):

```
¹ Asai et al., 2026. Synthesizing scientific literature with retrieval-augmented language models, *Nature* (650), 857–863. https://doi.org/10.1038/s41586-025-10072-4
```

Rules: authors abbreviated with `et al.` after the first author when there are more than two, period after the year, article title in sentence case (no quotes, no italics), **journal name in italics** (Inter Italic, same size and color as the rest of the strip), volume in parentheses immediately after the journal, page range with en-dash (`–`, not hyphen), trailing period, then the full DOI URL rendered as a hyperlink in `color.claims-blue` with a same-color underline. Never use shorthand like `Asai et al., Nature 2026` — the full citation lives on the slide so a reader can verify the source without leaving the deck. This rule covers peer-reviewed journal articles only; other source types follow the formats below.

**Web / blog / organizational reference format**:

```
Organization, Year. Title. URL
```

Concrete example:

```
² DeSci Labs, 2026. Zero hallucinated citations: SciWeave's ScholarQABench results. https://www.desci.com/blog/zero-hallucinated-citations-sciweaves-scholarqabench-results
```

Rules: organization (or individual author if non-organizational) name, comma, year, period, title in sentence case (no quotes, no italics — there's no journal to italicize), period, full URL hyperlinked in `color.claims-blue` with same-color underline. Used for company blog posts, press releases, white papers, internal reports referenced externally, and any web source that isn't a peer-reviewed article. Working papers and preprints with DOIs follow the scientific-article format (with the DOI URL); blog/org posts without DOIs follow this format.

**Reference-strip layout when references stack**:
Multiple references in a strip use the **Nature numbered-superscript pattern** (per the in-body citation guidance above). The strip is anchored at `bottom: 110px` and grows upward as references are added — the bottom-most reference therefore stays at the same distance from the footer regardless of how many entries the strip carries. Use `8px` margin-top between references for breathing space (the references stay distinct without splitting visually into separate blocks). Max 4 references per slide; if more are needed, move them to the Appendix.

**Hyperlinks** render as `color.claims-blue` with a 0.5pt underline in the same color. Never the default PowerPoint purple-on-visited.

---

## 6. Do's and don'ts (global)

**Do**

- **Enforce the five rules in §0 first.** They override everything below.
- **One slide, one idea.** A long, multi-clause title is usually a sign that two slides are hiding inside one. The exception is **narrative title voice for the pitch register**: a sentence-style title (`AI ate the internet. Science is what it can't digest.`, `Live today. Two loops compounding.`, `Sequenced bets. Three gates.`) carries positioning work that a category label (`Market opportunity`, `Traction`, `Roadmap`) cannot. For investor and conference pitches the narrative title is allowed and often preferable — it makes the slide do rhetorical work even before the speaker opens their mouth. For board decks and internal updates, stay with tight nouns or short clauses; the audience already has the context, the title shouldn't compete for attention. The test for whether a narrative title earns its place: it would survive being read out loud as the speaker's opening line for that slide.
- Reach for the hero-stat archetype first. When the audience will remember the number more than the commentary, put the number on its own slide.
- Round to the digit that matters. `$732K cash`, not `$732,418 cash`, unless precision is the point.
- Use Inter Light at display sizes for every hero numeral. The scale carries the weight, not the typeface.
- Keep the left-edge Ink band on every content slide.
- When in doubt between fewer-dense slides and more-sparse slides, choose more-sparse. The deck gets longer. That's fine. The audience retains more.
- Vertically center short content blocks so the stage breathes on all four sides.
- Break lines explicitly (`<br>`) only after a period or a comma. Verify the natural wrap doesn't split a clause — widen the container or split into two explicit `<span class="line">` blocks when it does.
- Test the deck at half-screen share on a Zoom call before the meeting. If body text is hard to read at that size, the type is too small.

**Don't**

- Write paragraphs on slides. If a sentence runs longer than 10 words, it belongs in speaker notes.
- Break a line mid-sentence. No break between noun and verb, modifier and word, preposition and its object.
- Squeeze content into the upper-left corner. If the right half of the slide is empty, the content is mis-sized, not the slide.
- Ship a text-only content slide. If there's no visual anchor, either add one or merge the slide.
- Restate the same point across two slides. Each slide earns its place by adding something the previous didn't.
- Write slides the presenter would read verbatim. Slides carry headlines and data; voice carries narrative.
- Use sub-bullets (2nd or 3rd level). They read as memo-speak, not slide-speak.
- Put more than 5 items on a short-list slide.
- Drop a solo micro-stat with no comparison or unit context. If the number doesn't carry meaning on its own, cut it.
- Bold inside body text for emphasis. Use scale or color, not weight.
- Use Office-default chart colors. Stick to the 6-step categorical sequence in §2.1.
- Put a colored ribbon on a table header.
- Embed a dashboard screenshot to save time. Rebuild the chart in the deck's own system.
- Use any words from the CLAUDE.md AI-slop block in slide titles or body. The audience is technical; they smell it.
- Add a section divider for every subsection. Dividers are for top-level agenda items only.
- Break the left-edge band safe area.
- Introduce a second typeface. Inter only. Hierarchy comes from weight, size, color, and letter-spacing.

---

## 7. Open questions / deferred decisions

Flagged for review before build, not blocking the spec:

1. **Print parity for cover / closing.** The Ink overlay + render burns toner if printed at full opacity. The print CSS mutes the render to 15% — confirm legibility on a sample print before Proof of Talk.
2. **Footer date format.** Currently `02 · TRACTION · JUN 2026`. For an investor pitch the date may not earn its keep across every slide; consider dropping it on content slides and keeping only the section name + page number.

---

## 8. Print approach

Investors print. The HTML template includes a `@media print` block that the browser triggers when "Save as PDF" or "Print" is invoked.

**Print rules**

- Each slide maps to one printed page.
- Page orientation: landscape.
- Page size: standard A4 landscape (297mm × 210mm). US Letter landscape works equivalently.
- Background imagery and full-bleed color fills are suppressed or muted for print:
  - Cover render: prints at 15% opacity so the image is visible as a soft wash but uses minimal toner. Title and date switch to `color.ink` so they read on white.
  - Closing render: same treatment as cover.
  - Left-edge Ink band: prints as a 1.5pt `color.ink` rule at the same position, not a solid 64px fill. Preserves the continuity cue without burning through toner.
  - Section dividers: parchment background prints as white; type stays ink. Prints as-is.
- Content slides print unchanged (they're already mostly white ground with black type).
- Navigation controls, slide-counter UI, and keyboard-hint overlays are hidden in print.
- Page numbers in the footer carry through.

**Paper-copy test** Before the first live investor meeting, print one copy of a populated deck on a standard office laser printer. Check that the cover/closing don't exceed one-third ink coverage on those pages.

---

## 9. Deliverables

**In this pass**

1. This spec document.
2. **HTML presentation template** (`Pitch-Deck-Template.html`) — single self-contained file, embedded CSS + JS, all archetypes, keyboard + on-screen navigation, fullscreen-ready for Zoom, print CSS that produces a clean PDF when printed.

**Future work**

1. **Token file** (JSON or CSS custom properties exported cleanly) so the same system can govern marketing surfaces (landing pages, investor updates) that should match the pitch deck.
2. **One-page style tear-sheet** (printable) summarizing the system for team members who contribute slides.
3. **Chart component library** — D3 or Observable Plot helpers that render bar / line / donut / funnel in the deck's exact palette + type tokens, so charts don't need to be hand-tuned per slide.

PPTX is deprecated. The HTML template replaces it as the source of truth for all future pitch decks.

---

*End of spec. Questions, objections, or direction changes land better before the deck is populated than after.*
