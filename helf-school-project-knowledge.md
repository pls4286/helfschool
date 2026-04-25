# helf.school — Project Knowledge
**Last updated: April 2026**

---

## ⚠️ DOCUMENT INTEGRITY — CLAUDE MUST READ THIS BEFORE ANY SESSION WORK

**This document has 25 numbered sections. Minimum expected line count: ~700 lines.**

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

## MANDATORY PRE-OUTPUT AUDIT — RUNS BEFORE EVERY FILE IS PRESENTED

This audit must be completed internally before Claude presents any article, visuals, or teleprompter file. It is not optional and cannot be skipped. Presenting a file without completing this audit is a failure.

**For every article HTML file, run all of the following before presenting:**

1. **Voice audit** — scan every sentence for forbidden phrases. No "you should", "speak to your GP", "seek help", "call 999/111". Canonical phrase present in full in disclaimer bar and footer.

2. **Lay-clarification audit** — scan every paragraph for medical terminology. Every term a lay reader would not immediately know must have a plain English definition in brackets on first use in each section. This includes anatomical terms (periorbital, temporal, bilateral), physiological terms, symptom descriptors (lacrimation, rhinorrhoea, ptosis, miosis), drug class names (tricyclic antidepressant, beta-blocker), diagnostic labels, and statistical measures (HR, RR, OR, NNT, CI). **Do not rely on the Key Terms box alone.** Check every sentence.

3. **Citation audit** — for every reference cited:
   - Confirm the paper exists and is real (web search in same session)
   - Confirm it is the PRIMARY paper containing the stat, not a secondary source citing that paper
   - Confirm the specific numerical claim is in that paper — fetch the abstract if needed
   - Confirm the NICE guideline number is CG or NG (search to verify — never from memory)
   - Confirm the PubMed PMID resolves to the correct paper (search to verify — every PMID, every time)

4. **Key Terms cross-reference audit** — any Key Terms box term appearing in a structured list, criteria box, or table must have "(see Key Terms below)" added.

5. **Safety-critical terms audit** — any term with direct safety implications (teratogenic, hepatotoxic, contraindicated) must have an inline lay definition, not just a Key Terms entry.

6. **Hero badge colour** — hero series badge must use `color: #fff` — never the series accent colour against a matching gradient background.

7. **Research card clinical conclusion audit** — every research card stat box must state the complete clinical finding as it is relevant to the patient. Run the test: can a lay reader understand WHAT was studied and WHAT was found from the stat box alone, without reading the body text? If not, rewrite before presenting. Statistical machinery (OR values, RCT counts, confidence intervals) must never appear in the stat box as the headline finding.

**For every visuals file, additionally run:**

8. **ev-stat-box check** — `.ev-conditions` font is `.78rem`, padding is `.9rem .75rem`, `overflow:hidden` present. ev-conditions text is short enough to fit 220px column.

9. **animate-ready check** — all animated cards have `animate-ready` class. No hardcoded `opacity:0` on card elements.

**This audit replaces the tendency to generate output first and check after. The audit happens before output — every time, without exception.**

---

## 1. PROJECT OVERVIEW

**Owner:** Dr Paul — retired NHS GP, 20+ years experience. Tier One ill health retired end of 2019 by the Chief Medical Officer for the NHS.

**Platform:** helf.school — health education membership website.

**Mission:** "To give every person access to clear, honest, evidence-based health education — helping them become a more informed, empowered participant in their own care."

**Core philosophy:** Health education — not medical advice. helf.school describes what medicine knows and what services exist. It never instructs the reader. Good medicine begins with truly listening — that philosophy underpins everything on the site.

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
Article 21: all three files built April 2026 — upload to GitHub pending.

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

### Series D — Neurological Health (Articles 22–26)
Articles 22–26: all three files built April 2026 — upload to GitHub pending.

| # | Title | Slug | Status |
|---|-------|------|--------|
| 22 | Migraine | migraine | All 3 files built April 2026 ✅ — upload to GitHub |
| 23 | Headaches — Types and Red Flags | headaches | All 3 files built April 2026 ✅ — upload to GitHub |
| 24 | Dizziness and Vertigo | dizziness-vertigo | All 3 files built April 2026 ✅ — upload to GitHub |
| 25 | Memory, Cognition and Dementia | memory-dementia | All 3 files built April 2026 ✅ — upload to GitHub |
| 26 | Epilepsy — What It Is and How It's Managed | epilepsy | All 3 files built April 2026 ✅ — upload to GitHub |

