# helf.school — Project Knowledge
**Owner:** Dr Paul — retired NHS GP (ill-health retired end 2019), 20+ years GP experience. Building helf.school as a health education membership website presenting medical conditions and evidence-based research in plain English for the general public. Explicitly framed as health education, not medical advice.

**Communication style:** Dr Paul writes in uppercase and prefers brief, direct responses.

---

## SITE & DESIGN SYSTEM

**GitHub:** pls4286.github.io/helfschool (repo: pls4286/helfschool)
**Live site:** https://pls4286.github.io/helfschool/index.html
**Browser:** Microsoft Edge (accesses Claude via incognito due to extension conflict)
**Upload method:** Drag-and-drop at github.com/pls4286/helfschool/upload/main (Edge incognito)

**Colours:**
- Navy #1B2A4A · Coral #E8634A · Cream #FAF7F2 · Sage #7A9E87 · Amber #E8A84A
- Category colours: Cardio #C8423A · Neuro #6B5EA8 · Digestive #D47C3A · Fatigue #3A8A7A · Medical #2E6BA8 · Practical #7A6A2E

**Fonts:** Fraunces (serif headings) + DM Sans (body) — DM Sans minimum wght@400;500;600;700; **never weight 300**

**Logo:** open-book SVG + "HEALTH EDUCATION" tagline

**Membership pricing (confirmed):** £0 Free / £6/month or £60/year Member / £150 Lifetime

---

## ARTICLE INVENTORY & COMPLETION STATUS

### Three files required per article:
1. Article HTML (website page — lives on GitHub only, never in Claude project by design)
2. Visuals HTML (camera-facing, keyboard nav, no script)
3. Teleprompter HTML (RAF auto-scroll, 1.9rem font, speed 1–6, A+/A−, touch swipe, segment dots)

### Cardiovascular Series (Articles 01–07) — ALL COMPLETE
| # | Title | Status |
|---|-------|--------|
| 01 | Hypertension | All 3 files retrofitted |
| 02 | Cholesterol Explained | All 3 files retrofitted |
| 03 | How Doctors Estimate Heart Attack Risk | All 3 files retrofitted |
| 04 | Statins — Benefits & Risks | All 3 files retrofitted |
| 05 | How to Reduce Cardiovascular Risk with Lifestyle Changes | All 3 files retrofitted |
| 06 | Salt and Blood Pressure | All 3 files retrofitted |
| 07 | Do Supplements Lower Cholesterol? | All 3 files retrofitted |

### Practical Health Series (Articles 08–12)
| # | Title | Status |
|---|-------|--------|
| 08 | Mediterranean Diet | All 3 files retrofitted |
| 09 | Sleep | All 3 files retrofitted |
| 10 | Exercise | All 3 files retrofitted — visuals now 12 slides (research split into 2) |
| 11 | Stress | Visuals + teleprompter in project — article on GitHub. NOT YET RETROFITTED. |
| 12 | Alcohol | NOT YET STARTED |

### Digestive Health Series (Articles 13–18) — ALL COMPLETE
Articles 13 (Acid Reflux), 14 (IBD), 15 (IBS), 16 (Bloating), 17 (MASLD), 18 (Coeliac) — all 3 files confirmed complete and on GitHub. Educational voice retrofit confirmed complete.

### Extended Digestive / New Series (Articles 19–20)
| # | Title | Status |
|---|-------|--------|
| 19 | Gallstones | Teleprompter + visuals built |
| 20 | Diverticular Disease | Teleprompter + visuals built |

**Article 21 (Constipation):** DO NOT BUILD until all retrofits complete.

---

## RETROFIT CHECKLIST (applied to every article)

### Article HTML
1. Font imports: remove wght@300, DM Sans 400–700 only, Fraunces 400/600/700
2. `body`: font-weight:400 explicit; color:#2C2C2C
3. No fadeUp/opacity:0 animations on article body sections
4. Hero subtitle min rgba(255,255,255,0.85); meta min rgba(255,255,255,0.80)
5. Breadcrumb — navy background bar, rgba(255,255,255,0.75) min
6. Amber disclaimer bar between hero and jump-nav
7. Standard nav (open-book SVG logo, DM Sans tagline, full links)
8. Jump nav (sticky below header, section anchors with navy circle numbers)
9. Key terms — 2-column grid, defs rgba(255,255,255,0.90) min, amber term labels
10. Section numbers — navy circle (not coral, not amber)
11. Section 2 — 2×2 stat grid (outcome stats only — never participant counts)
12. Section 4 — navy research cards with rc-stat-row / rc-title / rc-body
13. Drug brand names in brackets after generic
14. Full references section with DOI pill links and inline superscript citations
15. Educational voice throughout — full phrase only
16. Copyright 2026
17. Disclaimer — coral-light box with SVG icon

