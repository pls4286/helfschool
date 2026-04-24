# helf.school — Project Knowledge
**Last updated: April 2026**

---

## ⚠️ DOCUMENT INTEGRITY — CLAUDE MUST READ THIS BEFORE ANY SESSION WORK

**This document has 25 numbered sections. Minimum expected line count: ~650 lines.**

When updating this document at the end of any session, Claude MUST:
1. Run `wc -l` on the new file before presenting it to Dr Paul
2. Confirm the new line count is **equal to or greater than** the previous version
3. Verify all 25 sections are present by scanning for each section heading
4. **Never deliver a shorter version without explicitly stating which sections were reduced, why, and receiving Dr Paul's confirmation before delivery**

If the new line count is lower and Claude cannot account for every removed line, the file is incomplete. Do not deliver it. Identify what is missing and restore it first.

Dr Paul cannot be expected to check line counts or audit section completeness himself. This is entirely Claude's responsibility. Delivering a shorter file without explanation is a failure.

**All 25 sections must be present:**
Section 0 · Section 1 (Project Overview) · Section 2 (Design System) · Section 3 (Article Inventory — source of truth) · Section 4 (Site Files Status) · Section 5 (Educational Voice) · Section 6 (Video Intro Standard) · Section 7 (Production Workflow) · Section 8 (Article HTML Standards) · Section 9 (Visuals HTML Standards) · Section 10 (Teleprompter Standards) · Section 11 (Graphics & Animation) · Section 12 (QC Checklist) · Section 13 (File Delivery & Upload) · Section 14 (Approved Research Sources) · Section 15 (Membership Pricing) · Section 16 (Pre-Draft Verification Rule) · Section 17 (Retrofit Status) · Section 18 (Key Learning Points) · Section 19 (Outstanding Tasks) · Section 20 (Constipation Reference Log) · Section 21 (Claude Project File Notes) · Section 22 (Session Start Rules) · Section 23 (Article-Specific Notes) · Section 24 (Planning Notes) · Section 25 (Process Notes)

---

## SECTION 0 — SESSION START PROTOCOL (READ FIRST — NO EXCEPTIONS)

**MANDATORY FIRST ACTION every session:** Read this file AND `helf-school-session-start-rules.md` IN FULL before any output, checks, or assessments. This step is non-negotiable because these files contain critical rules — including file integrity rules and the article inventory which is the source of truth. Reading after producing output is too late.

**Critical file integrity rule:** Files in the Claude project that are approximately 5,140 bytes and begin with "data-build-id" are Edge incognito loader stubs captured during upload — they are NOT the real file and are NOT corrupted. Never flag these as corrupted. Always verify real content via GitHub raw URL before any assessment. The article inventory in this document is the authoritative source of truth for what is built — not file sizes.

**GitHub raw URL format:** `https://raw.githubusercontent.com/pls4286/helfschool/main/[filename].html`

---

## 1. PROJECT OVERVIEW

**Owner:** Dr Paul — retired NHS GP, 20+ years experience. Tier One ill health retired end of 2019 by the Chief Medical Officer for the NHS.

**Platform:** helf.school — health education membership website.

**Mission:** "To give every person access to clear, honest, evidence-based health education — helping them become a more informed, empowered participant in their own care."

**Core philosophy:** Health education — not medical advice. helf.school describes what medicine knows and what services exist. It never instructs the reader what to do. Good medicine begins with truly listening — that philosophy underpins everything on the site.

**GitHub repo:** pls4286/helfschool
**Live site:** https://pls4286.github.io/helfschool/index.html
**Upload path:** github.com/pls4286/helfschool/upload/main
**Browser:** Microsoft Edge (Dr Paul uses incognito tab due to extension conflict with standard window)

---

## 2. DESIGN SYSTEM

### Colours
- Navy: `#1B2A4A`
- Coral: `#E8634A`
- Cream: `#FAF7F2`
- Sage: `#7A9E87`
- Amber: `#E8A84A`

### Category colours
- Cardiovascular: `#C8423A`
- Neurological: `#6B5EA8`
- Digestive: `#D47C3A`
- Fatigue: `#3A8A7A`
- Medical Decision: `#2E6BA8`
- Practical Health (series): `#7A6A2E`

### Fonts
- Headings: Fraunces (serif)
- Body: DM Sans — minimum weights required: `wght@400;500;600;700`
- **Never use weight 300 anywhere in body text** — not permitted in articles, visuals, or teleprompters

### Logo
Open-book SVG + "HEALTH EDUCATION" tagline. Used in all site pages.

---

## 3. ARTICLE INVENTORY — COMPLETE AND CURRENT (source of truth)

Three files required per article: **Article HTML · Visuals HTML · Teleprompter HTML**

### Series A — Cardiovascular Health (Articles 01–07)
All three files confirmed complete and on GitHub for all 7 articles. Educational voice retrofit confirmed complete.

