# helf.school — Project Knowledge
**Last updated: April 2026**

---

## SECTION 0 — SESSION START PROTOCOL (READ FIRST — NO EXCEPTIONS)

**MANDATORY FIRST ACTION every session:** Read this file AND `/mnt/project/helf-school-session-start-rules.md` IN FULL before any output, checks, or assessments. This step is non-negotiable because these files contain critical rules — including file integrity rules and the article inventory which is the source of truth. Reading after producing output is too late.

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
Article 21: article HTML built April 2026 — visuals and teleprompter still to build.

| # | Title | Slug | Status |
|---|-------|------|--------|
| 13 | Acid Reflux and GORD | acid-reflux | All 3 files on GitHub |
| 14 | IBD — Crohn's & Ulcerative Colitis | ibd | All 3 files on GitHub |
| 15 | Bloating — Causes and Evidence | bloating | All 3 files on GitHub |
| 16 | Irritable Bowel Syndrome (IBS) | ibs | All 3 files on GitHub |
| 17 | Fatty Liver Disease (MASLD) | masld | All 3 files on GitHub |
| 18 | Coeliac Disease | coeliac | All 3 files on GitHub |
| 19 | Gallstones | gallstones | All 3 files on GitHub |
| 20 | Diverticular Disease | diverticular-disease | All 3 files on GitHub |
| 21 | Constipation | constipation | Article HTML built April 2026; visuals + teleprompter outstanding |

**Total articles live on site:** 20
**Article 21:** article HTML complete, 2 files outstanding

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
- **Visuals HTML:** `alcohol-visuals.html` (canonical for horizontal-row layout)
- **Teleprompter HTML:** `stress-teleprompter.html` (canonical for cue box standard)
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

### CTA slide standard (all visuals files)
- Full-screen with radial gold-glow background + pulsing icon halo (3.2s drop-shadow)
- Fraunces headline: `clamp(3.2, 5.8vw, 4.9rem)`; Fraunces italic subline
- 4 action cards (NOT chips) — emoji + Fraunces bold label, gradient + gold border
- **Medical-advice disclaimer box required:** ⚕️ icon · dashed border · "Health education — not medical advice" + full educational-voice phrase
- Closing slide: same disclaimer box as CTA slide
- Reference: `hypertension-visuals.html`
- Retrofit outstanding across Articles 01–11, 13–18

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

### Cue box standard (reference file: `stress-teleprompter.html`)
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

### Outstanding — to confirm and apply
- Research card stat standard (outcomes only, not counts): outstanding across 01–11, 13–18
- Inline citations (superscripts linking to refs): outstanding across 01–11, 13–18
- CTA slide high-impact standard (disclaimer box, gold-glow, 4 action cards): outstanding across 01–11, 13–18
- Visuals layout standard (horizontal rows, ev-stat-row): outstanding across 01–11, 13–18
- Key terms / hero visibility standards: outstanding across 01–11, 13–18
- Teleprompter cue box standard: confirm per-file which were built before standard was set

Confirm per-article retrofit status at start of each session before beginning new work.

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

---

## 19. OUTSTANDING TASKS (April 2026)

### Immediate — Article 21 completion
- `constipation-visuals.html` — visuals file for Article 21 (to build next)
- `constipation-teleprompter.html` — teleprompter for Article 21 (to build after visuals)

### Verification
- `hypertension.html` references 5 & 6 — Cochrane PubMed IDs flagged ⚑ unverified — check before confirming article complete

### Series planning
- **Neurological series** — next series after Digestive Health. Article list not yet defined. Plan before building any Neurological content.

### Retrofit backlog (confirm at session start before new work)
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
| `stress-teleprompter.html` | Canonical teleprompter (cue box standard) |
| `alcohol-visuals.html` | Canonical visuals (ev-stat-row horizontal layout) |
| `hypertension-visuals.html` | Canonical CTA slide reference |

### Files confirmed in Claude project (April 2026)
**Teleprompters (all series):** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd · ibs · bloating · coeliac · masld · acid-reflux (check)

**Visuals (all series):** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd (screen) · ibs · bloating · coeliac · masld · acid-reflux

**Screen files:** Ar_barretts-screen · Ar_sphincter-screen · ibd-gut-screen · bloating-gut-screen · bloating-fodmap-screen

