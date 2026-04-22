# helf.school — Project Knowledge Document
*Last updated: April 2026 — All 18 articles complete across three series. All retrofit work complete: 17 visuals files updated to high-impact pattern (horizontal rows, colour narrative, emoji font stack); inline superscript citations applied to all articles; hero-first-screen standard applied to all articles. Canonical reference files: alcohol-visuals.html (visuals), stress-teleprompter.html (teleprompter), alcohol.html (article inline citations + first-screen). Next: Article 19+ Digestive Series (topic TBC) and community forum.*

---

## 🚨 1. READ THIS FIRST — UPLOADED FILES ARE NOT CORRUPTED

**Claude must read this section at the start of every session before commenting on project file state.**

### The false-alarm problem
When files are uploaded to this Claude Project via drag-and-drop from Microsoft Edge, the upload mechanism captures the **Claude.ai loader HTML page** (the thing that renders the Claude interface in the browser) rather than the actual file content. These upload artefacts look like this:

- **File size:** ~5140 bytes (script/teleprompter/screen) or ~6170 bytes (hypertension/IBS)
- **Content starts with:** `<!doctype html><html data-build-id="..." data-git-hash="..." ... class="h-screen antialiased scroll-smooth">`
- Contains references to `assets-proxy.anthropic.com` and `claude-ai/v2/assets/`

### These files are NOT corrupted. The real files:
- Live on GitHub at `github.com/pls4286/helfschool`
- Are intact and live on the website at `pls4286.github.io/helfschool`
- Can be viewed by clicking "Raw" on the GitHub file page

### The rule — applies to every session
> **NEVER raise a false alarm about "corrupted" project files based on byte size or visible loader HTML in the uploaded project context. The filename + the article inventory table in Section 6 below are the source of truth for what exists. If a real file inspection is needed, fetch via GitHub raw URL (see Section 17) or ask Paul to paste the content from GitHub Raw view.**

This has caused a full false-alarm session already. It must not happen again. If Claude notices a file that looks like a loader artefact, it should ignore the visible content and refer to the filename and inventory below.

---

## 2. PROJECT OVERVIEW

**Site:** helf.school
**GitHub:** pls4286/helfschool — live at pls4286.github.io/helfschool
**Upload method (to GitHub):** Drag-and-drop at github.com/pls4286/helfschool/upload/main
**Browser:** Microsoft Edge (incognito — extension conflict)
**Owner:** Dr Paul — retired NHS GP, over 20 years experience, ill-health retired end of 2019

**Mission:** "To give every person access to clear, honest, evidence-based health education — helping them become a more informed, empowered participant in their own care."

**Tone:** Informative, empowering, non-dictatorial, evidence-led, never prescriptive. Never use the word "eliminated". Content is explicitly health education — NOT medical advice.

**Audience:** General public.

---

## 3. DR PAUL

- Retired NHS GP, over 20 years experience
- Tier One ill-health retired by Chief Medical Officer for NHS at end of 2019 (stress)
- Happily married 38 years, four adult children
- Core philosophy: good medicine begins with truly listening
- Felt like "a square peg in a round hole" by 2018 as appointment times shortened
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
- **DM Sans** — body text. Minimum load: `wght@400;500;600;700`. Never weight 300.

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

✅ Confirmed correct on index.html and membership page.

### Members-only content
Full article library · Research analyses · Evidence ratings · Glossary · New content feed · Saved articles · Monthly Q&A

### Community forum (planned, not yet built)
Categories: Living with AF · Medications & Treatments · Lifestyle & Prevention · Research Discussion · Mental Health & Heart · Introductions
Rules: Be kind · No medical advice · Refer to articles for info · Respect privacy · 999 for emergencies
Free = read-only. Paid members = full access. Needs: thread creation, member profiles, moderation dashboard, crisis signposting, weekly digest.

---

## 6. ARTICLE INVENTORY