| # | Title | Slug |
|---|-------|------|
| 01 | Hypertension (High Blood Pressure) | hypertension |
| 02 | Cholesterol Explained | cholesterol |
| 03 | How Doctors Estimate Heart Attack Risk | heart-attack-risk |
| 04 | Statins — Benefits & Risks | statins |
| 05 | How to Reduce Cardiovascular Risk with Lifestyle Changes | lifestyle-changes |
| 06 | Salt and Blood Pressure | salt-blood-pressure |
| 07 | Do Supplements Lower Cholesterol? | supplements-cholesterol |

### Series B — Practical Health (Articles 08–12)
All three files confirmed complete and on GitHub for all 5 articles. Educational voice retrofit confirmed complete.

| # | Title | Slug |
|---|-------|------|
| 08 | The Mediterranean Diet | mediterranean-diet |
| 09 | Sleep and Your Health | sleep |
| 10 | Exercise — the Evidence Base | exercise |
| 11 | Stress and the Body | stress |
| 12 | Alcohol — What the Evidence Shows | alcohol |

### Series C — Digestive Health (Articles 13–21)
Articles 13–20: all three files confirmed complete and on GitHub. Educational voice retrofit confirmed complete.
Article 21: article HTML built April 2026. Visuals built April 2026. Teleprompter still to build.

| # | Title | Slug | Status |
|---|-------|------|--------|
| 13 | Acid Reflux and GORD | acid-reflux | All 3 files on GitHub ✅ |
| 14 | IBD — Crohn's & Ulcerative Colitis | ibd | All 3 files on GitHub ✅ |
| 15 | Bloating — Causes and Evidence | bloating | All 3 files on GitHub ✅ |
| 16 | Irritable Bowel Syndrome (IBS) | ibs | All 3 files on GitHub ✅ |
| 17 | Fatty Liver Disease (MASLD) | masld | All 3 files on GitHub ✅ |
| 18 | Coeliac Disease | coeliac | All 3 files on GitHub ✅ |
| 19 | Gallstones | gallstones | All 3 files on GitHub ✅ |
| 20 | Diverticular Disease | diverticular-disease | All 3 files on GitHub ✅ |
| 21 | Constipation | constipation | All 3 files built April 2026 ✅ — upload to GitHub |

**Total articles live on site:** 20
**Article 21:** all 3 files complete — upload constipation.html, constipation-visuals.html, constipation-teleprompter.html to GitHub

---

## 4. SITE FILES — CURRENT STATUS

| File | Status | Notes |
|------|--------|-------|
| index.html | Rebuilt April 2026 | 20+ years corrected; voice fixed; 2026 |
| helf-school-conditions.html | Rebuilt April 2026 | 20 live articles; 3 series; correct slugs |
| helf-school-membership.html | On GitHub | Pricing: £0 / £6pm or £60pa / £150 lifetime |

### helf-school-conditions.html — April 2026 rebuild (full rebuild, not patch)
- 3 series shown: Cardiovascular (7) · Practical Health (5) · Digestive Health (8 live + 1 coming soon)
- Filter chips: All topics · ❤️ Cardiovascular · 🌿 Practical Health · 🫁 Digestive Health
- Hero stats: 3 series published · 20 articles live now · ∞ growing over time
- Article 21 Constipation shown as "Coming soon" with modal
- Copyright © 2026
- Nav links: `index.html` throughout (old file wrongly used `helf-school.html`)
- Full canonical educational voice phrase in inline disclaimer and footer
- Unbuilt series (Neurological, Fatigue, Medical Decision, old Practical Articles) completely removed
- Article 07 now correctly shows as live with link (was wrongly "Coming soon")
- Practical Health Series (08–12) added — was entirely absent from old file

### index.html — April 2026 corrections applied
1. Hero h1: "Understanding your heart" → "Understanding your health" (broader scope)
2. Hero subtitle: "cardiovascular health" → "your health"
3. Hero trust item: "Always seek advice from your doctor" → full canonical phrase
4. Disclaimer banner: "Always speak to a qualified medical professional" → full canonical phrase
5. Why helf.school pillar: **30+ years → 20+ years** (primary fix)
6. Footer disclaimer: "Always consult your doctor" → full canonical phrase
7. Copyright © 2025 → © 2026
8. Disclaimer doc date: March 2025 → April 2026 · Version 1.0 → 1.1
9. Article template voice: "Your doctor will weigh these options with you" → full canonical phrase
10. Cloudflare email obfuscation removed → plain text contact reference
11. "About Dr [Name]" → "About Dr Paul" throughout
12. "Heart Conditions A–Z" footer link → `helf-school-conditions.html`

---

## 5. THE MOST IMPORTANT RULE — EDUCATIONAL VOICE

helf.school **describes** what medicine knows and what services exist. It **never instructs** the reader.

