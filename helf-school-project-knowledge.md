# helf.school — Project Knowledge Document
*Last updated: April 2026 — Retrofit session: Articles 01–03 (Hypertension, Cholesterol, Heart Attack Risk) fully rebuilt to current standards. New standards locked: Section 2 stat grid, Section 4 navy research cards, ev-stat-row evidence pattern, CTA horizontal rows, mandatory pre-output voice audit, disclaimer bar. Articles 04–18 retrofit still pending per new template standards. Next: Articles 04–07 (Statins, Lifestyle Changes, Salt, Supplements). Article 21 (Constipation) not built until all retrofits complete.*

---

## 🚨 1. READ THIS FIRST — UPLOADED FILES ARE NOT CORRUPTED

**Claude must read this section at the start of every session before commenting on project file state.**

### The false-alarm problem
When files are uploaded to this Claude Project via drag-and-drop from Microsoft Edge, the upload mechanism captures the **Claude.ai loader HTML page** rather than the actual file content. These artefacts look like this:
- **File size:** ~5140 bytes
- **Content starts with:** `<!doctype html><html data-build-id="..." ...>`
- Contains references to `assets-proxy.anthropic.com`

### These files are NOT corrupted. The real files:
- Live on GitHub at `github.com/pls4286/helfschool`
- Are intact at `pls4286.github.io/helfschool`
- Can be viewed by clicking "Raw" on the GitHub file page

### The rule
> **NEVER raise a false alarm about "corrupted" project files. The filename + article inventory in Section 6 are the source of truth. If a real file inspection is needed, ask Paul to paste from GitHub Raw view.**

---

## 2. PROJECT OVERVIEW

**Site:** helf.school
**GitHub:** pls4286/helfschool — live at pls4286.github.io/helfschool
**Upload method (to GitHub):** Drag-and-drop at github.com/pls4286/helfschool/upload/main
**Browser:** Microsoft Edge (incognito — extension conflict)
**Owner:** Dr Paul — retired NHS GP, over 20 years experience, ill-health retired end of 2019

**Mission:** "To give every person access to clear, honest, evidence-based health education — helping them become a more informed, empowered participant in their own care."

**Tone:** Informative, empowering, non-dictatorial, evidence-led, never prescriptive. Never use the word "eliminated". Content is explicitly health education — NOT medical advice.

---

## 3. DR PAUL

- Retired NHS GP, over 20 years experience
- Tier One ill-health retired by Chief Medical Officer for NHS at end of 2019 (stress)
- Happily married 38 years, four adult children
- Core philosophy: good medicine begins with truly listening
- Presents on video as "Dr Paul" (surname not used publicly)
- Communicates in UPPERCASE, prefers brief direct responses

---

## 4. DESIGN SYSTEM

### Colours
| Token | Hex |
|-------|-----|
| Navy | #1B2A4A |
| Coral | #E8634A |
| Cream | #FAF7F2 |
| Sage | #7A9E87 |
| Amber | #E8A84A |

### Category colours
| Series | Hex |
|--------|-----|
| Cardiovascular | #C8423A |
| Neurological | #6B5EA8 |
| Digestive | #D47C3A |
| Fatigue | #3A8A7A |
| Medical | #2E6BA8 |
| Practical | #7A6A2E |

### Fonts
- **Fraunces** — serif headings
- **DM Sans** — body text. Minimum load: `wght@400;500;600;700`. **Never weight 300.**
- Always set `font-weight: 400` explicitly on body element

### Logo
Open-book SVG with "HEALTH EDUCATION" tagline beneath helf.school wordmark.

---

## 5. SITE ARCHITECTURE

### Public pages
- `index.html` — homepage
- `helf-school-conditions.html` — conditions library
- `helf-school-membership.html` — membership pricing

### Membership pricing (LIVE — confirmed correct)
| Tier | Price |
|------|-------|
| Explorer (free) | £0 |
| Member | £6/month or £60/year |
| Lifetime | £150 one-off |

### Community forum (planned, not yet built)
Categories: Living with AF · Medications & Treatments · Lifestyle & Prevention · Research Discussion · Mental Health & Heart · Introductions
Free = read-only. Paid members = full access.