**Total articles built: 26. Articles 21–26 pending upload to GitHub.**

---

## 4. SITE FILES — CURRENT STATUS

| File | Status | Notes |
|------|--------|-------|
| index.html | Rebuilt April 2026 | 20+ years corrected; voice fixed; 2026 |
| helf-school-conditions.html | Rebuilt April 2026 | 20 live articles; 3 series; correct slugs |
| helf-school-membership.html | On GitHub | Pricing: £0 / £6pm or £60pa / £150 lifetime |

### helf-school-conditions.html — needs updating
Currently shows 20 live articles. Needs updating to reflect Articles 21–26 once uploaded to GitHub. When updating, rebuild from scratch — do not patch.

### index.html — April 2026 corrections applied
1. Hero h1: "Understanding your heart" → "Understanding your health"
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

**The stat box must convey the clinically important and relevant finding — not statistical machinery.**

This is a fundamental rule of health education. helf.school exists to help people understand their conditions. The research section must therefore convey what the research shows about their condition — stated as a complete, patient-relevant clinical conclusion.

**The complete clinical conclusion rule — LOCKED APRIL 2026:**

Every research card stat box must state the complete clinical finding in terms that are immediately meaningful to a lay reader. The stat box (ev-kf-label + ev-stat-row + ev-outcome + ev-conditions together) must answer:
1. **WHAT** was studied or found
2. **WHAT** the finding means for someone with that condition
3. Enough context for the finding to stand alone without the body text

**The test:** Can a lay reader understand the clinical finding from the stat box alone, without reading the body text? If not, rewrite.

**Correct examples — complete clinical conclusions:**
- "The Epley manoeuvre / is a safe & effective treatment for BPPV"
- "Vestibular rehabilitation / has moderate to strong evidence for its efficacy"
- "77% response rate / vs 44% placebo" (complete comparison — reader understands what works)
- "PEG superior / across all 4 outcomes" (clear clinical comparison)
- "Macrogol superior / to lactulose across all outcomes"
- "~50% / become seizure-free on their first anti-seizure medication"
- ">30% / develop drug-resistant epilepsy despite adequate treatment"

**Incorrect examples — statistical machinery or incomplete findings:**
- "11" with label "RCTs — Epley effective" — the number of trials is irrelevant to the patient
- "OR 2.67" — an odds ratio conveys nothing meaningful to a lay reader
- "Safe & effective" without stating WHAT is safe and effective — incomplete
- Participant counts, study counts, or cost figures as the headline stat — never permitted

**Stat boxes show outcomes only — effect sizes, risk changes, response rates, or complete qualitative clinical conclusions when no single number captures the finding. NEVER:**
- Participant counts ("868 participants", "2,441 participants")
- Study counts ("10 RCTs", "39 studies")
- Cost figures ("£113m", "£2.3bn")
- Incomplete qualifiers ("safe & effective" without the subject; "OR 2.67" without explanation)

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
- prochlorperazine (Stemetil)
- betahistine (Serc)
- cinnarizine (Stugeron)
- lamotrigine (Lamictal)
- levetiracetam (Keppra)
- sodium valproate (Epilim)
- carbamazepine (Tegretol)
- lacosamide (Vimpat)
- topiramate (Topamax)
- donepezil (Aricept)
- rivastigmine (Exelon)
- galantamine (Reminyl)
- memantine (Ebixa)

### Lay-clarification brackets — ALL medical terminology
**The general rule:** Every medical or clinical term that a lay reader would not immediately understand must have a plain English definition in brackets on first use in each section. This applies to anatomical terms, physiological terms, symptom descriptors, drug class names, procedural terms, and diagnostic labels — not just statistical measures.