### FORBIDDEN phrases — banned everywhere on the site, in every file:
- "please speak to your GP"
- "always tell your doctor"
- "you should..."
- "stop and seek urgent advice"
- "decision made in partnership"
- "if you have concerns"
- "always consult your doctor"
- "always seek advice from your doctor"
- "speak to a qualified medical professional"
- "Anything personally relevant is a conversation for your GP" — shortened version, not allowed

### REQUIRED standard phrase — always written in full, never shortened:
> "Anything personally relevant is a conversation for you to have with your GP or healthcare professional."

Applies to: every article, every visuals file, every teleprompter, every CTA, every disclaimer, every site page — new and retrospective.

---

## 6. VIDEO INTRO STANDARD (Segment 1, ~15–18 seconds)

Every video opens with this exact intro:

> "I'm Dr Paul — I spent over twenty years as an NHS GP before I retired in 2019. Today I want to talk to you about [TOPIC]. Now, I do have to say upfront — what I'm giving you here is health education, not medical advice. Anything personally relevant is a conversation for you to have with your GP or healthcare professional. Right — let's get into it."

---

## 7. PRODUCTION WORKFLOW

### Per-article order
**Article HTML first → Visuals HTML second → Teleprompter HTML third.**

Never reverse this order. Cross-check article ↔ presenter before finalising either file. Every key stat, study name, year, and citation must match exactly between article and teleprompter. Resolve discrepancies before upload — always correct to the verified academic source.

### Canonical reference files (in Claude project)
- **Article HTML:** `mediterranean-diet.html`
- **Visuals HTML:** `lifestyle-changes-visuals.html` (canonical for all layout patterns)
- **Teleprompter HTML:** `lifestyle-changes-teleprompter.html` (canonical for cue box standard)
- **CTA slide:** `hypertension-visuals.html`

### Large file crash risk
Very large HTML files (e.g. `statins.html`) can crash mid-build if too much is attempted in one turn. Strategy: build one file per turn, confirm successful delivery before proceeding to the next file.

### File fetch method (preferred)
GitHub raw URLs via `web_fetch` at session start:
`https://raw.githubusercontent.com/pls4286/helfschool/main/[filename].html`

Note: Claude cannot self-initiate `web_fetch` to GitHub raw URLs — the URL must be provided by Dr Paul or constructed from a confirmed slug. Do not rely on project uploads for article HTML files — they live on GitHub only by design and are intentionally absent from the Claude project.

### Dr Paul's preference
Dr Paul does not want to make manual edits to files. When corrections are needed to existing site files, Claude fetches the current file, applies all changes, and delivers the corrected file for download. Never ask Dr Paul to edit manually via the GitHub editor.

---

## 8. ARTICLE HTML STANDARDS

### Section structure (all condition articles)
1. What is it?
2. Key Terms box — navy background, sits between sections 1 and 2
3. Why does it matter? — max 5 bullet points
4. What your doctor might discuss
5. What the research shows
6. "Putting it all together" — navy box, italic text, bold closing line
7. References
8. Research flags ⚑ — for Dr Paul's review before upload

### Readability standards
- Body text: colour `#2C2C2C`, explicit `font-weight:400`
- Pale colours `#374151`, `#4B5563`, `#555` not permitted anywhere in articles
- No `fadeUp` or `opacity:0` animations on article body sections — content must be immediately visible on load
- Hero subtitle: minimum `rgba(255,255,255,0.85)`; below this not permitted
- Hero meta items: minimum `rgba(255,255,255,0.80)`
- Hero breadcrumb: minimum `rgba(255,255,255,0.75)`
- Values of 0.60 or below not permitted for hero/breadcrumb text

### Key Terms box standards
- Navy background `#1B2A4A`
- Title: Fraunces serif, minimum 1.05rem, `#fff`
- Term labels: minimum 0.88rem, `font-weight:700`, accent colour (amber `#E8A84A`)
- Definitions: minimum 0.92rem, `rgba(255,255,255,0.90)` — opacity 0.75 or 0.80 not permitted for definition text
- 1–2 boxes; alphabetical order within each box

### Inline citations
- Every stat or claim in prose carries a superscript number linking to anchored reference `id="ref-N"`
- Format: `<sup><a href="#ref-1">1</a></sup>`
- Superscript link colour matches the series accent colour

### Research card stat standard
- Stat boxes show **outcomes only** — effect sizes, risk changes, response rates
- **NEVER:** participant counts ("868 participants"), study counts ("10 RCTs"), cost figures ("£113m"), NHS admission numbers
- **Good examples:** "77% response rate vs 44% placebo" · "PEG superior across 4 outcomes" · "~30% CV event reduction" · "+12% / +30% mortality risk"
- **Bad examples:** "1.38M participants" · "87 RCTs" · "£168m NHS cost"
- Participant and study counts belong in the prose body text of the card, never the headline stat