### Cardiovascular Series (Articles 01–07) — ✅ ALL COMPLETE
| # | Title | Article HTML | Visuals | Teleprompter |
|---|-------|-------------|---------|--------------|
| 01 | Hypertension | hypertension.html | hypertension-visuals.html | hypertension-teleprompter.html |
| 02 | Cholesterol Explained | cholesterol.html | cholesterol-visuals.html | cholesterol-teleprompter.html |
| 03 | How Doctors Estimate Heart Attack Risk | heart-attack-risk.html | heart-attack-risk-visuals.html | heart-attack-risk-teleprompter.html |
| 04 | Statins — Benefits & Risks | statins.html | statins-visuals.html | statins-teleprompter.html |
| 05 | How to Reduce Cardiovascular Risk with Lifestyle Changes | lifestyle-changes.html | lifestyle-visuals.html | lifestyle-teleprompter.html |
| 06 | Salt and Blood Pressure | salt-blood-pressure.html | salt-visuals.html | salt-teleprompter.html |
| 07 | Do Supplements Lower Cholesterol? | supplements-cholesterol.html | supplements-visuals.html | supplements-teleprompter.html |

*Note: Old script files (e.g. hypertension-script.html) exist on GitHub for some articles but are superseded by the three-file standard. No new script files are created.*

### Practical Health Series (Articles 08–12) — ✅ ALL COMPLETE
| # | Title | Article HTML | Visuals | Teleprompter |
|---|-------|-------------|---------|--------------|
| 08 | The Mediterranean Diet | mediterranean-diet.html ✅ | mediterranean-diet-visuals.html ✅ | mediterranean-diet-teleprompter.html ✅ |
| 09 | Sleep | sleep.html ✅ | sleep-visuals.html ✅ | sleep-teleprompter.html ✅ |
| 10 | Exercise | exercise.html ✅ | exercise-visuals.html ✅ | exercise-teleprompter.html ✅ |
| 11 | Stress | stress.html ✅ | stress-visuals.html ✅ | stress-teleprompter.html ✅ |
| 12 | Alcohol | alcohol.html ✅ | alcohol-visuals.html ✅ | alcohol-teleprompter.html ✅ |

**Article 12 note:** Built with the new high-impact visuals pattern (horizontal-row layout, deck-wide colour narrative, inline superscript citations, hero-first-screen). Serves as the canonical reference for all articles.

### Digestive Health Series (Articles 13–18) — ✅ ALL COMPLETE
| # | Title | Article HTML | Visuals | Teleprompter | Screen files |
|---|-------|-------------|---------|--------------|--------------|
| 13 | Acid Reflux | acid-reflux.html | acid-reflux-visuals.html | acid-reflux-teleprompter.html | ar-sphincter-screen.html, ar-barretts-screen.html |
| 14 | IBD: Crohn's Disease and Ulcerative Colitis | ibd.html | ibd-visuals.html | ibd-teleprompter.html | ibd-gut-screen.html |
| 15 | Bloating | bloating.html | bloating-visuals.html | bloating-teleprompter.html | bloating-gut-screen.html, bloating-fodmap-screen.html |
| 16 | IBS | ibs.html | ibs-visuals.html | ibs-teleprompter.html | — |
| 17 | Fatty Liver Disease (MASLD) | masld.html ✅ | masld-visuals.html | masld-teleprompter.html | — |
| 18 | Coeliac Disease | coeliac.html | coeliac-visuals.html | coeliac-teleprompter.html | coeliac-villi-screen.html |

**Article 17 note:** ESSENCE trial ⚑ CLEARED — published NEJM April 2025, PubMed 40305708 ✓. masld.html © updated to 2026. Ready for live.

### Digestive Health Series — Article 19+
Continuing series — topics TBC.

---

## 7. WORKFLOW — NEW ARTICLE

Build in this order:
1. **Pre-draft verification** — web search every key claim, statistic, and study before writing
2. **Article HTML** — four sections, key terms box, references
3. **Visuals HTML** — `[article]-visuals.html`
4. **Teleprompter HTML** — `[article]-teleprompter.html`
5. **Screen HTMLs** — standalone full-screen diagrams where needed

Old script files are superseded. **Three files per article** is the current standard.

---

## 8. ARTICLE STANDARDS

### Structure
1. What is it?
2. Why does it matter? (max 5 bullets)
3. What your doctor might do
4. What the research shows

Key Terms box sits **between sections 1 and 2** — navy background, alphabetical, plain English definitions.

"Putting it all together" — always navy box, italic text, **bold closing line**.