---

## 6. ARTICLE INVENTORY

### Cardiovascular Series (Articles 01–07)
| # | Title | Slug | Status |
|---|-------|------|--------|
| 01 | Hypertension | hypertension | ✅ FULLY RETROFITTED April 2026 |
| 02 | Cholesterol Explained | cholesterol | ✅ FULLY RETROFITTED April 2026 |
| 03 | How Doctors Estimate Heart Attack Risk | heart-attack-risk | ✅ FULLY RETROFITTED April 2026 |
| 04 | Statins — Benefits & Risks | statins | ⏳ RETROFIT PENDING |
| 05 | How to Reduce Cardiovascular Risk with Lifestyle Changes | lifestyle-changes | ⏳ RETROFIT PENDING |
| 06 | Salt and Blood Pressure | salt-blood-pressure | ⏳ RETROFIT PENDING |
| 07 | Do Supplements Lower Cholesterol? | supplements-cholesterol | ⏳ RETROFIT PENDING |

Each article has three files: `[slug].html` · `[slug]-visuals.html` · `[slug]-teleprompter.html`

### Practical Health Series (Articles 08–12)
| # | Title | Slug | Status |
|---|-------|------|--------|
| 08 | The Mediterranean Diet | mediterranean-diet | ⏳ RETROFIT PENDING |
| 09 | Sleep | sleep | ⏳ RETROFIT PENDING |
| 10 | Exercise | exercise | ⏳ RETROFIT PENDING |
| 11 | Stress | stress | ⏳ RETROFIT PENDING |
| 12 | Alcohol | alcohol | ⏳ RETROFIT PENDING |

Article 12 Alcohol: canonical reference for visuals layout (horizontal rows, colour narrative, inline citations, hero-first-screen).

### Digestive Health Series (Articles 13–21)
| # | Title | Slug | Status |
|---|-------|------|--------|
| 13 | Acid Reflux | acid-reflux | ⏳ RETROFIT PENDING |
| 14 | IBD: Crohn's Disease and Ulcerative Colitis | ibd | ⏳ RETROFIT PENDING |
| 15 | Bloating | bloating | ⏳ RETROFIT PENDING |
| 16 | IBS | ibs | ⏳ RETROFIT PENDING |
| 17 | Fatty Liver Disease (MASLD) | masld | ⏳ RETROFIT PENDING |
| 18 | Coeliac Disease | coeliac | ⏳ RETROFIT PENDING |
| 19 | Gallstones | gallstones | ✅ COMPLETE (new build) |
| 20 | Diverticular Disease | diverticular-disease | ✅ COMPLETE (new build) |
| 21 | Constipation | constipation | ❌ NOT BUILT — build after all retrofits complete |

Screen files exist for: acid-reflux (ar-sphincter-screen.html, ar-barretts-screen.html), ibd (ibd-gut-screen.html), bloating (bloating-gut-screen.html, bloating-fodmap-screen.html), coeliac (coeliac-villi-screen.html).

Article 17 note: ESSENCE trial ⚑ CLEARED — published NEJM April 2025, PubMed 40305708 ✓.

*Note: Old script files (e.g. hypertension-script.html) exist on GitHub for some articles but are superseded by the three-file standard.*

---

## 7. WORKFLOW — NEW ARTICLE

Build in this order:
1. **Pre-draft verification** — web search every key claim, statistic, and study before writing
2. **Article HTML** — four sections, key terms box, references
3. **Visuals HTML** — `[article]-visuals.html`
4. **Teleprompter HTML** — `[article]-teleprompter.html`
5. **Screen HTMLs** — standalone full-screen diagrams where needed

---

## 8. ARTICLE STANDARDS

### Structure
1. What is it?
2. Why does it matter?
3. What your doctor might do
4. What the research shows

Key Terms box between sections 1 and 2 — navy background, 2-column grid, series colour on left border.

"Putting it all together" — navy box at end of Section 4. Coral title. Italic paragraphs. Final paragraph: bold white non-italic takeaway.

---

### ⚠️ LEGAL NOTICE — Educational Voice — TOP STANDARD (NON-NEGOTIABLE)