### Full references standard
- Full citation block: authors · title · journal · year · vol · pages · DOI
- CSS classes: `.ref-block` / `.ref-full` / `.ref-links`
- Pill links: journal DOI and PubMed — verified by web search in same session only
- PMC/PubMed links treated as unreliable unless verified in same session
- Reference block `border-left` colour matches series accent
- Inline citations (superscripts) must link to corresponding `id="ref-N"` anchor

### Research flags ⚑
- Unverified claims flagged ⚑ for Dr Paul's review
- Pre-draft rule: before building any article HTML, verify every cited study — (1) exists, (2) correct condition, (3) supports the specific claim, (4) URL/DOI resolves to correct article
- Never include an unverified link in a delivered file

### Drug naming standard
Apply everywhere, on first mention per section:
- macrogol (Movicol, Laxido)
- ispaghula husk (Fybogel)
- senna (Senokot)
- bisacodyl (Dulcolax)
- linaclotide (Constella)
- prucalopride (Resolor)
- atorvastatin (Lipitor)
- semaglutide (Ozempic)
- infliximab (Remicade)
- adalimumab (Humira)

### Lay-clarification brackets
Required every time for medical terms AND statistical measures in all prose, research cards, tables, and callouts:
- HR (hazard ratio — HR 1.23 = 23% higher risk)
- RR (relative risk)
- OR (odds ratio)
- SMD (standardised mean difference — effect size)
- NNT (number needed to treat)
- CI (confidence interval)
- PAR (population-attributable risk)

### People-centred content structure
- Frame everything around how the condition affects the reader and their life
- Research used two ways: (1) confirm what the condition does to them, (2) show what works so they can act
- CTAs = "what can I do NOW/LATER for MY condition, backed by research" — never generic
- Standard sections: What is it? / Why does it matter? / What your doctor might discuss / Research / Key Terms (navy, 1–2 boxes) / "Putting it all together" (navy italic close) / ⚑ flags
- Avoid the word "eliminated" — use clear plain English alternatives

---

## 9. VISUALS HTML STANDARDS

### Layout
- 4–6 item slides: **horizontal rows** using the `ev-stat-row` pattern — `72px icon | content | stat` — NOT vertical stacking
- Stats: 2.5–3.6rem font size
- Colour narrative: red = harm · amber = mechanism · green = action
- Cards: `min-height:0` + `overflow:hidden`
- Max 2 `ev-cards` per research slide
- CTA section: `cta-wrap-v2` class — horizontal row layout
- Uneven row heights: use uneven `fr` ratios (e.g. `grid-template-rows: 1fr 1fr 1.5fr`) or `grid-row:span 2` for a key card in 5–6 card grids — prevents bottom-card clipping

### Animation
- `animate-ready` class on all animated cards — **never** hardcoded `opacity:0` in final delivered files
- Cards animate in on keyboard advance, not on page load

### ev-stat-box — EXACT SPECIFICATION (locked April 2026)
The stat box sits in the left column (220px) of each ev-card. These values are required exactly — do not increase padding or font sizes or text will overflow the bottom of the box:

```css
.ev-stat-box { padding: .9rem .75rem; overflow: hidden; }
.ev-kf-label { margin-bottom: .35rem; }
.ev-stat-row { margin-bottom: .3rem; }
.ev-conditions { font-size: .78rem; line-height: 1.32; }
```

- `.ev-conditions` text must be short enough to fit 220px — keep under ~8 words per line, ~2 lines maximum
- Do NOT increase padding on `.ev-stat-box` — text will disappear off the bottom of the card
- Do NOT use `.ev-conditions` font size above `.78rem` — it will overflow at any larger size
- This was confirmed as the correct fix in April 2026 after repeated overflow errors

### CTA slide standard (all visuals files)
- Full-screen with radial gold-glow background + pulsing icon halo (3.2s drop-shadow)
- Fraunces headline: `clamp(3.2, 5.8vw, 4.9rem)`; Fraunces italic subline
- 4 action cards (NOT chips) — emoji + Fraunces bold label, gradient + gold border
- **Medical-advice disclaimer box required:** ⚕️ icon · dashed border · "Health education — not medical advice" + full educational-voice phrase
- Closing slide: same disclaimer box as CTA slide
- Reference: `hypertension-visuals.html`

### Readability standards — visuals (all rgba thresholds)
**Topbar:**
- Subtitle: minimum 0.75rem, `rgba(255,255,255,0.75)`
- Slide counter: minimum 0.85rem, `rgba(255,255,255,0.90)`
- Keyboard hint: minimum `rgba(255,255,255,0.60)` — values 0.35 or below not permitted

**Animation/diagram text:**
- Labels: minimum 13px, `rgba(255,255,255,0.80)`
- SVG annotations: minimum 10px, `rgba(255,255,255,0.60)` — opacity 0.50 or below not permitted

**Source attributions:**
- Minimum 0.75rem, `rgba(255,255,255,0.55)` on dark backgrounds
- Minimum 0.75rem, `#2C2C2C` on light backgrounds
- `.source-tag` style at `rgba(255,255,255,0.25)` not permitted