Examples of terms requiring lay clarification:
- Anatomical: periorbital (around the eye) · temporal (at the temple) · ipsilateral (same side) · bilateral (both sides)
- Symptoms: lacrimation (tearing) · rhinorrhoea (runny nose) · ptosis (drooping eyelid) · miosis (pupil constriction) · conjunctival redness (redness of the white of the eye)
- Clinical: teratogenic (capable of causing harm to a developing foetus) · hepatotoxic (toxic to the liver) · tachycardia (fast heart rate)
- Drug classes: tricyclic antidepressant · beta-blocker · prokinetic antiemetic
- Neurological: EEG (electroencephalogram — brain activity recording) · MRI (magnetic resonance imaging) · postictal (recovery period after a seizure) · tonic-clonic (stiffening then rhythmic jerking)

**Statistical measures** (also require lay clarification on first use per section):
- HR (hazard ratio — HR 1.23 = 23% higher risk)
- RR (relative risk)
- OR (odds ratio)
- SMD (standardised mean difference — effect size)
- NNT (number needed to treat)
- CI (confidence interval)
- PAR (population-attributable risk)

### Inline lay definitions — safety-critical and Key Terms box terms
Two rules apply to all article HTML files:

**Rule 1 — Safety-critical terms:** Any clinical term that carries significant implications for the reader — especially safety-critical ones such as teratogenicity, hepatotoxicity, nephrotoxicity, arrhythmia, or similar — must always have an **inline lay definition** in the same sentence where the term first appears. A Key Terms box entry alone is not sufficient.

**Rule 2 — Structured lists and criteria boxes:** When a medical term that appears in the Key Terms box also appears in a structured list, numbered criteria, or diagnostic criteria box — where prose inline explanation is not practical — add **(see Key Terms below)** immediately after the term.

### Cite the paper's exact numerical expression — never convert or paraphrase — LOCKED APRIL 2026
When a paper reports a statistic, use its exact wording and numerical form in every location it appears. Never convert between forms — do not turn ">30%" into "1 in 3", "33%", or "around a third"; do not turn "1 in 1,000" into "0.1%". The conversion introduces inaccuracy and misrepresents the source. This rule applies to the stat grid, research cards, Key Terms definitions, body prose, Putting It Together box, and the teleprompter. Before delivering any file, cross-check every instance of every figure for consistency against the source paper's exact wording.

---

## 9. VISUALS HTML STANDARDS

### VIEWPORT MAXIMISATION — MANDATORY RULE (LOCKED APRIL 2026)

**Every visuals slide must fill the available viewport. This is non-negotiable.**

The fixed viewport is `100vw × 100vh` minus the 52px topbar and 32px dots bar = approximately `calc(100vh - 84px)` of usable vertical space. Every slide must use this space aggressively. Content that occupies only 60–70% of the screen with large empty areas is a failure.

**Required minimums/maximums — apply to every slide:**
- Slide padding: maximum `1rem 1.5rem 0.8rem` — never `1.8rem` or more top padding
- Slide title: minimum `1.55rem` — never `1.35rem`
- Slide subtitle margin-bottom: maximum `.6rem` — never `1rem`
- All body text in cards and rows: minimum `.90rem` — never `.75rem` or `.80rem`
- Card/row gaps: maximum `.5rem` — never `.7rem` or `.9rem` between items
- Info/step row body line clamp: minimum 3 lines — never 2 lines (wastes space)
- Intro stat numbers: minimum `2.3rem` — never `1.8rem`

**CTA slide — confirmed working sizes (April 2026):**
- Central icon: `5.5rem` — must dominate the slide
- Headline: `clamp(2.8rem, 5.5vw, 4.2rem)`
- Italic subline: `1.2rem`
- Card emoji icons: `2.2rem`
- Card title text: `.96rem`

**Closing slide — confirmed working sizes (April 2026):**
- Logo: `2.8rem`
- Tagline: `1.05rem`
- Link/series label: `1rem`

**The test before delivering any visuals file:** Open every slide in a browser. Is the content filling at least 85% of the visible area? If large white/dark expanses of empty space are visible below the content, the sizing is wrong. Increase font sizes and reduce gaps until the slide feels full.

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

**The complete clinical conclusion rule applies equally to visuals ev-stat-boxes.**