Research claims flagged ⚑ for Paul review before publishing.

### Educational voice — TOP STANDARD
**DESCRIBES, never INSTRUCTS.** This standard applies to every article, visuals deck, teleprompter, screen file, CTA, disclaimer, and footer — and overrides any older phrasing.

**AVOID (directive):**
- "please speak to your GP"
- "always tell / always discuss / always speak to"
- "you should / you must / you need to"
- "stop and seek urgent / seek medical advice"
- "if concerns / if worried / if anything feels relevant to you personally"
- "decision in partnership"
- "don't avoid / don't ignore"
- Any shortened version such as "conversation for your GP" or "conversation with your doctor"

**USE (descriptive):**
- **"conversation for you to have with your GP or healthcare professional"** — ALWAYS this full phrase. Never shortened. This is the single mandated phrase for signposting clinical discussion, disclaimers, footers, and video intros.
- "in UK practice" (when describing typical clinical approach)
- "clinically recognised as time-sensitive — 111/urgent GP exists for this" (for red-flag / time-sensitive features)
- "NICE describes as shared decision" (for shared decision-making)
- Describe what happens rather than instruct the reader: "the diary comes before the appointment" not "do it before your appointment"; "UK practice is to screen for X" not "your GP should screen for X"
- Red-flag section headings use "Clinically time-sensitive features" rather than "When to see your GP"

**Disclaimer (top of article, footer, and Segment 0 of every video):**
> "Anything personally relevant is a conversation for you to have with your GP or healthcare professional."

**CTA-title rule:** CTA titles must describe, not command. Example: "CBT-I is the NHS first-line option" — not "ask about CBT-I".

### Medical term lay-clarification standard
When a medical/technical term is used in an article, a plain-English meaning in brackets must follow — every time, not just first mention. Examples: ataxia (balance/coordination problems), peripheral neuropathy (nerve tingling/numbness), cardiovascular events (heart attacks, strokes, and cardiovascular deaths), Integrated Care Boards (NHS bodies that plan and fund health services for a region). Apply in prose, tables, bullets, callouts. Short-form brackets OK in tight table cells.

### Statistical term lay-clarification standard
Statistical measures require plain-English brackets every time they appear — in all prose, research cards, tables, and callouts:
- HR (hazard ratio — HR 1.23 = 23% higher risk)
- PAR (population-attributable risk — share of population cases linked to this factor)
- OR (odds ratio)
- RR (relative risk)
- SMD (standardised mean difference — effect size)
- NNT (number needed to treat — how many people need the treatment for one to benefit)
- CI (confidence interval — the range within which the true value most likely falls)

### Drug naming
Always include brand name(s) in brackets after generic name — e.g. semaglutide (Ozempic, Wegovy), atorvastatin (Lipitor), infliximab (Remicade). Apply to all articles.

### References standard
Every research item must include:
- Full citation: authors, full title, journal, year, volume, pages, DOI
- Pill links: journal full text + PubMed/PMC (only if verified by web search in same session)
- Use `.ref-block / .ref-full / .ref-links` CSS pattern from supplements-cholesterol.html
- Short link alone is NOT sufficient

⚠️ PubMed IDs are UNRELIABLE from training data. Confirmed wrong IDs found previously. Rule: no PubMed/PMC pill links unless verified by web search in same session. Omit and flag ⚑ if unverified. Journal DOI links acceptable. Paul checks every link before any article goes live.

### 🔑 Inline citation standard (CANONICAL — from Article 12 Alcohol)
**Every stat or specific research claim in article prose must carry a superscript reference number linking to the anchored entry in the references section.** Readers must always have a one-click route from any stat back to its source.

**Implementation:**
- Add `id="ref-N"` anchor to each reference block in the references section
- Add inline superscript markers to every stat: `<sup class="ref-sup"><a href="#ref-N">N</a></sup>`
- CSS: gold-accented pill styling, small pill background `rgba(122,106,46,.1)`, hover darker

**Example from alcohol.html (Section 2):**
> "...in 2023 the Office for National Statistics recorded **10,473 alcohol-specific deaths in the UK**<sup>10</sup> — the highest number since records began, and 38% higher than in 2019.<sup>10</sup>"