**Presenter intro and closing slides:**
- Taglines + series label: minimum `rgba(255,255,255,0.70)`
- Logo dot: minimum `rgba(255,255,255,0.60)`
- Stat card label: `rgba(255,255,255,0.90)`
- Stat source: 0.75rem, `rgba(255,255,255,0.65)`

---

## 10. TELEPROMPTER HTML STANDARDS

### Core technical spec
- RAF (requestAnimationFrame) auto-scroll
- Body font: 1.9rem
- Speed levels: `[0, 8, 14, 20, 28, 38, 50]`, default index 3 (speed 20)
- Controls: speed 1–6 · A+/A− font size · touch swipe
- Segment dots: bottom of screen
- Pause button: ⏸ — **NOT ▶ PLAY button** (a common error)
- No Google Fonts — fully self-contained (no external dependencies)
- No topbar
- Segment IDs: `seg-N`

### Cue box standard (reference file: `lifestyle-changes-teleprompter.html`)
Cue box always **precedes** the script lines for its segment — never after.
Dr Paul advances slide FIRST, then reads — viewer sees slide before Dr Paul speaks.
Label: `▶ ADVANCE NOW — then read`
Prior teleprompter files built before this standard was confirmed may require retrofitting — confirm per file.

### Video length standard
- Maximum 4–5 minutes
- Word count: approximately 600–750 words at ~150 words per minute
- Cut ruthlessly — no redundant examples, tight preamble, merge segments where possible
- The teleprompter is the tight, high-impact doorway to the full article

### Teleprompter content standard
Each teleprompter must deliver:
1. Fundamental messages stated clearly
2. Key statistics with exact numbers — no rounding drift from the article figures
3. Specific practical pointers — "add 1,000 steps/day" not "move more"; "30g fibre daily" not "eat more fibre"

Every segment serves message, statistic, or action — cut what doesn't earn its place. Article = full-depth reference; teleprompter = tight doorway in.

---

## 11. GRAPHICS AND ANIMATION STANDARDS

### Standalone animation files
- Standalone animation HTML files (e.g. `salt-sources.html`) are GIF capture sources only
- Never embedded directly in articles or presenter files
- Each presenter contains its own inline recreation of the visual in the `visuals{}` object

### New video — three files always required
For any visual used in a video: standalone animation HTML (GIF source) + screen file + presenter cue box must all exist before filming.

### GIF settings
Scale 0.62 · every 2nd frame · 120 colours · under 1.5MB total PPTX

### Video screen workflow
- Camera-ready HTML files (e.g. `ar-sphincter-screen.html`): full-screen, responsive, auto-animate on load, bold for filming
- Presenter HTML: bold red `.diagram-cue` callout box shows filename to open on second screen facing camera
- Dr Paul reads from presenter; diagram HTML full-screened on second screen
- Layout: `flex-start`, `6vh` top padding (prevents title clipping)

---

## 12. QC CHECKLIST (run before every upload)

1. Readability — no pale text below colour minimums specified above
2. References — full citation blocks with DOI; pill links verified in same session
3. Research flags ⚑ — all claims verified against source; no unverified links
4. Graphics — standalone animation file exists; presenter has matching inline visual
5. Article ↔ presenter consistency — all facts, study names, years, citations match exactly
6. Educational voice — no forbidden phrases; canonical phrase correct and in full throughout
7. Drug names — brand names in brackets after all generics
8. Lay-clarification — statistical terms bracketed on first use in each section
9. Research card stats — outcomes only; never participant/study counts or cost figures
10. CTA slide — disclaimer box present with full canonical phrase
11. Closing slide — same disclaimer box present
12. Copyright year — 2026
13. Body text weight — `font-weight:400` throughout (never 300 in body)
14. No `opacity:0` animations on article body sections — content immediately visible
15. **ev-stat-box — `.ev-conditions` font is `.78rem`, padding is `.9rem .75rem`, `overflow:hidden` present — check before delivery on every visuals file**

---

## 13. FILE DELIVERY AND UPLOAD

### Downloading from Claude
**Primary route:** Artifact panel download button.
**Backup route:** Open in Notepad → File → Save As → Downloads → `[filename].html` → file type "All Files".
**Never Ctrl+S** — saves the webpage wrapper, not the source HTML.

### Uploading to GitHub
github.com/pls4286/helfschool/upload/main
Sign in with Google if session has expired. Upload individual HTML files (not zipped). Commit with a brief description.

### File corruption pattern — know and ignore
Edge incognito uploads occasionally capture the Claude.ai loader HTML (~5,140 bytes, begins with "data-build-id") instead of the actual file. Never false-alarm on byte size alone. Verify content via GitHub raw URL before any assessment. This is an upload capture issue, not a file corruption issue.

---

## 14. APPROVED RESEARCH SOURCES