### Navy Research Card Standard (LOCKED)
```css
.rc-stat { font-size:2.4rem; font-weight:700; color:#d4b84a; }
.rc-stat-label { font-size:1.1rem; color:#fff; font-weight:700; }
.rc-title { font-family:'Fraunces'; font-size:1.3rem; font-weight:700; color:var(--coral); }
.rc-body { font-size:1.05rem; line-height:1.75; color:rgba(255,255,255,.92); }
```

### Visuals HTML — Row card sizing by row count (CONFIRMED WORKING)

| Rows | Gap | Padding | Icon col | Icon size | Title | Body |
|------|-----|---------|----------|-----------|-------|------|
| 3 | .65rem | 1rem 1.5rem | 72px | 2.8rem | 1.5rem | 1rem |
| 4 | .65rem | 1rem 1.5rem | 64px | 2.8rem | 1.4rem | .98rem |
| 5 | .45rem | .70rem 1.2rem | 52px | 2.2rem | 1.2rem | .93rem |
| 6 | .35rem | .60rem 1.1rem | 52px | 1.9rem | 1.1rem | .88rem |

- ALL row cards: `align-items:start` (NEVER center)
- `-webkit-line-clamp:2` on body text
- `padding-top:.1rem` on icons

---

## LOCKED STANDARDS (CRITICAL — apply every session)

### Educational voice (TOP PRIORITY)
helf.school *describes* what medicine knows — never instructs the reader.

**FORBIDDEN:**
- "speak to your GP / please tell your GP / ask your GP" (as instructions)
- "you should / you must / always tell your doctor"
- "seek advice / seek urgent care"
- "take it to your doctor"
- Any shortened version of the disclaimer phrase
- "Take what's useful to your doctor"

**REQUIRED full phrase:**
"a conversation for you to have with your GP or healthcare professional"
— ALWAYS the complete phrase, never shortened.

### Video intro standard (Segment 0)
"I'm Dr Paul — I spent over twenty years as an NHS GP before I retired in 2019. Today I want to talk to you about [TOPIC]. Now, I do have to say upfront — what I'm giving you here is health education, not medical advice. Anything personally relevant is a conversation for you to have with your GP or healthcare professional. Right — let's get into it."

### Cue box standard (teleprompter)
Cue box always *precedes* script lines for its segment — label: `▶ ADVANCE NOW — then read`. Viewer sees slide before Dr Paul speaks. stress-teleprompter.html is the reference file.

### ev-stat-box rule — NEVER add overflow:hidden
**`.ev-stat-box` must never have `overflow:hidden`.** The parent `.ev-card` already provides overflow containment. Adding it to the box clips multi-part stat strings (e.g. `+12% / +30%`, `+1.8 / +4.5y`, `–18% / –25%`) at large font sizes, making them invisible. If word-label capping is needed, apply `overflow:hidden` to the `.ev-stat` element only.

### ev-card visibility rule — always opacity:1
**`.ev-card` default must be `opacity:1; transform:translateY(0)`** — never `opacity:0`. The fade-in animation via `.vis` class is a bonus enhancement. If animation misfires, cards must still be readable. Apply this to ALL visuals files.

### ev-stage card count rule — max 5 per slide
**Maximum 5 ev-cards per ev-stage slide.** If 6 studies are needed, split into two 3-card slides with separate slide titles. Six cards cause height overflow at typical presentation resolution, and long stat strings overflow the 170px stat-box.

### Long stat string sizing
These stat strings must use `font-size:1.4rem` inline (not the default 1.75rem–2.2rem):
- `+1.8 / +4.5y`
- `–18% / –25%`
- `+12% / +30%`
- Any stat string over ~8 characters at default size

### ev-num word label rule
- Short word ("Switch", "Lasting") → font-size:2rem
- Two-line phrase ("Not supported") → font-size:1.7rem; line-height:1.2
- Numbers (−22%, −47%) → standard size
- Long fractions → font-size:1.4rem

### CTA slide standard (visuals)
- Horizontal rows (NOT chip cards), NO `.cta-icon` pulsing emoji
- Structure: `.cta-wrap-v2` grid 3 rows + `.cta-rows-v2` 4 rows, both `min-height:0; overflow:hidden`
- Headline: clamp(2rem,3.8vw,3.2rem); subline: clamp(.95rem,1.5vw,1.2rem)
- 4 action rows: icon 1.7rem + Fraunces bold label + body text (line-clamp:2) + word stat
- Disclaimer: "Anything personally relevant is a conversation for you to have with your GP or healthcare professional."