### CTA slide standard (all visuals files)
- Full-screen with radial gold-glow background + pulsing icon halo (3.2s drop-shadow)
- **Central icon: minimum `5.5rem`** — the icon must dominate the slide visually
- **Fraunces headline: minimum `clamp(2.8rem, 5.5vw, 4.2rem)`**
- **Fraunces italic subline: minimum `1.2rem`**
- 4 action cards (NOT chips) — emoji + Fraunces bold label, gradient + gold border
- **Card emoji icons: minimum `2.2rem`**
- **Card title text: minimum `.96rem`**
- **Medical-advice disclaimer box required:** ⚕️ icon · dashed border · "Health education — not medical advice" + full educational-voice phrase
- Closing slide: same disclaimer box as CTA slide
- Reference: `hypertension-visuals.html`

### Closing slide standard (all visuals files)
- **Logo text: minimum `2.8rem`**
- **Tagline: minimum `1.05rem`**
- **Link/series label: minimum `1rem`**
- Same disclaimer box as CTA slide, centred
- Background: gradient from series dark colour to `#0d0d1a`

### Readability standards — visuals (all rgba thresholds)
**Topbar:**
- Subtitle: minimum 0.75rem, `rgba(255,255,255,0.75)`
- Slide counter: minimum 0.85rem, `rgba(255,255,255,0.90)`
- Keyboard hint: minimum `rgba(255,255,255,0.60)`

**Animation/diagram text:**
- Labels: minimum 13px, `rgba(255,255,255,0.80)`
- SVG annotations: minimum 10px, `rgba(255,255,255,0.60)`

**Source attributions:**
- Minimum 0.75rem, `rgba(255,255,255,0.55)` on dark backgrounds
- Minimum 0.75rem, `#2C2C2C` on light backgrounds

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

### Video length standard
- Maximum 4–5 minutes
- Word count: approximately 600–750 words at ~150 words per minute
- Cut ruthlessly — no redundant examples, tight preamble, merge segments where possible

### Teleprompter content standard
Each teleprompter must deliver:
1. Fundamental messages stated clearly
2. Key statistics with exact numbers — no rounding drift from the article figures
3. Specific practical pointers — "add 1,000 steps/day" not "move more"; "30g fibre daily" not "eat more fibre"

Every segment serves message, statistic, or action — cut what doesn't earn its place.

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
- Camera-ready HTML files: full-screen, responsive, auto-animate on load, bold for filming
- Presenter HTML: bold red `.diagram-cue` callout box shows filename to open on second screen
- Dr Paul reads from presenter; diagram HTML full-screened on second screen
- Layout: `flex-start`, `6vh` top padding (prevents title clipping)

---

## 12. QC CHECKLIST (run before every upload)