Applied to all articles 01–18. ✅

### 🔑 First-screen standard (CANONICAL — from Article 12 Alcohol)
**On landing, every article's first visible screen must show only the hero + the yellow health-disclaimer box.** Section 1 ("What is it?") begins below the fold, revealed on scroll.

**Implementation:**
- Hero CSS: `min-height: calc(100vh - 56px - 8.5rem); display: flex; align-items: center;`
- The `8.5rem` reserves space below the hero for the yellow disclaimer block to sit within the viewport
- Sticky nav is 56px; disclaimer + its top margin accounts for the ~8.5rem reservation

**Why it matters:** Setting the frame on arrival — the reader sees the title, the author credit, the "health education — not medical advice" disclaimer, and nothing else. No content is half-visible peeking up from below. Section 1 properly starts when the reader chooses to engage.

Applied to all articles 01–18. ✅

### Pre-draft verification
Before presenting any article, script, or visuals HTML, verify via web search that every cited study, trial, or statistic: (1) exists, (2) relates to the correct condition, (3) supports the claim made, and (4) every URL/DOI resolves to the correct article.

### Readability
- Body text: `#2C2C2C`, explicit `font-weight:400`
- Pale colours NOT permitted: `#374151`, `#4B5563`, `#555`
- DM Sans minimum `wght@400` — never 300
- No `fadeUp` or `opacity:0` animations on body sections — content must be immediately visible

### Hero visibility
- Hero subtitle: min `rgba(255,255,255,0.85)`
- Meta items: min `rgba(255,255,255,0.80)`
- Breadcrumb: min `rgba(255,255,255,0.75)`
- Values below 0.60 not permitted

### Key Terms box visibility
- "Key Terms" header: min `1.05rem`, `#fff`
- Term labels: min `0.88rem`, `font-weight:700`, category accent colour
- Definition text: min `0.92rem`, `rgba(255,255,255,0.90)`
- Opacity 0.75 or 0.80 not permitted for definition text

### Jump nav scroll offset — CRITICAL
Every article `.article-section` CSS rule MUST include:
```css
.article-section { scroll-margin-top: 150px; }
```
This compensates for sticky main nav (68px) + sticky jump nav (~46px) + breathing room. Without it, tab navigation scrolls section headings behind the nav bars. Never omit.

### Inline source references
- Min `0.75rem`, `rgba(255,255,255,0.55)` on dark / `#2C2C2C` on light
- The `.source-tag` style (tiny, `rgba(255,255,255,0.25)`) is NOT permitted

---

## 9. VIDEO STANDARDS

### Three-file architecture (current standard)
Each video requires **three** HTML files. Old combined presenter/script files are superseded.

**(1) Article HTML** — `[slug].html`
- Website page for readers
- Full depth, all references, all technical nuance

**(2) Visuals HTML** — `[slug]-visuals.html`
- Camera-facing slide deck
- Diagrams, animations, stat cards, research cards
- Keyboard navigation (← → arrows)
- No script text

**(3) Teleprompter HTML** — `[slug]-teleprompter.html`
- Scrolling script on phone/tablet beside camera lens
- Default speed: speed level 3 (`PX_PER_SEC_BASE = 20`)
- Default font: `1.9rem`
- Speed control: 1–6 via +/− buttons
- Font control: A+ / A− buttons
- **CUE BOX PATTERN — cue box PRECEDES the script lines for its segment, not follows them.** Label reads `▶ ADVANCE NOW — then read`. Viewer sees visual before Dr Paul speaks about it. Advance the visual first, then read the script while it is on screen. `stress-teleprompter.html` is the canonical reference implementation.
- RAF auto-scroll loop, touch swipe, segment jump dots

### Standard intro (every video, Segment 0)
> "I'm Dr Paul — I spent over twenty years as an NHS GP before I retired in 2019. Today I want to talk to you about [TOPIC]. Now, I do have to say upfront — what I'm giving you here is health education, not medical advice. Anything personally relevant is a conversation for you to have with your GP or healthcare professional. Right — let's get into it."
~15–18 seconds. Uses the full educational-voice phrase — never shortened. See Section 8 Educational Voice standard.