### rc-stat-label standard
MUST be bold white (font-weight:700; color:#fff). Number + finding = ONE complete statement.

### rc-title standard
MUST be coral, 1.3rem, Fraunces, weight 700. Human-readable key takeaway.

---

## TELEPROMPTER FORMAT STANDARD

Standard format ONLY — no custom scroll engines. Reference: stress-teleprompter.html.

**Required elements:**
- RAF auto-scroll with speed levels [8,14,20,28,38,52], speed index default 2 (display "3")
- Font size 1.9rem default, A+/A− controls
- Segment dots (right side, click to jump)
- `.seg-label` with `data-seg` attribute for each segment
- `.cue-box` with `.cue-label` ("▶ ADVANCE NOW — then read") and `.cue-text`
- `.line` class for all script lines
- `.pause` inline marker for deliberate pauses

**If a teleprompter is in non-standard format (e.g. `.seg`/`.cue` divs, different scroll mechanism), rebuild it entirely in standard format.**

---

## READABILITY STANDARDS

### Body text
- Color: #2C2C2C, font-weight:400 explicit
- Pale colours (#374151, #4B5563, #555) not permitted anywhere

### Hero
- Subtitle: min rgba(255,255,255,0.85)
- Meta items: min rgba(255,255,255,0.80)

### Key Terms (navy box)
- Term labels: min 0.88rem, font-weight 700, #d4b84a (practical) or var(--coral)
- Definitions: min 0.92rem, rgba(255,255,255,0.90)

### Presenter visuals
- Topbar subtitle: min 0.75rem, rgba(255,255,255,0.75)
- Slide counter: min 0.85rem, rgba(255,255,255,0.90)
- Source attributions: min 0.75rem, rgba(255,255,255,0.55)

---

## REFERENCES STANDARD

- Full citation: authors, title, journal, year, vol, pages, DOI
- Pill links: journal full text + PubMed/PMC only if verified by web search in same session
- Inline superscript citations on every stat/claim in prose
- Research card stats: OUTCOMES only — never participant counts as headline stat
- Good: "+30% CV event reduction" | Bad: "7,447 participants"

---

## DRUG NAMING (all articles)
Generic first, brand in brackets:
atorvastatin (Lipitor) · rosuvastatin (Crestor) · lovastatin (Mevacor) · zopiclone (Zimovane) · zolpidem (Stilnoct) · warfarin (Coumadin) · semaglutide (Ozempic) · infliximab (Remicade)

## LAY-CLARIFICATION STANDARD
Plain-English brackets required for: HR (hazard ratio) · OR (odds ratio) · RR (relative risk) · NNT (number needed to treat) · CI (confidence interval) · HbA1c · QRISK · MVPA · VO₂ max

---

## PRODUCTION WORKFLOW

**File fetch:** `https://raw.githubusercontent.com/pls4286/helfschool/main/[filename].html`
Article HTML files live on GitHub only — never in Claude project by design.

**Pre-draft verification:** Before any article/script/visuals, verify every cited study via web search: (1) exists, (2) correct condition, (3) supports claim, (4) URL/DOI resolves. Never include unverified links.

**QC before upload:**
1. Readability — no pale text
2. References — full citations with DOI
3. Research flags — all ⚑ verified
4. Graphics — standalone animation exists where needed
5. Article ↔ presenter consistency — all facts, stats, citations match

**File corruption pattern:** Edge incognito uploads sometimes capture Claude.ai loader HTML (~5,140 bytes). Fetch real content via GitHub raw URLs to verify.

**Large file crash risk:** Build one file per turn, confirm before proceeding.

**File delivery:** Download button in Claude interface, or: Open in Notepad → File → Save As → [filename].html with 'All Files' type selected.

---

## PENDING WORK

### Next up
1. **Article 11 — Stress:** Article on GitHub. Visuals + teleprompter in project. All 3 files need retrofit.
2. **Article 12 — Alcohol:** Article not yet started. All 3 files needed.

### Ongoing
- Teleprompter cue box audit — Articles 01–06 built before standard; verify cue format
- CTA slide audit — verify all visuals 01–20 use horizontal row standard (not chips)
- ev-card opacity audit — verify all visuals files have opacity:1 default (not opacity:0)
- ev-stat-box audit — verify no overflow:hidden on ev-stat-box in any file

### Do not build
- Article 21 (Constipation) — wait until all series retrofits complete

---

## SITE ARCHITECTURE
- **Public:** Homepage, About Dr Paul, Conditions preview, Sample articles ×3, Newsletter, Disclaimer, Privacy, Contact
- **Members only:** All condition guides, research analyses, evidence ratings, glossary, new content feed, saved articles, monthly Q&A
- **Community:** Forum with categories, member profiles, thread creation, moderation, crisis signposting, weekly digest
- **Admin:** CMS, member management, payments, email automation, analytics, SEO, review log

## APPROVED RESEARCH SOURCES
BMJ · NICE guidelines · Cochrane Database · NEJM · The Lancet · JAMA · BMJ Best Practice · PubMed · NHS/NHS Digital · ONS · CDC · WHO · Global Burden of Disease Study · ESC/EAS guidelines

---

*Last updated: April 2026 — end of session covering Articles 07–10 retrofit + new locked standards (ev-card opacity, ev-stat-box overflow, ev-stage card count limit)*