BMJ · NICE guidelines · Cochrane Database · NEJM · The Lancet · JAMA · BMJ Best Practice · PubMed · NHS/NHS Digital · ONS · CDC · WHO · Global Burden of Disease Study · ESC/EAS guidelines · Alimentary Pharmacology & Therapeutics · European Heart Journal

No non-peer-reviewed sources, commercial health sites, or forum content permitted.

---

## 15. MEMBERSHIP PRICING

- Free (Explorer): £0 — no credit card required
- Member: £6/month or £60/year — cancel anytime
- Lifetime: £150 one-off payment

---

## 16. PRE-DRAFT VERIFICATION RULE

Before presenting any article, visuals, or teleprompter HTML — verify via web search that every cited study, trial, or statistic:
1. Exists as a real published paper
2. Relates to the correct condition
3. Supports the specific claim made in the article
4. URL/DOI resolves to the correct article

Never include an unverified link. Never assume a study exists based on a plausible-sounding citation. Never cite NICE CG99 for adult constipation — it covers children and young people only. The correct adult reference is NICE CKS at `cks.nice.org.uk/constipation`.

---

## 17. RETROFIT STATUS (retroactive standards across existing articles)

### Confirmed complete
- Educational voice: confirmed complete across Articles 01–21 (as built)
- Article HTML retrofits (Articles 13–18): confirmed complete
- Visuals and teleprompters (Articles 13–18): confirmed built

### Outstanding — to confirm and apply
- Research card stat standard (outcomes only, not counts): outstanding across 01–11
- Inline citations (superscripts linking to refs): outstanding across 01–11
- CTA slide high-impact standard (disclaimer box, gold-glow, 4 action cards): outstanding across 01–11
- Visuals layout standard (horizontal rows, ev-stat-row): outstanding across 01–11
- Key terms / hero visibility standards: outstanding across 01–11
- Teleprompter cue box standard: confirm per-file which were built before standard was set

---

## 18. KEY LEARNING POINTS (accumulated)

### NICE CG99 is for children only — never cite for adults
NICE CG99 covers constipation in **children and young people only**. For adult constipation the correct reference is **NICE CKS** at `cks.nice.org.uk/constipation`. Citing CG99 for an adult article is a meaningful clinical error.

### Dr Paul's experience is 20+ years, not 30+
All references to clinical experience must read "20+ years" or "over twenty years as an NHS GP". The incorrect "30+" was on the live index.html and was corrected April 2026. Check all new content for this before delivery.

### Local link testing — expected not to work
When Dr Paul opens a downloaded HTML file locally and clicks article links, they appear broken. This is expected and correct — the linked article files don't exist in the Downloads folder. Links are correctly coded as relative (`href="salt-blood-pressure.html"`) and work on the live GitHub site where all article files share the same directory. Do not recode links to absolute URLs to fix this apparent issue.

### Dr Paul prefers Claude to handle all file edits
Never ask Dr Paul to make manual edits to files via the GitHub editor. When corrections are needed, Claude fetches the file, applies all changes, and delivers the corrected file for download and re-upload.

### Conditions page — always rebuild, never patch
When helf-school-conditions.html needs significant changes, rebuild from scratch. The old version had deeply structural problems (entire Practical Health series missing, wrong article statuses, 4 unbuilt series shown, fake digestive articles). Partial patching would miss cascading issues.

### Educational voice — systemic issue in older files
index.html had directive language in three locations. When fetching any older file for any purpose, audit for forbidden phrases and correct them as part of the work.

### Teleprompter cue box — advance THEN read
The cue box precedes the script for its segment. Dr Paul advances the slide first, then reads the script — the viewer sees the slide before Dr Paul speaks. Cue box label: `▶ ADVANCE NOW — then read`. Do not place cue boxes after script lines.

### Large file writing — use create_file not bash
For HTML files over ~400 lines, `create_file` is the correct tool. Bash heredocs fail on large HTML because of shell character escaping (backticks, dollar signs, special characters in SVG and CSS). Always use `create_file` for full HTML files, and never attempt workarounds via bash for large content.

### File already exists — delete and retry
If `create_file` reports "file already exists", delete the existing placeholder (`rm /home/claude/filename.html`) and retry. The error is always a leftover placeholder — not a meaningful conflict.

### Constipation article — April 2026 research decisions
- NICE CG99 explicitly excluded (children only)
- Rome IV criteria used as the clinical framework — explained in lay terms in text
- Laxative stepwise shown as 4 numbered steps with all brand names included
- Toileting position (footstool) included — evidence-based, often overlooked practical point
- Research card 1: macrogol vs lactulose (Cochrane 2010, CD007570)
- Research card 2: fibre supplementation response rate 77% vs 44% (Christodoulides 2016)
- Important distinction: fibre evidence is for fibre supplements (psyllium/ispaghula) not dietary fibre from whole foods — clearly stated in the article