helf.school presents health education, NOT medical advice. If any content directs a reader to take a specific clinical action, it creates potential legal liability for Dr Paul personally.

**Claude MUST run a full internal voice audit on every article, visuals deck, and teleprompter BEFORE outputting any file. Dr Paul must never need to ask.**

**DESCRIBES, never INSTRUCTS.**

**AVOID (directive):**
- "you should / you must / you need to"
- "speak to / see / call your GP"
- "seek advice / seek help / seek urgent care"
- "avoid / don't / do not" directed at reader
- "are to be avoided" / "should be avoided"
- "report to your GP" / "worth reporting"
- "that's urgent" / "needs assessment"
- "act on it early" / "make sure"
- "always tell / always discuss / always speak to"
- "stop and seek urgent"
- Any shortened version of the disclaimer phrase

**USE (descriptive):**
- **"conversation for you to have with your GP or healthcare professional"** — ALWAYS the full phrase. Never shortened.
- "in UK practice..."
- "clinically recognised as..."
- "clinically recognised as time-sensitive — 111 and urgent GP services exist for this" / "999 exists for this"
- "NICE describes / recommends / identifies..."
- Describe what happens rather than instruct

**Disclaimer (article, footer, Segment 0 of every video):**
> "Anything personally relevant is a conversation for you to have with your GP or healthcare professional."

---

### Section 2 — 2×2 Stat Grid (MANDATORY — locked April 2026)

NEVER use bullet-point cards. USE a 2×2 grid:
- Large Fraunces number → bold label → 1-line prose body
- Series colour on `border-top: 3px solid`
- Inline superscript citations on every stat
- 2–3 prose paragraphs below grid

```css
.why-stat-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 0.9rem; margin: 1.6rem 0 2rem; }
.why-stat-card { background: #fff; border-radius: 10px; border: 1px solid var(--border); padding: 1.2rem 1.3rem; border-top: 3px solid [series-colour]; }
.why-stat-n { font-family: 'Fraunces', serif; font-weight: 900; font-size: clamp(2.4rem,4.5vw,3.2rem); color: [series-colour]; line-height: 1; }
.why-stat-label { font-size: 1.00rem; font-weight: 700; color: var(--navy); }
.why-stat-body { font-size: 0.93rem; color: var(--text); font-weight: 400; }
```

---

### Section 4 — Navy Research Cards with Stat-First Layout (MANDATORY — locked April 2026)

NEVER use old white research item cards. USE navy research cards, stat FIRST.

**Card order:** header → meta → stat block → body → source. Number is the visual anchor.

```css
.research-card { background: var(--navy); border-radius: 12px; padding: 1.5rem 1.7rem; color: #fff; }
.research-card-stat-block { background: rgba(255,255,255,0.08); border-radius: 8px; padding: 0.8rem 1rem; margin-bottom: 0.9rem; }
.research-card-stat-context { font-size: 0.72rem; font-weight: 700; letter-spacing: 0.09em; text-transform: uppercase; color: rgba(255,255,255,0.60); }
.research-card-stat-row { display: flex; align-items: baseline; gap: 0.5rem; flex-wrap: wrap; }
.research-card-stat-number { font-family: 'Fraunces', serif; font-weight: 900; font-size: 2.8rem; color: var(--coral); line-height: 1; }
.research-card-stat-what { font-family: 'Fraunces', serif; font-weight: 700; font-size: 1.25rem; color: #fff; }
.research-card-stat-label { font-size: 0.95rem; font-weight: 600; color: rgba(255,255,255,0.85); }
```

---

### Disclaimer bar (MANDATORY — locked April 2026)

Yellow bar immediately below hero, above jump nav:

```html
<div class="disclaimer-bar" role="note">
  <div class="disclaimer-bar-inner">
    <span class="disclaimer-bar-icon">⚕️</span>
    <p><strong>Health education — not medical advice.</strong> Anything personally relevant is a conversation for you to have with your GP or healthcare professional.</p>
  </div>
</div>
```

```css
.disclaimer-bar { background: #FFF8E7; border-top: 3px solid var(--amber); padding: 0.95rem 2rem; }
```

---

