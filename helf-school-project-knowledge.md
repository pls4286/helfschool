# helf.school — Project Knowledge Document
*Last updated: April 2026 — updated after major build session. All 10 articles complete with script, visuals, teleprompter. Old presenter files superseded. Project Knowledge document correctly uploaded to helfschool Project.*

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

### Membership pricing (CONFIRMED — must reflect on all pages)
| Tier | Price |
|------|-------|
| Explorer (free) | £0 |
| Member | £6/month or £60/year |
| Lifetime | £150 one-off |

⚠️ `index.html` and membership page currently show INCORRECT prices (£7/£15). Must be updated.

### Members-only content
Full article library · Research analyses · Evidence ratings · Glossary · New content feed · Saved articles · Monthly Q&A

### Community forum (planned, not yet built)
Categories: Living with AF · Medications & Treatments · Lifestyle & Prevention · Research Discussion · Mental Health & Heart · Introductions  
Rules: Be kind · No medical advice · Refer to articles for info · Respect privacy · 999 for emergencies  
Free = read-only. Paid members = full access. Needs: thread creation, member profiles, moderation dashboard, crisis signposting, weekly digest.

---

## 5. ARTICLE INVENTORY

### Cardiovascular Series (Articles 01–07) — ALL COMPLETE
| # | Title | Article HTML | Script | Visuals | Teleprompter |
|---|-------|-------------|--------|---------|--------------|
| 01 | Hypertension | hypertension.html | hypertension-script.html | hypertension-visuals.html | hypertension-teleprompter.html |
| 02 | Cholesterol Explained | cholesterol.html | cholesterol-script.html | cholesterol-visuals.html | cholesterol-teleprompter.html |
| 03 | How Doctors Estimate Heart Attack Risk | heart-attack-risk.html | heart-attack-risk-script.html | heart-attack-risk-visuals.html | heart-attack-risk-teleprompter.html |
| 04 | Statins — Benefits & Risks | statins.html | statins-script.html | statins-visuals.html | statins-teleprompter.html |
| 05 | How to Reduce Cardiovascular Risk with Lifestyle Changes | lifestyle-changes.html | lifestyle-script.html | lifestyle-visuals.html | lifestyle-teleprompter.html |
| 06 | Salt and Blood Pressure | salt-blood-pressure.html | salt-script.html | salt-visuals.html | salt-teleprompter.html |
| 07 | Do Supplements Lower Cholesterol? | supplements-cholesterol.html | supplements-script.html | supplements-visuals.html | supplements-teleprompter.html |

### Articles 08–12 — RESERVED (series TBC, not yet built)

### Digestive Health Series — IN PROGRESS
| # | Title | Article HTML | Script | Visuals | Teleprompter | Screen files |
|---|-------|-------------|--------|---------|--------------|--------------|
| 13 | Acid Reflux | acid-reflux.html | acid-reflux-script.html | acid-reflux-visuals.html | acid-reflux-teleprompter.html | ar-sphincter-screen.html, ar-barretts-screen.html |
| 14 | Bloating | bloating.html | bloating-script.html | bloating-visuals.html | bloating-teleprompter.html | bloating-gut-screen.html, bloating-fodmap-screen.html |
| 15 | IBS | ibs.html | ibs-script.html | ibs-visuals.html | ibs-teleprompter.html | — |
| 16+ | TBC | — | — | — | — | — |

⚠️ Note: IBS article hero currently shows "Article 16" — numbering to be confirmed.

---

## 6. WORKFLOW — NEW ARTICLE

Build in this order:
1. **Article HTML** — four sections, key terms box, references
2. **Script HTML** — `[article]-script.html`
3. **Visuals HTML** — `[article]-visuals.html`
4. **Teleprompter HTML** — `[article]-teleprompter.html`
5. **Screen HTMLs** — standalone full-screen diagrams where needed
6. **GIF source HTMLs** — for PPTX capture (scale 0.62, every 2nd frame, 120 colours, under 1.5MB total)

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