### Video length standard — 4 to 5 minutes maximum
People get bored easily on video — shorter is better. Teleprompter word count should be approximately **600–750 words total** (assuming ~150 wpm delivery). Aim for tight, punchy segments. When writing or revising, if word count exceeds ~750, cut — remove redundant examples, tighten preamble, merge segments. Applies to every video in every series.

### Teleprompter core standard — messages, statistics, pointers
Every teleprompter must deliver:
1. **Fundamental MESSAGES** — clearly and precisely
2. **Key STATISTICS** — exact numbers, no rounding drift from article
3. **Specific practical POINTERS** — what the viewer should do (e.g. "add 1,000 steps/day", not "move more")

Every segment must serve message, statistic, or action. Cut what doesn't. Warm, non-prescriptive tone retained — but clarity and impact come first. Article is the full-depth reference; teleprompter is the tight, high-impact doorway.

### Screen files
Standalone full-screen HTML files for camera filming (e.g. `ar-sphincter-screen.html`, `coeliac-villi-screen.html`).
- Full-screen, auto-animate on load, bold for filming
- Footer: min `clamp(.65rem,1vw,.80rem)`, `rgba(255,255,255,0.65)`
- Referenced by bold red `.diagram-cue` box in teleprompter

### GIF capture settings
Scale 0.62 · Every 2nd frame · 120 colours · Under 1.5MB total PPTX

### Graphics standard
Standalone animation HTMLs = GIF capture sources ONLY. Never embedded directly in articles or presenters. Each presenter contains its own inline recreation in the `visuals{}` object. Both standalone and inline versions must exist for every segment visual.

### Article ↔ presenter consistency
All trial names, years, citation authors, and statistics must match across article and presenter files. Cross-check before upload.

---

## 10. VISUALS FILE STANDARDS