### Inline citation standard (CANONICAL)
Every stat or research claim in prose must carry a superscript reference linking to the references section.
```html
<sup class="ref-sup"><a href="#ref-N">N</a></sup>
```
CSS: amber pill styling, `rgba(122,106,46,.1)` background.

### References section standard
Every reference: full citation (authors, title, journal, year, DOI) + pill links (DOI required, PubMed only if verified by web search in same session).

⚠️ **PubMed IDs are UNRELIABLE from training data.** Never add PubMed IDs without web search verification. Flag ⚑ if unverified.

### First-screen standard (CANONICAL)
Hero + disclaimer bar fill the first screen. Section 1 begins below fold.
```css
.article-hero { min-height: calc(100vh - 56px - 8.5rem); display: flex; align-items: center; }
```

### Medical term lay-clarification
Plain-English bracket after every medical term — every time it appears, not just first mention.

### Statistical term lay-clarification
Plain-English brackets every time: HR (hazard ratio) · PAR (population-attributable risk) · OR (odds ratio) · RR (relative risk) · NNT (number needed to treat) · CI (confidence interval).

### Drug naming
Generic + brand in brackets: atorvastatin (Lipitor), semaglutide (Ozempic, Wegovy).

### Readability
- Body text: `#2C2C2C`, explicit `font-weight: 400`
- Pale colours NOT permitted: `#374151`, `#4B5563`, `#555`, `#6B7280`
- No `fadeUp` animations on body sections
- `scroll-margin-top: 150px` on every `.article-section`

---

## 9. VIDEO STANDARDS

### Three-file architecture (current standard)
**(1) Article HTML** · **(2) Visuals HTML** · **(3) Teleprompter HTML**

### Standard video intro (Segment 0 of every video)
> "I'm Dr Paul — I spent over twenty years as an NHS GP before I retired in 2019. Today I want to talk to you about [TOPIC]. Now, I do have to say upfront — what I'm giving you here is health education, not medical advice. Anything personally relevant is a conversation for you to have with your GP or healthcare professional. Right — let's get into it."

~15–18 seconds. Full phrase always. Never shortened.

### Video length: 4–5 minutes maximum
Teleprompter word count: **600–750 words total**. Cut ruthlessly.

### Teleprompter core standard
Every teleprompter delivers: (1) fundamental MESSAGES · (2) key STATISTICS · (3) specific practical POINTERS.

### GIF capture settings
Scale 0.62 · Every 2nd frame · 120 colours · Under 1.5MB PPTX.

---

## 10. TELEPROMPTER STANDARDS

### Format
- Default speed: level 3 · Default font: `1.9rem`
- RAF auto-scroll · Touch swipe · Segment jump dots
- **Canonical control bar:** Speed − [N] + | Font A− A+ | ⏸ Pause | ↑ Top | word count right-aligned
- **Canonical reference:** stress-teleprompter.html (and all April 2026 retrofit files)

### Cue box format (MANDATORY)
```
▶ ADVANCE NOW — then read · SLIDE [N] — [description]
```
Cue box PRECEDES the script lines for its segment. Advance visual first, then read.

### Segment structure (6 segments standard)
- Seg 0: Introduction + disclaimer
- Seg 1: What is it
- Seg 2: Why it matters
- Seg 3: What doctors do
- Seg 4: The evidence (slides 5–7)
- Seg 5: CTA / Close (ends with closing card cue)

---

## 11. VISUALS FILE STANDARDS

### Slide structure (10 slides standard)
1. Title / intro card
2. Concept diagram
3. Why it matters — horizontal harm rows (RED)
4. What doctor might do — horizontal action rows (GREEN)
5–7. Research evidence — 3 slides × 2 ev-cards
8. Mechanisms — horizontal amber rows
9. CTA / takeaway slide
10. Closing card

---

### Evidence card stat block pattern (MANDATORY — locked April 2026)

Every evidence card (slides 5–7) uses the updated stat block:

```
.ev-stat-context  → "KEY FINDING" (0.68rem, caps, 60% opacity)
.ev-num           → Big number (3.0rem, .good/.bad/.warn colour class)
.ev-what          → Bold outcome description (1.0rem white)
.ev-label         → Conditions qualifier (0.82rem, 80% opacity)
```

