# helf.school — Project Knowledge Document
*Last updated: April 2026 — comprehensive reference for all Claude sessions*

---

## 1. PROJECT OVERVIEW

**Site:** helf.school  
**GitHub:** pls4286/helfschool — live at pls4286.github.io/helfschool  
**Upload method:** Drag-and-drop at github.com/pls4286/helfschool/upload/main  
**Browser:** Microsoft Edge (incognito — extension conflict)  
**Owner:** Dr Paul — retired NHS GP, over 20 years experience, ill-health retired end of 2019  

**Mission:** "To give every person access to clear, honest, evidence-based health education — helping them become a more informed, empowered participant in their own care."

**Tone:** Informative, empowering, non-dictatorial, evidence-led, never prescriptive. Never use the word "eliminated". Content is explicitly health education — NOT medical advice.

**Audience:** General public.

---

## 2. DR PAUL

- Retired NHS GP, over 20 years experience
- Tier One ill-health retired by Chief Medical Officer for NHS at end of 2019 (stress)
- Happily married 38 years, four adult children
- Core philosophy: good medicine begins with truly listening
- Felt like "a square peg in a round hole" by 2018 as appointment times shortened
- Presents on video as "Dr Paul" (surname not used publicly)

---

## 3. DESIGN SYSTEM

### Colours
| Token | Hex |
|-------|-----|
| Navy | #1B2A4A |
| Coral | #E8634A |
| Cream | #FAF7F2 |
| Sage | #7A9E87 |
| Amber | #E8A84A |

### Category Colours
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

## 4. SITE ARCHITECTURE

### Public pages
- `index.html` — homepage
- `helf-school-conditions.html` — conditions library
- `helf-school-membership.html` — membership pricing

### Membership pricing (CONFIRMED CORRECT as of April 2026)
| Tier | Price |
|------|-------|
| Explorer (free) | £0 |
| Member | £6/month or £60/year |
| Lifetime | £150 one-off |

✅ Both `index.html` and `helf-school-membership.html` confirmed correct.

### Members-only content
Full article library · Research analyses · Evidence ratings · Glossary · New content feed · Saved articles · Monthly Q&A

### Community forum (planned, not yet built)
Categories: Living with AF · Medications & Treatments · Lifestyle & Prevention · Research Discussion · Mental Health & Heart · Introductions  
Rules: Be kind · No medical advice · Refer to articles for info · Respect privacy · 999 for emergencies  
Free = read-only. Paid members = full access. Needs: thread creation, member profiles, moderation dashboard, crisis signposting, weekly digest.

---

## 5. ARTICLE INVENTORY

### Cardiovascular Series (Articles 01–07) — ALL COMPLETE
| # | Title | Article HTML | Visuals | Teleprompter |
|---|-------|-------------|---------|--------------|
| 01 | Hypertension | hypertension.html | hypertension-visuals.html | hypertension-teleprompter.html |
| 02 | Cholesterol Explained | cholesterol.html | cholesterol-visuals.html | cholesterol-teleprompter.html |
| 03 | How Doctors Estimate Heart Attack Risk | heart-attack-risk.html | heart-attack-risk-visuals.html | heart-attack-risk-teleprompter.html |
| 04 | Statins — Benefits & Risks | statins.html | statins-visuals.html | statins-teleprompter.html |
| 05 | How to Reduce Cardiovascular Risk with Lifestyle Changes | lifestyle-changes.html | lifestyle-visuals.html | lifestyle-teleprompter.html |
| 06 | Salt and Blood Pressure | salt-blood-pressure.html | salt-visuals.html | salt-teleprompter.html |
| 07 | Do Supplements Lower Cholesterol? | supplements-cholesterol.html | supplements-visuals.html | supplements-teleprompter.html |