### ev-stat-box overflow fix — LOCKED APRIL 2026
Text disappearing off the bottom of ev-cards on the research slide is a recurring error. The confirmed fix is:
- `.ev-stat-box`: `padding:.9rem .75rem` + `overflow:hidden` — do NOT increase padding
- `.ev-kf-label`: `margin-bottom:.35rem`
- `.ev-stat-row`: `margin-bottom:.3rem`
- `.ev-conditions`: `font-size:.78rem; line-height:1.32` — do NOT increase font size
- `.ev-conditions` text content: keep short — max ~8 words per line, ~2 lines
- This spec is in Section 9 and QC checklist item 15. Check it on every visuals build before delivery.

### session-start-rules.md status table conflict — April 2026
The session-start-rules.md file fell out of sync with the project knowledge multiple times in April 2026, causing Claude to repeatedly tell Dr Paul that retrofits and builds were outstanding when they had already been done. The fix applied: Rule 6A added to session-start-rules.md stating that project knowledge always overrides this file on status. Both files must be updated and uploaded together at every session end.

---

## 19. OUTSTANDING TASKS (April 2026)

### Immediate
- Upload Article 21 files to GitHub: `constipation.html` · `constipation-visuals.html` · `constipation-teleprompter.html`
- Update `helf-school-conditions.html` to show Article 21 as live (currently shows "Coming soon")

### Verification
- `hypertension.html` references 5 & 6 — Cochrane PubMed IDs flagged ⚑ unverified — check before confirming article complete

### Series planning
- **Neurological series (Articles 22–26)** — article list confirmed April 2026. See Section 24. Build Article 22 (Migraine) first. Update conditions page before first Neurological article goes live.

### Retrofit backlog (Articles 01–11 only — 13–20 confirmed complete)
- Research card stat standard
- Inline citations (superscripts)
- CTA slide standard
- Visuals layout standard (ev-stat-row, horizontal rows)
- Key terms / hero visibility standards
- Teleprompter cue box — confirm which files pre-date standard

---

## 20. CONSTIPATION ARTICLE — VERIFIED REFERENCES (April 2026)

All five sources verified by web search in April 2026 session.

| Ref | Citation | DOI / URL | Used for |
|-----|----------|-----------|----------|
| 1 | NICE CKS Constipation (adults). Last revised 2023 | cks.nice.org.uk/constipation | Definition (Rome IV), red flags, laxative stepwise approach |
| 2 | Dowden A. Prescriber 2021 + BJHA 2025 | wchh.onlinelibrary.wiley.com/doi/10.1002/psb.1954 | NHS burden: ~83,000 admissions/yr; 18.6m prescriptions; ~£113m cost |
| 3 | Lee-Robichaud H et al. Cochrane Database Syst Rev 2010;(7):CD007570. PMID 20614462 | doi.org/10.1002/14651858.CD007570.pub2 | Macrogol superior to lactulose across all outcomes (10 RCTs, 868 participants) |
| 4 | Christodoulides S et al. Aliment Pharmacol Ther 2016;44(2):103–116. PMID 27170558 | doi.org/10.1111/apt.13662 | Fibre: 77% response vs 44% placebo; RR 1.71 (95% CI 1.20–2.42) |
| 5 | NHS Inform. Constipation | nhsinform.scot/illnesses-and-conditions/stomach-liver-and-gastrointestinal-tract/constipation | Prevalence: 1 in 7 adults UK at any time; women twice as often as men |

---

## 21. CLAUDE PROJECT FILE NOTES

The Claude project holds **visuals, teleprompter, and screen files only**. Article HTML files live on GitHub only — intentionally absent from the Claude project. Exception: `mediterranean-diet.html` kept as canonical article template.

### Canonical reference files
| File | Purpose |
|------|---------|
| `mediterranean-diet.html` | Canonical article HTML template |
| `lifestyle-changes-teleprompter.html` | Canonical teleprompter (cue box standard) |
| `lifestyle-changes-visuals.html` | Canonical visuals (ev-stat-row horizontal layout, all patterns) |
| `hypertension-visuals.html` | Canonical CTA slide reference |

### Files confirmed in Claude project (April 2026)
**Teleprompters (all series):** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd · ibs · bloating · coeliac · masld · acid-reflux · constipation

**Visuals (all series):** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd (screen) · ibs · bloating · coeliac · masld · acid-reflux · constipation

**Screen files:** Ar_barretts-screen · Ar_sphincter-screen · ibd-gut-screen · bloating-gut-screen · bloating-fodmap-screen

**Scripts (older format):** acid-reflux-script · bloating-script · cholesterol-script · heart-attack-risk-script · hypertension-script · ibd-script · ibs-script

---

## 22. SESSION START RULES (content of helf-school-session-start-rules.md)

These rules must be applied at the start of every session, before any output or assessment is produced.

### Rule 1 — Read before acting
Read `helf-school-project-knowledge.md` AND `helf-school-session-start-rules.md` in full before any output, checks, or assessments. No exceptions.