### References standard
Every research item must include:
- Full citation: authors, full title, journal, year, volume, pages, DOI
- Pill links: journal full text + PubMed/PMC (only if verified by web search in same session)
- Use `.ref-block / .ref-full / .ref-links` CSS pattern from supplements-cholesterol.html
- Short link alone is NOT sufficient

⚠️ PubMed IDs are UNRELIABLE from training data. Confirmed wrong IDs found previously. Rule: no PubMed/PMC pill links unless verified by web search in same session. Omit and flag ⚑ if unverified. Journal DOI links acceptable. Paul checks every link before any article goes live.

### Pre-draft verification
Before presenting any article, script, or visuals HTML, verify via web search that every cited study, trial, or statistic: (1) exists, (2) relates to the correct condition, (3) supports the claim made.

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
This compensates for sticky main nav (68px) + sticky jump nav (~46px) + breathing room. Without it, tab navigation scrolls section headings behind the nav bars. Never omit.

### Inline source references
- Min `0.75rem`, `rgba(255,255,255,0.55)` on dark / `#2C2C2C` on light
- The `.source-tag` style (tiny, `rgba(255,255,255,0.25)`) is NOT permitted

---

## 8. VIDEO STANDARDS

### Standard intro (every video, Segment 0)
> "I'm Dr Paul — I spent over twenty years as an NHS GP before I retired in 2019. Today I want to talk to you about [TOPIC]. Now, I do have to say upfront — what I'm giving you here is health education, not medical advice. If anything feels relevant to you personally, please take it to your own doctor. Right — let's get into it."
~15–18 seconds.

### Two-file presenter architecture
Each video requires TWO HTML files:

**(1) Script file** — e.g. `acid-reflux-script.html`
- Dr Paul's screen only
- Full script text, timing, segment labels
- Bold red `.diagram-cue` callout boxes showing filenames for each visual
- No visuals displayed
- Doubles as developer specification

**(2) Visuals file** — e.g. `acid-reflux-visuals.html`
- Camera-facing screen only
- All diagrams, animations, stat cards
- Keyboard navigation (← → arrows)
- No script text

### Teleprompter file — REQUIRED for every article
e.g. `acid-reflux-teleprompter.html`

Spec:
- Default speed: `PX_PER_SEC_BASE = 20`
- Default font: `1.9rem`
- Speed control: 1–6 via +/− buttons
- Font control: A+ / A− buttons
- Visual cue boxes at **bottom of each segment** (not top of next) — amber/red bordered box reading "COMING UP — Screen X: [description] · advance now"
- Auto-scroll via RAF loop
- Touch swipe support for phone/tablet
- Segment jump navigation dots

### Screen files
Standalone full-screen HTML files for camera filming (e.g. `ar-sphincter-screen.html`).
- Full-screen, auto-animate on load
- Bold, large text for filming
- Layout: `flex-start`, `6vh` top padding
- Footer: min `clamp(.65rem,1vw,.80rem)`, `rgba(255,255,255,0.65)`
- Referenced by bold red `.diagram-cue` in script file

### GIF capture settings
Scale 0.62 · Every 2nd frame · 120 colours · Under 1.5MB total PPTX

### Graphics standard
Standalone animation HTMLs = GIF capture sources ONLY. Never embedded directly in articles or presenters. Each presenter contains its own inline recreation in the `visuals{}` object. Both standalone and inline versions must exist for every segment visual.

### Article ↔ presenter consistency
All trial names, years, citation authors, and statistics must match across article and presenter files. Cross-check before upload.

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
2. **References** — full citation blocks with DOI and pill links (verified)
3. **Research flags** — all ⚑ claims verified against source before finalising
4. **Graphics** — standalone animation file exists AND presenter has matching inline visual
5. **Article ↔ presenter consistency** — all facts, names, years, citations match
6. **Scroll offset** — `scroll-margin-top: 150px` present on `.article-section`
7. **Visuals visibility** — no source text below opacity 0.70, all font sizes within spec

---

## 11. APPROVED RESEARCH SOURCES

BMJ · NICE guidelines · Cochrane Database · NEJM · The Lancet · JAMA · BMJ Best Practice · PubMed · NHS/NHS Digital · ONS · CDC · WHO · Global Burden of Disease Study · ESC/EAS guidelines

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