### Practical Health Series (Articles 08–12) — PLANNED
| # | Title | Status |
|---|-------|--------|
| 08 | The Mediterranean Diet | Not yet built |
| 09 | Sleep — Why It Matters More Than You Think | Not yet built |
| 10 | Exercise and Movement — The Evidence | Not yet built |
| 11 | Stress and the Body | Not yet built |
| 12 | Alcohol — What the Evidence Actually Shows | Not yet built |

**Series colour:** Practical `#7A6A2E`  
**Series rationale:** Each article covers one modifiable factor at the intersection of multiple conditions — actionable without a prescription or referral. Mediterranean diet is Article 08 as it is referenced across cardiovascular, MASLD, and digestive articles.

### Digestive Health Series (Articles 13–17+) — IN PROGRESS
| # | Title | Article HTML | Visuals | Teleprompter | Screen files |
|---|-------|-------------|---------|--------------|--------------|
| 13 | Acid Reflux | acid-reflux.html | acid-reflux-visuals.html | acid-reflux-teleprompter.html | ar-sphincter-screen.html, ar-barretts-screen.html |
| 14 | Bloating | bloating.html | bloating-visuals.html | bloating-teleprompter.html | bloating-gut-screen.html, bloating-fodmap-screen.html |
| 15 | IBD: Crohn's Disease and Ulcerative Colitis | ibd.html | ibd-visuals.html | ibd-teleprompter.html | ibd-gut-screen.html |
| 16 | IBS | ibs.html | ibs-visuals.html | ibs-teleprompter.html | — |
| 17 | Fatty Liver Disease (MASLD) | masld.html ⚑ in progress | — | — | — |
| 18+ | Coeliac disease (planned next) | — | — | — | — |

**Article 17 notes:** masld.html built April 2026. ESSENCE trial reference flagged ⚑ — verify publication status before going live. Drug brand names included throughout. Waist circumference thresholds included in Sections 1 and 3.

---

## 6. WORKFLOW — NEW ARTICLE

Build in this order:
1. **Pre-draft verification** — web search every key claim, statistic, and study before writing
2. **Article HTML** — four sections, key terms box, references
3. **Visuals HTML** — `[article]-visuals.html`
4. **Teleprompter HTML** — `[article]-teleprompter.html`
5. **Screen HTMLs** — standalone full-screen diagrams where needed

Old script files (e.g. ibd-script.html) are superseded. Three files per article is the current standard.

---

## 7. ARTICLE STANDARDS

### Structure
1. What is it?
2. Why does it matter? (max 5 bullets)
3. What your doctor might do
4. What the research shows

Key Terms box sits **between sections 1 and 2** — navy background, alphabetical, plain English definitions.

"Putting it all together" — always navy box, italic text, **bold closing line**.

Research claims flagged ⚑ for Paul review before publishing.

### Drug naming standard
Every generic drug name must be followed immediately by the brand name(s) in brackets. Examples: semaglutide (Ozempic, Wegovy), atorvastatin (Lipitor), infliximab (Remicade), mesalazine (Asacol, Octasa). Apply to all articles.

### References standard
Every research item must include:
- Full citation: authors, full title, journal, year, volume, pages, DOI
- Pill links: journal full text + PubMed/PMC — **only if verified working by web search in the same session**
- Use `.ref-block / .ref-full / .ref-links` CSS pattern
- Short link alone is NOT sufficient

⚠️ PubMed IDs are UNRELIABLE from training data. Rule: no PubMed/PMC pill links unless verified by web search in same session. Omit and flag ⚑ if unverified.

⚠️ Every URL must be verified to actually resolve to the correct article before inclusion. Never include a link that has not been confirmed working in the same session.

### Pre-draft verification
Before presenting any article, script, or visuals HTML, verify via web search that every cited study, trial, or statistic: (1) exists, (2) relates to the correct condition, (3) supports the claim made, (4) every URL resolves correctly.

### Readability
- Body text: `#2C2C2C`, explicit `font-weight:400`
- Pale colours NOT permitted: `#374151`, `#4B5563`, `#555`
- DM Sans minimum `wght@400` — never 300
- No `fadeUp` or `opacity:0` animations on body sections — content must be immediately visible