Number and outcome read as ONE UNIT — layperson reads the full finding in one pass.

**ev-num word labels — HARD RULE (confirmed error slides 5–7, statins-visuals):**
When `.ev-num` contains a word or phrase rather than a number, the standard 3.0–3.4rem font-size overflows the stat box. Apply these caps — no exceptions:
- Short word (e.g. "Switch", "Confirmed") → `font-size: 2rem`
- Two-word / two-line (e.g. "Not supported") → `font-size: 1.7rem; line-height: 1.2`
- Numeric stats (e.g. −22%, >90%, ~57%) → standard `font-size: 3.0rem`
Always add to `.ev-stat`: `overflow: hidden` — prevents bleed into the `.ev-det` column regardless of label length.

**Canonical reference:** diverticular-disease-visuals.html slide 6.

```css
.ev-stat { background: rgba(212,184,74,.09); border-radius: 14px; padding: 1.1rem .9rem; text-align: left; }
.ev-stat-context { font-size:.68rem; font-weight:700; letter-spacing:.10em; text-transform:uppercase; color:rgba(255,255,255,.60); margin-bottom:.2rem; }
.ev-num { font-family:'Fraunces',serif; font-size:3.0rem; font-weight:700; line-height:1; margin-bottom:.25rem; }
.ev-what { font-size:1.0rem; font-weight:700; color:#fff; line-height:1.3; margin-bottom:.3rem; }
.ev-label { font-size:.82rem; color:rgba(255,255,255,.80); line-height:1.4; }
```

---

### High-impact layout standard (CANONICAL — Article 12 Alcohol)