### 🔑 High-impact layout standard (CANONICAL — from Article 12 Alcohol)
For slides presenting **4–6 parallel items** (systems affected, effects, mechanisms, doctor's tools, risk factors, stages), use **HORIZONTAL stacked rows**, not narrow vertical columns.

**Card grid:** `icon (72px fixed) | content (title + body) | hero-stat (right)`

**Why it works for the layperson:**
- The stat can be 2.5–3.6rem (vs ~1.6rem crammed into narrow columns) — genuinely eye-catching
- Body text reads as proper sentences, not 3-word fragment columns
- Each row feels like a standalone headline — newspaper-front-page, not crowded index card
- Icon (left) → content (middle) → stat (right) matches English reading direction

**Deck-wide colour narrative — apply consistently:**
| Colour | Variable | Use on... |
|--------|----------|-----------|
| 🔴 Red | `var(--bad)` + coral border | Harm / risk stats — *"this is what alcohol does to you"* |
| 🟠 Amber | `var(--warn)` + amber border | Mechanism / pathway outcomes — *"this is HOW it does it"* |
| 🟢 Green | `var(--good)` + sage border | Action / help columns — *"this is what can be done about it"* |

A layperson moving through the deck unconsciously picks up the semantics: **red things happen → amber pathways explain → green things can be done**. That is sound educational design, not decoration.

**Alcohol article 12 visuals is the canonical reference** — slides 3 (five systems), 4 (doctor's toolkit), 8 (mechanisms) all use this pattern. Applied to all articles 01–18. ✅

### 🔑 High-impact CTA slide standard (CANONICAL — from hypertension-visuals.html)
Every CTA slide must be full-screen with:
- Radial gold-glow background + pulsing icon halo (3.2s drop-shadow animation)
- Fraunces headline: `clamp(3.2rem, 5.8vw, 4.9rem)`, bold
- Fraunces italic subline
- 4 ACTION CARDS (not chips) — emoji + Fraunces bold label, gradient + gold border
- **MEDICAL-ADVICE DISCLAIMER BOX** — ⚕️ icon, dashed border, "Health education — not medical advice" + full educational-voice phrase
- Closing slide also gets same disclaimer box

### Visuals purpose standard
Every visuals slide deck serves one job — make the evidence feel real and personal, then pull the viewer toward action. Stats are chosen because they answer "does this affect me?" or "can I change this?" — not because they are the most impressive numbers. Every research card connects forward to a CTA. The CTA slides are the destination; the evidence slides are the journey there. Visuals must be bold, striking, and immediately readable at filming distance. A layperson watching the video should be able to read every stat on screen, understand what it means for their life, and feel pulled toward the call to action by the time it appears.

### Screen presence
All visuals HTML files must fill the screen boldly and be readable at distance:
- Stage padding: maximum `0.6rem 0.75rem`
- No artificial `max-width` below `100%` on content wrappers

### Slide layout hygiene rules
1. **Multi-row grids MUST have explicit `grid-template-rows`** (e.g. `1fr 1fr`, `repeat(6,1fr)`) — without this, auto-rows size to content and the bottom row drops off screen.
2. **Cards in constrained grids MUST have `min-height: 0` + `overflow: hidden`** — without these, long content bleeds into the next row.
3. **Use emoji font-family stack** on icon elements: `"Apple Color Emoji", "Segoe UI Emoji", "Noto Color Emoji", sans-serif` — forces reliable colour-emoji rendering across OS/browser combinations. Avoids the "missing heart" / "missing brain" rendering issue seen with newer Unicode emojis (e.g. 🫀 from 2021).
4. **Maximum 3 vertical blocks per card** (heading + main content + label/badge). Four or more elements stacked always becomes cramped and overlaps.
5. **Sub-text must be ONE short line** (≤ 12 words). Longer explanation belongs in the teleprompter — not the slide.
6. **Comparison stats: context AT TOP** in Fraunces accent colour showing *what* is being compared (e.g. "2,000 → 4,000 steps/day"). Never bury the comparison in tiny italic sub-text.
7. **No redundant hero banners** that duplicate what the slide-title already says.
8. **Tight padding for constrained slides:** card padding `0.65–0.9rem`, internal card gap `0.4–0.7rem`, grid gap `0.6–0.75rem`.
9. **Uneven row heights for uneven content:** When one card has significantly heavier content (multi-line stat, longer body), use uneven fr ratios — e.g. `grid-template-rows: 1fr 1fr 1.5fr` — or `grid-row: span 2` for a key card in a 5–6 card grid. Prevents bottom-card clipping.

### Font sizes (minimum) — HARD FLOORS
These are absolute minimums. When in doubt, go above them — never below. Apply to every element in every visuals file.
| Text type | Minimum |
|-----------|---------|
| Source / reference text | `0.80rem` |
| Description / body text | `0.93rem` |
| Supporting / label text | `1.00rem` |
| Heading text | `1.05rem` |

### Stat sizes (minimum)
| Type | Minimum |
|------|---------|
| Hero stat | `4.0rem` |
| Medium stat | `2.4rem` |
| Small inline stat | `1.9rem` |

### Opacity minimums — HARD FLOORS
| Element | Minimum |
|---------|---------|
| Journal / source citations | `rgba(255,255,255,0.80)` — NOT 0.70 |
| Body / finding text | `rgba(255,255,255,0.88)` — NOT 0.80 |
| Supporting labels | `rgba(255,255,255,0.80)` |
| Disclaimer footer (exception) | `0.18` permitted |

**Enforcement rule:** Before finalising any visuals file, check every `.ev-journal`, `.doc-body`, `.sys-body`, `.mech-body`, and any equivalent class against these floors. If text is not clearly readable at arm's length on screen, it is too faint or too small — increase it regardless of whether it technically passes the minimum.

### Grid layout — orphaned card rule
When a grid has N cards where N does not fill the last row evenly, the orphaned card(s) in the last row get squashed by `overflow:hidden`. Fix: match column count to card count so every row is full, OR use `grid-template-columns: repeat(2,1fr)` as the default safe layout for 4–6 cards. A 3-col grid with 5 cards will always orphan one card.

### Animation text visibility
- Label/caption text: min `13px`, `rgba(255,255,255,0.80)`
- Card sub-text: `rgba(255,255,255,0.80)`
- SVG annotations: min `10px`, `rgba(255,255,255,0.60)`
- Opacity 0.50 or below NOT permitted for readable text

### Topbar / slide counter
- Topbar sub-title: min `0.75rem`, `rgba(255,255,255,0.75)`
- Slide counter: min `0.85rem`, `rgba(255,255,255,0.90)`
- Keyboard hint: min `rgba(255,255,255,0.60)`
- Values 0.35 or below NOT permitted

### Intro / closing slides
- "HEALTH EDUCATION" tagline: `rgba(255,255,255,0.70)`
- Series/article label: `rgba(255,255,255,0.70)`
- Closing tagline: `rgba(255,255,255,0.70)`
- Dot in logo: `rgba(255,255,255,0.60)`
- Stat card label: `rgba(255,255,255,0.90)`
- Stat card source: `0.75rem`, `rgba(255,255,255,0.65)`
- Opacity 0.35 or below NOT permitted

### Research card stat standard
Stat boxes must show OUTCOMES — effect sizes, risk changes, response rates — NEVER participant counts or study counts.
- Good: "+12% / +30% mortality risk", "~30% CV event reduction"
- Bad: "1.38M participants", "87 RCTs", "Curvilinear" (descriptive word, not outcome)

Participant counts belong in body detail, not headline stat.

---

## 11. QC PASS — REQUIRED BEFORE EVERY UPLOAD

Run before uploading any article or presenter:

1. **Readability** — no pale text colours, explicit font-weight:400 on body
2. **References** — full citation blocks with DOI and pill links (verified)
3. **Research flags** — all ⚑ claims verified against source before finalising
4. **Graphics** — standalone animation file exists AND presenter has matching inline visual
5. **Article ↔ presenter consistency** — all facts, names, years, citations match
6. **Scroll offset** — `scroll-margin-top: 150px` present on `.article-section`
7. **Visuals visibility** — no source text below opacity 0.70, all font sizes within spec
8. **Slide layout** — multi-row grids have explicit rows; cards have min-height:0 + overflow:hidden; no 4+ vertical blocks per card; sub-text ≤ 12 words
9. **Video length** — teleprompter 600–750 words (4–5 min target)

---

## 12. APPROVED RESEARCH SOURCES

BMJ · NICE guidelines · Cochrane Database · NEJM · The Lancet · JAMA · BMJ Best Practice · PubMed · NHS/NHS Digital · ONS · CDC · WHO · Global Burden of Disease Study · ESC/EAS guidelines

Do NOT use: non-peer-reviewed sources, commercial health sites, forum content.

---

## 13. PRODUCTION SETUP — VIDEO RECORDING

**Method:** OBS Studio (free) compositing camera feed + visuals HTML
- Camera films Dr Paul speaking to camera
- Visuals file (`[article]-visuals.html`) runs full-screen on laptop, composited by OBS behind/beside Dr Paul
- Teleprompter (`[article]-teleprompter.html`) on phone/tablet beside camera lens
- Arrow keys advance visuals screen in sync with teleprompter cues

**Teleprompter placement:** Phone/tablet propped just below or beside camera lens. Dr Paul reads from it, glances at camera. PAUSE markers indicate natural breaks. **Cue boxes appear at the TOP of each segment** — advance the visuals screen first, then read the script while the viewer watches that visual.

---

## 14. OUTSTANDING TASKS (as of April 2026)

### Completed ✅
- All Cardiovascular Series articles 01–07 — article, visuals, teleprompter complete ✅
- All Practical Series articles 08–12 — article, visuals, teleprompter complete ✅
- All Digestive Series articles 13–18 — article, visuals, teleprompter complete ✅
- All 17 teleprompters fully retrofitted — cue-box pattern + educational voice phrase correct ✅
- **Article 12 Alcohol — ALL THREE FILES COMPLETE ✅**
  - Built with new high-impact design pattern (horizontal rows, colour narrative, inline citations, hero-fills-first-screen)
  - Serves as canonical reference for all articles
- **Educational voice retrofit — ALL article HTML files 01–18 complete ✅**
- **Visuals high-impact retrofit — ALL 17 visuals files 01–18 complete ✅**
  - Cardiovascular 01–07 ✅
  - Practical 08–11 ✅
  - Digestive 13–18 ✅
- **Inline superscript citation retrofit — ALL article HTML files 01–18 complete ✅**
- **Hero-first-screen retrofit — ALL article HTML files 01–18 complete ✅**
- masld.html © updated to 2026 ✅
- **ESSENCE trial ⚑ CLEARED** — published NEJM April 2025, PubMed 40305708 ✓
- **Lancet Commission dementia ⚑ CLEARED** — 14 modifiable risk factors confirmed (2024 update, DOI 10.1016/S0140-6736(24)01296-0)
- Pricing confirmed correct (£0/£6/£60/£150) ✅
- **ALL STANDARDS LOCKED IN AND APPLIED (April 2026):**
  - Horizontal-row visuals layout for 4–6 item slides ✅
  - Deck-wide colour narrative (red harm / amber mechanism / green action) ✅
  - Inline superscript citations for every article stat ✅
  - Hero + disclaimer fills first screen, Section 1 below fold ✅
  - Emoji font-family stack for reliable rendering ✅
  - High-impact CTA slide pattern (radial glow + 4 action cards + disclaimer box) ✅
  - Medical term lay-clarification standard ✅
  - Statistical term lay-clarification standard ✅
  - Video length standard (4–5 min max) ✅
  - Teleprompter core standard (messages + stats + pointers) ✅
  - Educational Voice TOP STANDARD ✅
  - Standard video intro using full educational-voice phrase ✅
  - Teleprompter cue-box standard (▶ ADVANCE NOW — then read) ✅

### Outstanding
- [ ] Digestive Series — Article 19+ (topic TBC)
- [ ] Build community forum

### Each new article requires
1. Article HTML
2. Visuals HTML
3. Teleprompter HTML
4. Screen HTMLs (where diagrams needed)

---

## 15. FILE NAMING CONVENTION

| File type | Pattern | Example |
|-----------|---------|---------|
| Article | `[slug].html` | `hypertension.html` |
| Visuals | `[slug]-visuals.html` | `hypertension-visuals.html` |
| Teleprompter | `[slug]-teleprompter.html` | `hypertension-teleprompter.html` |
| Screen file | `[slug-abbrev]-[name]-screen.html` | `ar-sphincter-screen.html` |
| GIF source | `[slug]-[name]-gif.html` | `bloating-gut-gif.html` |

*Note: Old script files (e.g. hypertension-script.html) exist on GitHub for some articles but are superseded by the three-file standard. No new script files are created.*

---

## 16. COMMUNICATION STYLE

- Dr Paul communicates in UPPERCASE
- Prefers brief, direct responses
- Work sessions are long and often cover multiple files simultaneously
- Always confirm article numbers and file names before building
- Flag any inconsistencies found during QC immediately

---

## 17. FILE UPLOAD METHOD

### Uploading TO GitHub
The drag-and-drop upload in Edge incognito works for GitHub. Most reliable methods to get file contents into chat:
- **From local file:** Open in Notepad → Ctrl+A → Ctrl+C → paste into chat
- **From GitHub:** Find file → click Raw → Ctrl+A → Ctrl+C → paste into chat
- **Download from Claude outputs:** Use the Artifact download button — NEVER Ctrl+S or browser File → Save

### Uploading TO Claude Project (for knowledge sync)
⚠️ Drag-and-drop from Edge incognito to this Claude Project captures the browser page (Claude.ai loader HTML) rather than the file. This is a known limitation — see Section 1 above. Real files still exist on GitHub; don't panic.

### Preferred method — fetching files into Claude (session start)
**Use GitHub raw URLs via web_fetch.** This bypasses the Edge incognito loader-stub problem entirely.

Raw URL format:
```
https://raw.githubusercontent.com/pls4286/helfschool/main/[filename].html
```

Example:
```
https://raw.githubusercontent.com/pls4286/helfschool/main/ibd.html
```

Fetch at session start for any files needed. Do NOT rely on project uploads for real file content — they may be loader stubs (~5140 bytes, starting `data-build-id`). Real content always lives on GitHub and is intact.

---

## 18. END-OF-SESSION UPDATE PROTOCOL

At the end of each productive session, update this document to reflect:
- New files built and their status
- Any completed tasks checked off
- New outstanding items added
- Any standard changes or new instructions agreed

Download updated `.md` from outputs and upload to **both GitHub and the Claude Project** to replace the previous version. This step is critical — if it is skipped, the next session will start from stale information.