### Rule 2 — Article inventory is the source of truth
The article inventory in Section 3 of this document is authoritative. Do not infer article status from file sizes, project file listings, or previous session summaries alone.

### Rule 3 — 5,140-byte files are NOT corrupted
Files approximately 5,140 bytes beginning with "data-build-id" are Edge incognito loader stubs. Never flag as corrupted. Fetch from GitHub raw URL to verify content.

### Rule 4 — Never produce output before confirming understanding
Before building or modifying any file, confirm: (1) which article/file, (2) current status per inventory, (3) canonical reference checked.

### Rule 5 — Educational voice check on every file
Audit every file for forbidden phrases before delivery. Always apply the full canonical phrase; never shorten it.

### Rule 6 — Cross-check article ↔ teleprompter before delivery
All key statistics, study names, years, and citation authors must match exactly between both files.

### Rule 6A — Project knowledge always overrides session-start-rules on status
**If the file status table in session-start-rules.md conflicts with Section 3 of this document, this document (project knowledge) is correct.** Never flag work as outstanding based on session-start-rules.md alone. Both files must be updated together at every session end.

### Rule 7 — One large file per turn
Build very large HTML files one per turn. Wait for confirmation before proceeding to the next file.

### Rule 8 — Verify references before building
Run web searches to verify all planned citations before building any article HTML.

### Rule 9 — Update project knowledge at session end
Update this document and session-start-rules.md together. Dr Paul uploads both to GitHub AND the Claude Project.

### Rule 10 — NICE CG99 is children only
Never cite NICE CG99 in any adult article. Correct adult constipation reference: NICE CKS at cks.nice.org.uk/constipation.

---

## 23. ARTICLE-SPECIFIC NOTES — KNOWN ISSUES

### hypertension.html
References 5 and 6 — Cochrane PubMed IDs flagged ⚑ unverified. These need verification via web search before the article can be confirmed fully complete. All other references in this article are confirmed.

### statins.html
Very large HTML file — has caused mid-build crashes in previous sessions. If this file needs to be rebuilt or significantly edited, handle it in one dedicated turn.

### conditions page (helf-school-conditions.html)
Rebuilt April 2026. If any further changes are needed, rebuild the whole file — do not attempt partial patches.

### index.html
Rebuilt April 2026 with all 12 corrections listed in Section 4. "About Dr Paul" section correctly reads "NHS GP · 20+ years". Consistent throughout.

---

## 24. PLANNING NOTES — NEXT SERIES

### Neurological Series (Articles 22–26) — CONFIRMED APRIL 2026
Series colour: `#6B5EA8` (purple)

| # | Title | Slug |
|---|-------|------|
| 22 | Migraine | migraine |
| 23 | Headaches — Types and Red Flags | headaches |
| 24 | Dizziness and Vertigo | dizziness-vertigo |
| 25 | Memory, Cognition and Dementia | memory-dementia |
| 26 | Epilepsy — What It Is and How It's Managed | epilepsy |

**Rationale:**
- Migraine: ~23% UK working-age adults, #3 global DALY burden, massively under-diagnosed
- Headaches: most common neurological GP presentation; "when to worry" is heavily searched
- Dizziness and Vertigo: BPPV very common and treatable; patients anxious and poorly informed
- Memory and Dementia: highest public anxiety; most costly neurological condition in UK
- Epilepsy: ~600,000 UK patients; significant stigma; strong educational need

**Possible extensions (Articles 27–28, to confirm later):**
- Stroke and TIA (could bridge with cardiovascular series)
- Parkinson's Disease (rising incidence, ageing population)

**Before building any Neurological article:**
- Confirm slugs are not already in use on GitHub
- Update helf-school-conditions.html to include the Neurological series section
- Establish series colour `#6B5EA8` is consistently applied across all three files per article

### Cancer Series (further horizon)
Discussed as a future series but not yet planned. No article list defined.

---

## 25. PROCESS NOTES — FILE CREATION IN CLAUDE

### Writing large HTML files
Use `create_file` for all HTML files. Bash heredocs fail on large HTML content because shell escaping breaks SVG paths, CSS values, and JavaScript (backticks, `$`, `&`, `>`, `<`). `create_file` handles all of these correctly.

### File already exists error
If `create_file` reports "file already exists", the cause is always a placeholder or earlier version from the same session. Run `rm /home/claude/filename.html` then retry `create_file`.

### Outputs directory
All files for Dr Paul must be copied to `/mnt/user-data/outputs/` and presented via `present_files`. Files in `/home/claude/` are not visible to Dr Paul until this step is completed.

### QC before presenting
Always run bash QC checks (grep for key phrases, count required elements, verify word counts) before copying to outputs. Deliver only after QC passes.

---

*End of document. Update at the end of every session. Download via Artifact panel. Upload to both GitHub (pls4286/helfschool/main) and the Claude Project to take effect in future sessions.*