**Scripts (older format):** acid-reflux-script · bloating-script · cholesterol-script · heart-attack-risk-script · hypertension-script · ibd-script · ibs-script

---

---

## 22. SESSION START RULES (content of helf-school-session-start-rules.md)

These rules must be applied at the start of every session, before any output or assessment is produced.

### Rule 1 — Read before acting
Read `/mnt/project/helf-school-project-knowledge.md` AND `/mnt/project/helf-school-session-start-rules.md` in full before any output, checks, or assessments. No exceptions. Reading after producing output is too late.

### Rule 2 — Article inventory is the source of truth
The article inventory in Section 3 of this document is authoritative. Do not infer article status from file sizes, project file listings, or previous session summaries alone. If there is any doubt about whether a file is on GitHub, fetch it via raw URL to verify.

### Rule 3 — 5,140-byte files are NOT corrupted
Files in the Claude project that are approximately 5,140 bytes (or similar small sizes like 6,170 bytes) and begin with "data-build-id" are Edge incognito loader stubs. They are captured during the upload process, not corrupted versions of the real file. Never flag these as corrupted or missing. The real file lives on GitHub. Fetch from raw URL to verify content.

### Rule 4 — Never produce output before confirming understanding
Before building or modifying any file, confirm: (1) which article/file is being worked on, (2) what the current status is per the inventory, (3) whether the canonical reference file has been checked. Do not start building based on an assumption.

### Rule 5 — Educational voice check on every file
Before delivering any file, audit it for forbidden phrases. The single most common error in older files is directive language. Always apply the full canonical phrase; never shorten it.

### Rule 6 — Cross-check article ↔ teleprompter before delivery
Any time both an article and a teleprompter/visuals file exist for the same article, verify that all key statistics, study names, years, and citation authors match exactly between both files. Discrepancies must be resolved before either file is delivered.

### Rule 7 — One large file per turn
If building a very large HTML file (600+ lines), build it in one turn and wait for Dr Paul to confirm successful receipt before proceeding to the next file. Do not queue multiple large file builds in a single turn.

### Rule 8 — Verify references before building
Before building any article HTML, run web searches to verify all planned citations. Confirm each study (1) exists, (2) relates to the correct condition, (3) supports the specific claim, (4) DOI/URL resolves correctly. Never build an article with unverified citations.

### Rule 9 — Update project knowledge at session end
At the end of every session: (1) update this project knowledge document with anything new, (2) present it via Artifact panel for download, (3) Dr Paul uploads it to GitHub AND to the Claude Project — both are required. If only one is updated, the other will be out of sync next session.

### Rule 10 — NICE CG99 is children only
Never cite NICE CG99 in any adult article. It covers constipation in children and young people only. The correct adult constipation reference is NICE CKS at cks.nice.org.uk/constipation. This rule exists because the error is easy to make and is clinically significant.

---

## 23. ARTICLE-SPECIFIC NOTES — KNOWN ISSUES

### hypertension.html
References 5 and 6 — Cochrane PubMed IDs flagged ⚑ unverified. These need verification via web search before the article can be confirmed fully complete. All other references in this article are confirmed.

### statins.html
This is a very large HTML file and has caused mid-build crashes in previous sessions. If this file needs to be rebuilt or significantly edited, handle it in one dedicated turn and do not attempt other work in the same turn.

### conditions page (helf-school-conditions.html)
Rebuilt April 2026. If any further changes are needed, rebuild the whole file — do not attempt partial patches. The old version had too many cascading structural problems for safe patching.

### index.html
Rebuilt April 2026 with all 12 corrections listed in Section 4. The "About Dr Paul" section correctly reads "NHS GP · 20+ years". The credential item and the intro quote ("In over twenty years as an NHS GP...") are consistent and correct.

---

## 24. PLANNING NOTES — NEXT SERIES

### Neurological Series
Not yet started. Article list not defined. Before building any Neurological article, define the series structure with Dr Paul — article titles, slugs, and sequence — and update this project knowledge document before the first build.

Suggested starting topics (to confirm with Dr Paul):
- Migraine and headache types
- When headaches need investigating
- Dizziness and vertigo
- Fainting (syncope)
- Memory and cognitive decline

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