1. Readability — no pale text below colour minimums specified above
2. References — full citation blocks with DOI; pill links verified in same session; **each cited stat confirmed to be in the specific paper cited, not just in a secondary source that references it**
3. Research flags ⚑ — all claims verified against source; no unverified links
4. Graphics — standalone animation file exists; presenter has matching inline visual
5. Article ↔ presenter consistency — all facts, study names, years, citations match exactly
6. Educational voice — no forbidden phrases; canonical phrase correct and in full throughout
7. Drug names — brand names in brackets after all generics
8. **Lay-clarification — ALL medical terminology in brackets on first use per section**
9. **Research card clinical conclusions — complete clinical conclusion test (LOCKED APRIL 2026)**
10. Research card stats — outcomes only; never participant/study counts or cost figures as headline stat
11. CTA slide — disclaimer box present with full canonical phrase
12. Closing slide — same disclaimer box present
13. Copyright year — 2026
14. Body text weight — `font-weight:400` throughout (never 300 in body)
15. No `opacity:0` animations on article body sections — content immediately visible
16. **ev-stat-box — `.ev-conditions` font is `.78rem`, padding is `.9rem .75rem`, `overflow:hidden` present**
17. **NICE guideline numbers — verify CG vs NG via web search in the same session. Never cite from memory.**
18. **Safety-critical terms — any term like teratogenic, hepatotoxic, nephrotoxic must have an inline lay definition**
19. **Structured lists and criteria boxes — any Key Terms box term appearing in a list or criteria box must have "(see Key Terms below)" added**
20. **VIEWPORT MAXIMISATION — open every slide in a browser before delivering. Content must fill at least 85% of the visible area.**
21. **PMID VERIFICATION — every PMID must be verified by web search in the same session. A PubMed URL must be found in search results confirming the PMID resolves to the correct paper. Never include a PMID from memory or inference.**
22. **STRICT SOURCE RULE — every stat, claim, and causal attribution must be traceable to an approved source. Charity and advocacy websites (Epilepsy Action, Alzheimer's Society, etc.) are not approved. Derived figures (calculating deaths from a prevalence rate) are not acceptable — only cite figures explicitly stated in the approved source. If a stat cannot be traced, omit it.**
23. **EXACT FIGURE RULE — use the paper's exact numerical expression everywhere. Never convert between forms (">30%" must not become "1 in 3" or "33%"; "1 in 1,000" must not become "0.1%"). Cross-check stat grid, research cards, Key Terms, body prose, Putting It Together, and teleprompter for consistency before delivering any file.**

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
Edge incognito uploads occasionally capture the Claude.ai loader HTML (~5,140 bytes, begins with "data-build-id") instead of the actual file. Never false-alarm on byte size alone. Verify content via GitHub raw URL before any assessment.

---

## 14. APPROVED RESEARCH SOURCES

BMJ · NICE guidelines · Cochrane Database · NEJM · The Lancet · JAMA · BMJ Best Practice · PubMed · NHS/NHS Digital · ONS · CDC · WHO · Global Burden of Disease Study · ESC/EAS guidelines · Alimentary Pharmacology & Therapeutics · European Heart Journal · QJM · Epilepsia · Seizure: European Journal of Epilepsy · JAMA Neurology

**NOT approved:** Epilepsy Action · Alzheimer's Society · Alzheimer's Research UK · any charity or advocacy website · commercial health sites · forum content · any secondary source that cites a primary paper without being that primary paper.

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
3. **Contains the specific stat or finding claimed — not just plausibly could contain it**
4. URL/DOI resolves to the correct article — fetch the abstract or full text if needed to confirm
5. **PMID resolves to the correct paper — a PubMed URL must be found in search results**

**Step 3 is the step that fails most often.** Finding a paper by the same author on the same topic is not sufficient. The specific numerical claim must be traceable to that specific paper.

**Step 5 is a new rule confirmed April 2026.** Claude has repeatedly generated plausible-sounding but incorrect PMIDs. Every PMID must be verified by web search. A search result showing the PMID in a PubMed URL is required. This is non-negotiable.

**Derived statistics are not acceptable.** If a source provides a prevalence rate (e.g. 1 in 1,000 per year) but not the absolute UK death count, Claude must not calculate and cite an absolute figure. Only figures explicitly stated in the approved source may be used.

**Never include an unverified link. Never assume a study exists based on a plausible-sounding citation.**

**NICE guideline number rule:** Always verify the exact NICE guideline number — including whether it is CG or NG — via web search before citing. Never from memory.

---

## 17. RETROFIT STATUS (retroactive standards across existing articles)

### Confirmed complete
- Educational voice: confirmed complete across Articles 01–26 (as built)
- Article HTML retrofits (Articles 13–18): confirmed complete
- Visuals and teleprompters (Articles 13–18): confirmed built

### Outstanding — to confirm and apply
- Research card stat standard (outcomes only, not counts): outstanding across 01–11
- **Research card complete clinical conclusion standard: outstanding across 01–23**
- Inline citations (superscripts linking to refs): outstanding across 01–11
- CTA slide high-impact standard (disclaimer box, gold-glow, 4 action cards): outstanding across 01–11
- Visuals layout standard (horizontal rows, ev-stat-row): outstanding across 01–11
- Key terms / hero visibility standards: outstanding across 01–11
- Teleprompter cue box standard: confirm per-file which were built before standard was set

---

## 18. KEY LEARNING POINTS (accumulated)

### NICE CG99 is for children only — never cite for adults
NICE CG99 covers constipation in **children and young people only**. For adult constipation the correct reference is **NICE CKS** at `cks.nice.org.uk/constipation`.

### Dr Paul's experience is 20+ years, not 30+
All references to clinical experience must read "20+ years" or "over twenty years as an NHS GP".

### Local link testing — expected not to work
When Dr Paul opens a downloaded HTML file locally and clicks article links, they appear broken. This is expected and correct — links are correctly coded as relative and work on the live GitHub site.

### Dr Paul prefers Claude to handle all file edits
Never ask Dr Paul to make manual edits to files via the GitHub editor.

### Conditions page — always rebuild, never patch
When helf-school-conditions.html needs significant changes, rebuild from scratch.

### Educational voice — systemic issue in older files
When fetching any older file for any purpose, audit for forbidden phrases and correct them as part of the work.

### Teleprompter cue box — advance THEN read
The cue box precedes the script for its segment. Dr Paul advances the slide first, then reads. Cue box label: `▶ ADVANCE NOW — then read`.

### Large file writing — use create_file not bash
For HTML files over ~400 lines, `create_file` is the correct tool. Bash heredocs fail on large HTML.

### File already exists — delete and retry
If `create_file` reports "file already exists", delete the existing placeholder (`rm /home/claude/filename.html`) and retry.

### Constipation article — April 2026 research decisions
- NICE CG99 explicitly excluded (children only)
- Rome IV criteria used as the clinical framework
- Laxative stepwise shown as 4 numbered steps with all brand names included
- Research card 1: macrogol vs lactulose (Cochrane 2010, CD007570)
- Research card 2: fibre supplementation response rate 77% vs 44% (Christodoulides 2016)

### Secondary source cited instead of primary — April 2026
In the headaches article, Reference 5 was incorrectly cited. The rule strengthened: Step 3 of the pre-draft verification rule now explicitly requires confirming the specific stat is in the specific paper.

### Lay-clarification rule broadened — April 2026
Every medical or clinical term a lay reader would not immediately understand requires a plain English definition in brackets on first use in each section. General rule, not a list of specific terms.

### Safety-critical terms need inline lay definitions — April 2026
Any clinical term that carries significant implications for the reader must have an inline lay definition in the same sentence, not just a Key Terms box entry.

### Structured lists — Key Terms terms need "(see Key Terms below)" — LOCKED APRIL 2026
When a medical term from the Key Terms box appears in a structured list or criteria box, add "(see Key Terms below)" immediately after the term.

### NICE guideline number verification — CG vs NG — LOCKED APRIL 2026
NICE uses two guideline series: **CG** (pre-~2014) and **NG** (from ~2014 onwards). Always verify via web search in the same session.

### Visuals must maximise viewport space — LOCKED APRIL 2026
Slide padding reduced to maximum `1rem 1.5rem 0.8rem`; all body text raised to minimum `.90rem`; all gaps reduced to maximum `.5rem`; line clamp raised to minimum 3 lines; slide title raised to minimum `1.55rem`.

### ev-stat-box text overflow — confirmed fix April 2026
`.ev-stat-box` `padding:.9rem .75rem` + `overflow:hidden`; `.ev-conditions` `font-size:.78rem; line-height:1.32`. Do not increase either value.

### Research card stat boxes must state complete clinical conclusions — LOCKED APRIL 2026
Every research card stat box must state the complete clinical finding as it is relevant to the patient. Statistical machinery (ORs, RCT counts, CIs) must never be the headline finding.

### PMIDs must be verified by web search every time — LOCKED APRIL 2026
Claude has repeatedly generated plausible-sounding but incorrect PMIDs. This has happened across multiple sessions. The fix: every PMID must be found in a web search result showing the PubMed URL before it is included in any file. No exceptions. A PMID from memory or inference is not acceptable.

### Charity and advocacy websites are not approved sources — LOCKED APRIL 2026
Epilepsy Action, Alzheimer's Society, Alzheimer's Research UK, and similar organisations produce valuable work but are not in the approved source list for helf.school. Stats and claims derived from charity websites must not be included even when they appear credible. Derived statistics (e.g. calculating UK annual deaths from a per-1,000 incidence rate) are also not acceptable — only figures explicitly stated in an approved source may be cited. If a stat cannot be traced to an approved source, omit it.

### Causal attributions require primary citations — April 2026
Causal claims (e.g. "driven partly by disability discrimination") require a specific primary citation confirming that causal relationship. Inference from context is not sufficient. If the causal attribution cannot be cited, it must be removed.

### NEAD — use neutral language — April 2026
Non-epileptic attack disorder (NEAD) should not be described as "typically a manifestation of psychological distress." This is an oversimplification that does not reflect current understanding of functional neurological disorder and may cause offence. Use neutral language: "episodes that resemble seizures but are not caused by abnormal electrical activity in the brain."

### Drug-resistant epilepsy — cite the paper's exact figure — April 2026
Kwan & Brodie NEJM 2000 reports "more than 30 percent" — not "1 in 3" or "33%". Always cite the paper's exact language. Cross-check article prose, stat grid, Key Terms, research cards, and Putting It Together section for consistency.

### session-start-rules.md status table conflict — April 2026
The session-start-rules.md file fell out of sync with project knowledge multiple times. Fix applied: Rule 6A added — project knowledge always overrides session-start-rules on status.

---

## 19. OUTSTANDING TASKS (April 2026)

### Immediate — GitHub uploads required
- Upload Articles 21, 22, 23, 24, 25, 26 files to GitHub (6 articles × 3 files = 18 files)
- Update `helf-school-conditions.html` to show Articles 21–26 as live once uploaded

### Verification
- `hypertension.html` references 5 & 6 — Cochrane PubMed IDs flagged ⚑ unverified

### Series planning
- **Neurological series (Articles 22–26)** — all complete April 2026
- **Next series TBD** — possible extensions: Stroke and TIA (bridges cardiovascular) · Parkinson's Disease

### Retrofit backlog (Articles 01–11 only — 13–26 confirmed complete)
- Research card clinical conclusion standard
- Research card stat standard (outcomes only, not counts)
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
| 3 | Lee-Robichaud H et al. Cochrane Database Syst Rev 2010;(7):CD007570. PMID 20614462 | doi.org/10.1002/14651858.CD007570.pub2 | Macrogol superior to lactulose across all outcomes |
| 4 | Christodoulides S et al. Aliment Pharmacol Ther 2016;44(2):103–116. PMID 27170558 | doi.org/10.1111/apt.13662 | Fibre: 77% response vs 44% placebo |
| 5 | NHS Inform. Constipation | nhsinform.scot/illnesses-and-conditions/stomach-liver-and-gastrointestinal-tract/constipation | Prevalence: 1 in 7 adults UK at any time |

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
**Teleprompters (all series):** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd · ibs · bloating · coeliac · masld · acid-reflux · constipation · migraine · headaches · dizziness-vertigo · memory-dementia · epilepsy

**Visuals (all series):** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd (screen) · ibs · bloating · coeliac · masld · acid-reflux · constipation · migraine · headaches · dizziness-vertigo · memory-dementia · epilepsy

**Screen files:** Ar_barretts-screen · Ar_sphincter-screen · ibd-gut-screen · bloating-gut-screen · bloating-fodmap-screen

---

## 22. SESSION START RULES (content of helf-school-session-start-rules.md)

### Rule 1 — Read before acting
Read `helf-school-project-knowledge.md` AND `helf-school-session-start-rules.md` in full before any output, checks, or assessments. No exceptions.

### Rule 2 — Article inventory is the source of truth
The article inventory in Section 3 of this document is authoritative.

### Rule 3 — 5,140-byte files are NOT corrupted
Files approximately 5,140 bytes beginning with "data-build-id" are Edge incognito loader stubs. Never flag as corrupted.

### Rule 4 — Never produce output before confirming understanding
Before building or modifying any file, confirm: (1) which article/file, (2) current status per inventory, (3) canonical reference checked.

### Rule 5 — Educational voice check on every file
Audit every file for forbidden phrases before delivery.

### Rule 6 — Cross-check article ↔ teleprompter before delivery
All key statistics, study names, years, and citation authors must match exactly.

### Rule 6A — Project knowledge always overrides session-start-rules on status
If the file status table in session-start-rules.md conflicts with Section 3, this document is correct.

### Rule 7 — One large file per turn
Build very large HTML files one per turn. Wait for confirmation before proceeding.

### Rule 8 — Verify references before building
Run web searches to verify all planned citations before building any article HTML.

### Rule 9 — Update project knowledge at session end
Update this document and session-start-rules.md together at the end of every session.

### Rule 10 — NICE CG99 is children only
Never cite NICE CG99 in any adult article.

### Rule 11 — Research card complete clinical conclusion
Before presenting any article or visuals file, audit every research card stat box against the complete clinical conclusion rule.

### Rule 12 — Visuals must maximise viewport space
Every visuals slide must fill the available viewport. See Section 9 for full specification.

### Rule 13 — PMIDs must be verified by web search every time
Every PMID must be found in a web search result before inclusion. No PMID from memory or inference. No exceptions.

### Rule 14 — Strict source rule
Only approved sources (Section 14) may be cited. Charity/advocacy websites are not approved. Derived statistics are not acceptable. If a stat cannot be traced to an approved source, omit it.

---

## 23. ARTICLE-SPECIFIC NOTES — KNOWN ISSUES

### hypertension.html
References 5 and 6 — Cochrane PubMed IDs flagged ⚑ unverified.

### statins.html
Very large HTML file — has caused mid-build crashes. Handle in one dedicated turn.

### conditions page (helf-school-conditions.html)
Rebuilt April 2026. If further changes are needed, rebuild the whole file. Currently shows 20 live articles — needs updating to 26 once all pending uploads complete.

### index.html
Rebuilt April 2026 with all 12 corrections. "About Dr Paul" correctly reads "NHS GP · 20+ years".

### dizziness-vertigo.html
Research flags noted: NICE CKS Vertigo (last revised 2022 — check for updates); betahistine/Ménière's evidence contested (BEMED 2016 trial); 92-week UK delay figure cited via von Brevern 2007 rather than primary UK source.

### epilepsy.html — April 2026 decisions
- NICE NG217 (April 2022, updated January 2025) used as primary clinical reference
- Kwan & Brodie NEJM 2000: figure is "more than 30%" not "1 in 3" — all instances corrected
- SUDEP stat: ~1 in 1,000 per year (Thurman et al Epilepsia 2014, PMID 24903551) — no derived UK death count included
- Misdiagnosis rate: 26.1% from Smith, Defalla & Chadwick QJM 1999 (PMID 10209668) — specific primary UK paper, not a range
- NEAD described neutrally: "episodes that resemble seizures but are not caused by abnormal electrical activity in the brain" — not attributed to psychological distress
- Disability/unemployment paragraph removed — Epilepsy Action statistic not an approved source; no causal citation for discrimination claim
- Valproate teratogenicity: inline lay definition present in same sentence; MHRA Valproate Pregnancy Prevention Programme referenced
- 6 references total; all PMIDs verified by web search in session

---

## 24. PLANNING NOTES — NEXT SERIES

### Neurological Series (Articles 22–26) — COMPLETE APRIL 2026
All five articles built. All 15 files (article + visuals + teleprompter × 5) completed April 2026. Upload to GitHub pending.

### Possible next series (to confirm with Dr Paul)
- **Stroke and TIA** — bridges well with cardiovascular series; high public interest
- **Parkinson's Disease** — rising incidence, ageing population, strong educational need
- **Cancer Series** — discussed as a future series; no article list defined yet

---

## 25. PROCESS NOTES — FILE CREATION IN CLAUDE

### Writing large HTML files
Use `create_file` for all HTML files. Bash heredocs fail on large HTML content.

### File already exists error
If `create_file` reports "file already exists", run `rm /home/claude/filename.html` then retry.

### Outputs directory
All files for Dr Paul must be copied to `/mnt/user-data/outputs/` and presented via `present_files`.

### QC before presenting
Always run bash QC checks (grep for key phrases, count required elements) before copying to outputs.

### Research card stat box — writing guidance
1. Identify the clinically important finding
2. State it as a complete subject + finding
3. Check: can a lay reader understand this from the stat box alone?
4. Put supporting detail in the body text and `.ev-conditions` line
5. Never lead with ORs, RCT counts, confidence intervals, or participant counts

### PMID verification — mandatory process
1. Search for the paper by author, title, journal, year
2. Find a PubMed URL in the search results
3. The PMID is the number in that URL
4. Only then include the PMID in the file
5. Never include a PMID from memory — it will be wrong

---

*End of document. Update at the end of every session. Download via Artifact panel. Upload to both GitHub (pls4286/helfschool/main) and the Claude Project to take effect in future sessions.*