## 13. OUTSTANDING TASKS (updated April 2026)

### Immediate
- [ ] Fix membership pricing on `index.html` and membership page (£7/£15 → £6/£60/£150)
- [ ] Confirm IBS article number (currently shows Article 16 — is this correct?)

### Completed this session ✓
- [x] ibs-teleprompter.html — built and uploaded
- [x] All 10 teleprompter files built (hypertension through ibs)
- [x] All 10 visuals files fixed (opacity + font sizes)
- [x] All 10 article files fixed (scroll-margin-top: 150px)
- [x] Old combined presenter files superseded — removed from master set
- [x] 53-file master set consolidated and uploaded to GitHub
- [x] Project Knowledge document correctly uploaded to helfschool Project
- [x] All corrupted GitHub files replaced with correct versions

### Near-term
- [ ] Continue Digestive Health Series (articles beyond IBS — Article 16+)
- [ ] Determine Articles 08–12 series topic
- [ ] Build community forum

### Each new article requires
1. Article HTML
2. Script HTML
3. Visuals HTML
4. Teleprompter HTML
5. Screen HTMLs (where diagrams needed)
6. GIF source HTMLs (for PPTX)

---

## 14. FILE NAMING CONVENTION

| File type | Pattern | Example |
|-----------|---------|---------|
| Article | `[slug].html` | `hypertension.html` |
| Script | `[slug]-script.html` | `hypertension-script.html` |
| Visuals | `[slug]-visuals.html` | `hypertension-visuals.html` |
| Teleprompter | `[slug]-teleprompter.html` | `hypertension-teleprompter.html` |
| Screen file | `[slug-abbrev]-[name]-screen.html` | `ar-sphincter-screen.html` |
| GIF source | `[slug]-[name]-gif.html` | `bloating-gut-gif.html` |

---

## 15. FILE ARCHITECTURE — CURRENT STANDARD

Each article now has exactly FOUR associated video files (no more combined presenter files):

| File | Purpose |
|------|---------|
| `[slug].html` | Published article (public-facing) |
| `[slug]-script.html` | Dr Paul's filming screen — full script + timing + diagram cues |
| `[slug]-visuals.html` | Camera-facing screen — all diagrams, animations, cards |
| `[slug]-teleprompter.html` | Scrolling teleprompter — speed 20px/s, visual cues at segment ends |

Screen files (`[slug]-screen.html`) are additional — only where specific diagrams are needed for filming.

Old combined presenter files (e.g. `hypertension-presenter.html`) are SUPERSEDED. Do not build new ones. Do not reference them.

---

## 16. COMMUNICATION STYLE

- Dr Paul communicates in UPPERCASE
- Prefers brief, direct responses
- Work sessions are long and often cover multiple files simultaneously
- Always confirm article numbers and file names before building

---

## 17. CRITICAL — SAVING AND UPLOADING FILES

### The only safe way to download a file from Claude
**Always use the download arrow button on the Artifact panel** (top-right corner of the preview panel).  
**NEVER use Ctrl+S or File → Save in the browser.** This saves the Claude.ai webpage wrapper, not the file content. The resulting file will appear to work but contains Claude.ai code, not helf.school code.

### Uploading to GitHub
- Go to github.com/pls4286/helfschool/upload/main
- Drag and drop files — uploading a file with the same name automatically overwrites the old version
- No deletion needed to replace a file

### Uploading to Project Knowledge
- Go to helfschool Project in Claude
- Click the + button beneath "How can I help you today"
- Upload the `.md` file — confirm receipt on the confirmation screen
- This makes the document available automatically in every future session

### End-of-session update protocol — MANDATORY
At the end of every session where new articles are built, decisions are made, or standards change:
1. Claude updates this Project Knowledge document with all changes
2. Paul downloads it using the Artifact download button
3. Paul uploads it to GitHub (overwrites old version automatically)
4. Paul uploads it to the helfschool Project using the + button (replaces old version)

**This is the only way to ensure continuity between sessions. Claude cannot access previous conversations. This document is the single source of truth.**