For slides with 4–6 parallel items (systems affected, mechanisms, doctor's tools): **HORIZONTAL stacked rows**, not columns.

**Card grid:** `icon (72px) | content (title + body) | hero-stat (right)`

**Deck-wide colour narrative:**
| Colour | Variable | Use |
|--------|----------|-----|
| 🔴 Red | `var(--bad)` | Harm / risk slides |
| 🟠 Amber | `var(--warn)` | Mechanism slides |
| 🟢 Green | `var(--good)` | Action / doctor slides |

**Row card standards:**
- `align-items: start` — **NEVER center**
- `.doc-body` / `.mech-body` / `.sys-body`: `-webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden`
- Icons: `padding-top: 0.1rem`
- Emoji font stack: `"Apple Color Emoji","Segoe UI Emoji","Noto Color Emoji",sans-serif`

**Row count → sizing guide (confirmed via statins-visuals):**
| Rows | Gap | Padding | Icon | Title | Body |
|------|-----|---------|------|-------|------|
| 4 | .65rem | 1rem 1.5rem | 2.8rem | 1.4rem | .98rem |
| 5 | .45rem | .70rem 1.2rem | 2.2rem | 1.2rem | .93rem |
| 6 | .35rem | .60rem 1.1rem | 1.9rem | 1.1rem | .88rem |

These are confirmed working values — do not increase them for slides with these row counts.

---

### CTA/Takeaway slide standard (MANDATORY — locked April 2026)

Slide 9: **full-width horizontal rows** — NOT chips or small cards.

**Structure:**
```css
.cta-wrap-v2 { display: grid; grid-template-rows: auto 1fr auto; height: 100%; padding: .4rem; gap: .45rem; min-height: 0; overflow: hidden; }
.cta-rows-v2 { display: grid; grid-template-rows: 1fr 1fr 1fr 1fr; gap: .4rem; min-height: 0; overflow: hidden; }
.cta-row-v2 { display: grid; grid-template-columns: 52px 1fr auto; align-items: start; border-left: 4px solid var(--acc); border-radius: 0 10px 10px 0; padding: .6rem .95rem; min-height: 0; overflow: hidden; }
.cta-row-body-v2 { font-size: .82rem; -webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden; }
.cta-row-word-v2 { font-family:'Fraunces',serif; font-weight:900; font-size:clamp(1.2rem,2vw,1.7rem); color:var(--acc); }
```

**Top section confirmed sizes (prevent bottom overflow):**
- Icon: `clamp(2.2rem,3.8vw,3.2rem)` — NEVER larger
- Headline: `clamp(2rem,3.8vw,3.2rem)` — NEVER larger
- Subline: `clamp(.95rem,1.5vw,1.2rem)` — NEVER larger
- `.cta-top` gap: `.3rem` · outer wrap gap: `.45rem`

**Required elements:**
- Radial glow background
- Badge: "What the evidence shows"
- 4 horizontal rows with stat/word on right
- `.cta-bottom` with `flex-shrink: 0` — full disclaimer phrase

**OVERFLOW RULE:** `.cta-wrap-v2` and `.cta-rows-v2` MUST both have `min-height:0; overflow:hidden` — without this the bottom disclaimer is pushed off screen.

**CTA ICON RULE:** The large emoji icon (`.cta-icon-v2`) on slide 9 is OMITTED by default. The badge + headline + subline + 4 rows + disclaimer already fill the slide. The icon wastes vertical space and pushes content off screen. Do not include it unless the slide has fewer than 4 rows and space is confirmed available.

---

### Slide content limits
- Max: (a) 3 stat + 1 research card, (b) 3 research cards, (c) 1 diagram + 2 info cards
- Never shrink text to fit — split to new slide

### Slide layout hygiene rules
1. Multi-row grids MUST have explicit `grid-template-rows`
2. Cards MUST have `min-height: 0` + `overflow: hidden`
3. Emoji font-family stack on icons
4. Maximum 3 vertical blocks per card
5. Sub-text ≤ 12 words
6. Comparison stats: context AT TOP
7. No redundant hero banners

### Font sizes (minimum — HARD FLOORS)
| Text type | Minimum |
|-----------|---------|
| Source / reference | `0.80rem` |
| Description / body | `0.93rem` |
| Supporting / label | `1.00rem` |
| Heading | `1.05rem` |

### Opacity minimums (HARD FLOORS)
| Element | Minimum |
|---------|---------|
| Journal / source | `rgba(255,255,255,0.80)` |
| Body / finding text | `rgba(255,255,255,0.88)` |
| Supporting labels | `rgba(255,255,255,0.80)` |
| Disclaimer footer (exception) | `0.18` |

### Research card stat standard
Stat boxes show OUTCOMES — effect sizes, risk changes — NEVER participant counts as headline.

---

## 12. QC PASS — REQUIRED BEFORE EVERY UPLOAD

1. **Readability** — no pale text, explicit font-weight:400 on body
2. **References** — full citation blocks with DOI (verified)
3. **Research flags** — all ⚑ claims verified before finalising
4. **Graphics** — standalone animation file exists + presenter inline match
5. **Article ↔ presenter consistency** — all facts, names, years match
6. **Scroll offset** — `scroll-margin-top: 150px` on `.article-section`
7. **Visuals visibility** — font sizes and opacity within spec
8. **Slide layout** — explicit rows, min-height:0, overflow:hidden
9. **Video length** — 600–750 words (4–5 min)
10. **Educational voice** — full internal audit before outputting. Zero tolerance.

---

## 13. APPROVED RESEARCH SOURCES

BMJ · NICE guidelines · Cochrane Database · NEJM · The Lancet · JAMA · BMJ Best Practice · PubMed · NHS/NHS Digital · ONS · CDC · WHO · Global Burden of Disease Study · ESC/EAS guidelines

---

## 14. PRODUCTION SETUP — VIDEO RECORDING

**Method:** OBS Studio compositing camera + visuals HTML.
- Visuals file full-screen on laptop, composited by OBS
- Teleprompter on phone/tablet beside camera lens
- Arrow keys advance visuals in sync with cues
- Cue boxes at TOP of each segment — advance visual FIRST, then read

---

## 15. OUTSTANDING TASKS (as of April 2026)

### ✅ Completed
- Articles 01–03 FULLY RETROFITTED to all current standards (April 2026)
- Articles 19–20 (Gallstones, Diverticular Disease) — COMPLETE new builds
- All standards locked (April 2026): Section 2 stat grid · Section 4 navy cards · ev-stat-row · CTA horizontal rows · mandatory voice audit · disclaimer bar · horizontal-row visuals layout · colour narrative · inline citations · hero first-screen · emoji font stack
- ESSENCE trial ⚑ CLEARED — NEJM April 2025, PubMed 40305708 ✓
- Lancet Commission dementia ⚑ CLEARED — DOI 10.1016/S0140-6736(24)01296-0
- Pricing confirmed correct (£0/£6/£60/£150) ✅

### ⏳ PRIORITY — Retrofit Articles 04–18 (do before building Article 21)

Five retrofit items per article:
1. Educational voice audit
2. Section 2 → 2×2 stat grid
3. Section 4 → navy research cards stat-first
4. Visuals slides 5–7 → ev-stat-row pattern
5. Visuals slide 9 → CTA horizontal rows

**Batch order:**
- Batch 1: Cardiovascular 04–07 ← NEXT UP
- Batch 2: Practical Health 08–12
- Batch 3: Digestive 13–18

**Method:** Paul pastes each file from GitHub Raw → Claude audits and fixes → outputs corrected files → Paul downloads (Artifact panel) and uploads to GitHub.

### ⏳ New builds
- Article 21 — Constipation — **DO NOT BUILD until all retrofits complete**
- Community forum

### ⚑ Citation verification needed before publishing
- **hypertension.html** ref 5 — Cochrane, BP lowering in over-60s (PubMed ID unverified)
- **hypertension.html** ref 6 — Cochrane 2025, mild hypertension (PubMed ID unverified)

---

## 16. FILE NAMING CONVENTION

| File type | Pattern | Example |
|-----------|---------|---------|
| Article | `[slug].html` | `hypertension.html` |
| Visuals | `[slug]-visuals.html` | `hypertension-visuals.html` |
| Teleprompter | `[slug]-teleprompter.html` | `hypertension-teleprompter.html` |
| Screen file | `[slug-abbrev]-[name]-screen.html` | `ar-sphincter-screen.html` |
| GIF source | `[slug]-[name]-gif.html` | `bloating-gut-gif.html` |

---

## 17. COMMUNICATION STYLE

- Dr Paul communicates in UPPERCASE
- Prefers brief, direct responses
- Always confirm article numbers and file names before building
- Flag any inconsistencies found during QC immediately

---

## 18. FILE UPLOAD METHOD

### Uploading TO GitHub
- **From local file:** Open in Notepad → Ctrl+A → Ctrl+C → paste into chat
- **From GitHub:** Find file → click Raw → Ctrl+A → Ctrl+C → paste into chat
- **Download from Claude outputs:** Artifact panel download button — **NEVER Ctrl+S or File → Save**

### Fetching files into Claude
Use GitHub raw URLs:
```
https://raw.githubusercontent.com/pls4286/helfschool/main/[filename].html
```

### Uploading TO Claude Project
⚠️ Drag-and-drop from Edge incognito captures the browser page (loader stub) — see Section 1.

---

## 19. END-OF-SESSION UPDATE PROTOCOL

At the end of each productive session:
1. Update this document
2. Download with Artifact panel button (NEVER Ctrl+S)
3. Upload to **both GitHub AND the Claude Project**

---

## 20. KEY DECISIONS LOG

| Date | Decision |
|------|----------|
| April 2026 | Section 2 standard locked: 2×2 stat grid (no bullet cards) |
| April 2026 | Section 4 standard locked: navy research cards, stat-first layout |
| April 2026 | CTA slide standard locked: full-width horizontal rows (no chips) |
| April 2026 | Evidence card stat block locked: ev-stat-row pattern |
| April 2026 | Educational voice: MANDATORY pre-output audit — legal protection |
| April 2026 | Disclaimer bar standard: amber bar below hero, above jump nav |
| April 2026 | Retrofit confirmed: Articles 04–18 need voice + stat grid + navy cards + ev-stat-row + CTA rows |
| April 2026 | Article 21 Constipation: not built until all retrofits complete |
| April 2026 | Membership lifetime price: £150 (confirmed) |
| April 2026 | Copyright: 2026 across all new/retrofitted files |
| April 2026 | hypertension.html refs 5 and 6 (Cochrane): flagged ⚑ unverified |