### Hero visibility
- Hero subtitle: `rgba(255,255,255,0.85)`
- Meta items: `rgba(255,255,255,0.80)`
- Breadcrumb: `rgba(255,255,255,0.75)`
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

### Inline source references
- Min `0.75rem`, `rgba(255,255,255,0.55)` on dark / `#2C2C2C` on light
- The `.source-tag` style (tiny, `rgba(255,255,255,0.25)`) is NOT permitted

---

## 8. VIDEO STANDARDS

### Standard intro (every video, Segment 0)
> "I'm Dr Paul — I spent over twenty years as an NHS GP before I retired in 2019. Today I want to talk to you about [TOPIC]. Now, I do have to say upfront — what I'm giving you here is health education, not medical advice. If anything feels relevant to you personally, please take it to your own doctor. Right — let's get into it."
~15–18 seconds.

### Three files per article (current standard)
1. **Article HTML** — website page
2. **Visuals HTML** — camera-facing screen, keyboard nav (← →), no script text
3. **Teleprompter HTML** — scrolling teleprompter for filming

### Teleprompter spec
- Default speed: `PX_PER_SEC_BASE = 20`, speed levels `[8,14,20,28,38,52]`
- Default font: `1.9rem`
- Speed control: 1–6 via +/− buttons
- Font control: A+ / A− buttons
- Visual cue boxes at **bottom of each segment** — amber/red bordered box: "COMING UP — Screen X: [description] · advance now"
- Auto-scroll via RAF loop
- Touch swipe support for phone/tablet
- Segment jump navigation dots

### Screen files
Standalone full-screen HTML files for camera filming.
- Full-screen, auto-animate on load, bold for filming
- Layout: `flex-start`, `6vh` top padding
- Footer: min `clamp(.65rem,1vw,.80rem)`, `rgba(255,255,255,0.65)`

### Visuals research slide standard
In every visuals HTML file, the "What the research shows" slide must have each research card's key finding highlighted — the single most important number, percentage, or conclusion must be bold and in the accent colour. Never bury the headline finding in plain body text.

---

## 9. VISUALS FILE STANDARDS

### Screen presence
All visuals HTML files must fill the screen boldly and be readable at distance:
- Stage padding: maximum `0.6rem 0.75rem`
- No artificial `max-width` below `100%` on content wrappers

### Font sizes (minimum)
| Text type | Minimum |
|-----------|---------|
| Source / reference text | `0.78rem` |
| Description / body text | `0.93rem` |
| Supporting / label text | `1.00rem` |
| Heading text | `1.05rem` |

### Stat figure sizes (minimum)
| Type | Minimum |
|------|---------|
| Hero stat | `4.0rem` |
| Medium stat | `2.4rem` |
| Small inline stat | `1.9rem` |

### Reference / source opacity (minimum)
| Element | Minimum |
|---------|---------|
| Primary source citations | `rgba(255,255,255,0.70)` |
| Supporting labels | `rgba(255,255,255,0.75)` |
| Body text | `rgba(255,255,255,0.80)` |
| Disclaimer footer (exception) | `0.18` permitted |

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

### Visuals impact
- SVG diagrams fill min 40% available width
- SVG labels min 13px, key terms min 16px, stroke widths min 2.5px
- Key stats min 4rem
- Card text min 0.88rem
- Every visual must communicate core message at a glance from 3 feet

---

## 10. QC PASS — REQUIRED BEFORE EVERY UPLOAD

Run before uploading any article or presenter:

1. **Readability** — no pale text colours, explicit font-weight:400 on body
2. **References** — full citation blocks with DOI and pill links (verified working in same session)
3. **Research flags** — all ⚑ claims verified against source before finalising
4. **Links** — every URL confirmed to resolve to the correct article
5. **Drug names** — all generic drug names have brand names in brackets
6. **Article ↔ visuals consistency** — all facts, names, years, citations match
7. **Scroll offset** — `scroll-margin-top: 150px` present on `.article-section`
8. **Visuals visibility** — no source text below opacity 0.70, all font sizes within spec

---

## 11. APPROVED RESEARCH SOURCES

BMJ · NICE guidelines · Cochrane Database · NEJM · The Lancet · JAMA · BMJ Best Practice · PubMed · NHS/NHS Digital · ONS · CDC · WHO · Global Burden of Disease Study · ESC/EAS guidelines · EASL/EASD/EASO guidelines · BSG guidelines

Do NOT use: non-peer-reviewed sources, commercial health sites, forum content.

---

## 12. PRODUCTION SETUP — VIDEO RECORDING

**Method:** OBS Studio (free) compositing camera feed + visuals HTML
- Camera films Dr Paul speaking to camera
- Visuals file (`[article]-visuals.html`) runs full-screen on laptop, composited by OBS behind/beside Dr Paul
- Teleprompter (`[article]-teleprompter.html`) on phone/tablet beside camera lens
- Arrow keys advance visuals screen in sync with teleprompter cues

**Teleprompter placement:** Phone/tablet propped just below or beside camera lens. Dr Paul reads from it, glances at camera. PAUSE markers indicate natural breaks. Visual cue boxes at segment ends signal when to advance the visuals screen.

---

## 13. OUTSTANDING TASKS (as of April 2026)

### Completed ✅
- All Cardiovascular Series articles 01–07 — article, visuals, teleprompter complete
- All Digestive Series articles 13–16 — article, visuals, teleprompter complete
- Article 15 IBD — all files including ibd-gut-screen.html complete
- Article 17 MASLD — article HTML built, visuals and teleprompter still needed
- Pricing confirmed correct on index.html and membership page
- Project knowledge document updated April 2026

### Immediate — Article 17 MASLD
- [ ] Build masld-visuals.html
- [ ] Build masld-teleprompter.html
- [ ] Verify ESSENCE trial publication status before going live ⚑

### Near-term
- [ ] Practical Health Series — Articles 08–12 (Mediterranean diet, Sleep, Exercise, Stress, Alcohol)
- [ ] Digestive Series — Article 18 Coeliac disease
- [ ] Continue Digestive Series 19+
- [ ] Build community forum

### Each new article requires
1. Article HTML
2. Visuals HTML
3. Teleprompter HTML
4. Screen HTMLs (where diagrams needed)

---

## 14. FILE NAMING CONVENTION

| File type | Pattern | Example |
|-----------|---------|---------|
| Article | `[slug].html` | `hypertension.html` |
| Visuals | `[slug]-visuals.html` | `hypertension-visuals.html` |
| Teleprompter | `[slug]-teleprompter.html` | `hypertension-teleprompter.html` |
| Screen file | `[slug-abbrev]-[name]-screen.html` | `ar-sphincter-screen.html` |

---

## 15. COMMUNICATION STYLE

- Dr Paul communicates in UPPERCASE
- Prefers brief, direct responses
- Work sessions are long and often cover multiple files simultaneously
- Always confirm article numbers and file names before building
- Flag any inconsistencies found during QC immediately

---

## 16. FILE UPLOAD METHOD

The drag-and-drop upload in Edge incognito captures the browser page rather than the file. Reliable methods:
- **From local file:** Open in Notepad → Ctrl+A → Ctrl+C → paste into chat
- **From GitHub:** Find file → click Raw → Ctrl+A → Ctrl+C → paste into chat
- **Download from Claude outputs:** Use the Artifact download button — NEVER Ctrl+S or browser File → Save

---

## 17. END-OF-SESSION UPDATE PROTOCOL

At the end of each productive session, update this document to reflect:
- New files built and their status
- Any completed tasks checked off
- New outstanding items added
- Any standard changes or new instructions agreed
Download updated .md from outputs and upload to both GitHub and the Claude Project to replace the previous version.
