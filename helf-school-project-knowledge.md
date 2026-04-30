# helf.school — Project Knowledge
**Last updated: April 2026**

---

## ⚠️ DOCUMENT INTEGRITY — CLAUDE MUST READ THIS BEFORE ANY SESSION WORK

**This document has 25 numbered sections. Minimum expected line count: ~1552 lines.**

**Note — April 2026:** The authoritative version is the one stored in the Claude project (114KB). When pasted through chat, blank lines collapse, reducing apparent line count. The 1552-line figure is the reliable baseline for `wc -l` checks in Claude's bash environment. All content is present at this count.

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

**Project knowledge update protocol — LOCKED APRIL 2026:** At session end, the mandatory process is:
1. `web_fetch` the live version from GitHub (not the project copy, which may be stale)
2. Write the exact fetched content to `/home/claude/helf-school-project-knowledge.md`
3. `str_replace` to add only the new session content — never rewrite from scratch
4. `bash wc -l` to confirm new line count ≥ original
5. Deliver for download and re-upload to both GitHub and the Claude Project

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

7a. **ev-outcome reason audit — LOCKED APRIL 2026** — for every research card, confirm the ev-outcome line contains BOTH the finding AND the reason/comparison that produced the stat. The comparison ("CT screening vs no screening", "pembrolizumab vs chemotherapy", "osimertinib vs standard EGFR therapy") must be in ev-outcome — never relegated to ev-conditions alone. Read only the ev-stat-row and ev-outcome together: does a reader immediately understand the stat AND why it is that number? If not, rewrite ev-outcome to include the comparison.

8. **Stat grid citation audit — LOCKED APRIL 2026** — run `grep -A 3 "stat-prose"` before presenting any article and confirm every `.stat-prose` instance has a `ref-` link. Every stat grid card must carry a superscript inline citation. No exceptions.

9. **ALL STATS IN ALL LOCATIONS REQUIRE CITATIONS — LOCKED APRIL 2026** — scan every paragraph and every text element in the file for numerical figures and percentages. Every stat in every location must carry an inline superscript citation. This covers: body prose paragraphs, Key Terms box definitions, research card stat boxes and body text, Putting it all together box, discussion cards, myth panel evidence text, and visuals slide text. Stat grid cards are covered by audit item 8. This broader audit covers all other locations. No stat goes uncited anywhere.

**For every visuals file, additionally run:**

10. **ev-stat-box check** — `.ev-conditions` font is `.78rem`, padding is `.9rem .75rem`, `overflow:hidden` present. ev-conditions text is short enough to fit 220px column.

11. **animate-ready check** — all animated cards have `animate-ready` class. No hardcoded `opacity:0` on card elements.

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
- **Cancer (series): `#2A5A3A` (forest green) — confirmed April 2026. Dark variant: `#1A3A25`.**

### Series dark variants — for research card stat box gradients

| Series | Primary | Dark variant | Status |
|--------|---------|-------------|--------|
| Cardiovascular | `#C8423A` | `#8A2020` | ✅ Confirmed April 2026 |
| Neurological | `#6B5EA8` | `#4A4080` | ✅ Confirmed April 2026 |
| Digestive | `#D47C3A` | `#8A4A1A` | ✅ Confirmed April 2026 |
| Fatigue | `#3A8A7A` | `#1A5A4A` | ✅ Confirmed April 2026 |
| Medical Decision | `#2E6BA8` | `#1A3A6A` | ✅ Confirmed April 2026 |
| Practical Health | `#7A6A2E` | `#4A3A1A` | ✅ Confirmed April 2026 |
| Cancer | `#2A5A3A` | `#1A3A25` | ✅ Confirmed April 2026 |

**All dark variants confirmed April 2026. Research card colour retrofit is now unblocked across all series.**

### Fonts
- Headings: Fraunces (serif)
- Body: DM Sans — minimum weights required: `wght@400;500;600;700`
- **Never use weight 300 anywhere in body text**

### Logo
Open-book SVG + "HEALTH EDUCATION" tagline. Used in all site pages.

---

## 3. ARTICLE INVENTORY — COMPLETE AND CURRENT (source of truth)

Three files required per article: **Article HTML · Visuals HTML · Teleprompter HTML**

### Series A — Cardiovascular Health (Articles 01–07)

| # | Title | Slug |
|---|-------|------|
| 01 | Hypertension (High Blood Pressure) | hypertension |
| 02 | Cholesterol Explained | cholesterol |
| 03 | How Doctors Estimate Heart Attack Risk | heart-attack-risk |
| 04 | Statins — Benefits & Risks | statins |
| 05 | How to Reduce Cardiovascular Risk with Lifestyle Changes | lifestyle-changes |
| 06 | Salt and Blood Pressure | salt-blood-pressure |
| 07 | Do Supplements Lower Cholesterol? | supplements-cholesterol |

### Series B — Practical Health (Articles 08–12, extended to 32–33)

| # | Title | Slug | Status |
|---|-------|------|--------|
| 08 | The Mediterranean Diet | mediterranean-diet | All 3 files on GitHub ✅ |
| 09 | Sleep and Your Health | sleep | All 3 files on GitHub ✅ |
| 10 | Exercise — the Evidence Base | exercise | All 3 files on GitHub ✅ |
| 11 | Stress and the Body | stress | All 3 files on GitHub ✅ |
| 12 | Alcohol — What the Evidence Shows | alcohol | All 3 files on GitHub ✅ |
| 32 | Breast Awareness — What to Look For | breast-awareness | Planned — not yet built |
| 33 | Testicular Awareness — What to Look For | testicular-awareness | Planned — not yet built |

### Series C — Digestive Health (Articles 13–21)

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
| 21 | Constipation | constipation | All 3 files built April 2026 ✅ — on GitHub |

### Series D — Neurological Health (Articles 22–26)

| # | Title | Slug | Status |
|---|-------|------|--------|
| 22 | Migraine | migraine | All 3 files built April 2026 ✅ — on GitHub |
| 23 | Headaches — Types and Red Flags | headaches | All 3 files built April 2026 ✅ — on GitHub |
| 24 | Dizziness and Vertigo | dizziness-vertigo | All 3 files built April 2026 ✅ — on GitHub |
| 25 | Memory, Cognition and Dementia | memory-dementia | All 3 files built April 2026 ✅ — on GitHub |
| 26 | Epilepsy — What It Is and How It's Managed | epilepsy | All 3 files built April 2026 ✅ — on GitHub |

### Series E — Cancer (Articles 27–31) — ESTABLISHED APRIL 2026
Series colour: `#2A5A3A` (forest green). Dark variant: `#1A3A25`. Note: initial proposed colour `#8A3A5A` (deep rose) was rejected — contrast issues. Forest green confirmed April 2026.

| # | Title | Slug | Status |
|---|-------|------|--------|
| 27 | Breast Cancer | breast-cancer | All 3 files built April 2026 ✅ — on GitHub ✅ |
| 28 | Prostate Cancer | prostate-cancer | All 3 files built April 2026 ✅ — on GitHub ✅ |
| 29 | Lung Cancer | lung-cancer | All 3 files built April 2026 ✅ — on GitHub ✅ |
| 30 | Bowel (Colorectal) Cancer | bowel-cancer | All 3 files built April 2026 ✅ — on GitHub ✅ |
| 31 | Melanoma and Skin Cancer | melanoma | All 3 files built April 2026 ✅ — on GitHub ✅ |

**Total articles with all 3 files on GitHub: 31. All complete ✅.**

---

## 4. SITE FILES — CURRENT STATUS

| File | Status | Notes |
|------|--------|-------|
| index.html | Rebuilt April 2026 | 20+ years corrected; voice fixed; 2026 |
| helf-school-conditions.html | Rebuilt April 2026 | 28 articles live; hero stat needs updating to 31 |
| helf-school-membership.html | On GitHub | Pricing: £0 / £6pm or £60pa / £150 lifetime |

### index.html — April 2026 corrections applied
1. Hero h1: "Understanding your heart" → "Understanding your health"
2. Hero subtitle: "cardiovascular health" → "your health"
3. Why helf.school pillar: **30+ years → 20+ years** (primary fix)
4. Copyright © 2025 → © 2026
5. Disclaimer doc date: March 2025 → April 2026 · Version 1.0 → 1.1
6. "About Dr [Name]" → "About Dr Paul" throughout
7. "Heart Conditions A–Z" footer link → `helf-school-conditions.html`
8. All canonical phrases corrected throughout

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

### Educational voice — practical guidance

**Describing what medicine knows:** "Clinically recognised as a time-sensitive condition — 111/urgent GP exists for this" rather than "Call 111 immediately."

**Describing what services exist:** "The NHS screening programme invites women aged 50–70" rather than "Ask your GP about breast screening."

**Describing shared decisions:** "NICE describes this as a decision to be made with full information about benefits and risks" rather than "Discuss this with your doctor."

**The distinction that matters:** helf.school tells readers what medicine knows. It never tells them what to do. The reader decides what to do with the information — that is the essence of empowerment.

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
- **Visuals HTML:** `prostate-cancer-visuals.html` — PRIMARY CANONICAL REFERENCE confirmed April 2026. Demonstrates: 3-card split slides, canonical `cta-wrap-v2` CTA (slide 13), brand close (slide 14), ev-card research cards with series gradient stat box. `lifestyle-changes-visuals.html` remains a secondary reference for the 6-row grid pattern.
- **Teleprompter HTML:** `lifestyle-changes-teleprompter.html` (canonical for cue box standard)
- **CTA slide:** `prostate-cancer-visuals.html` slide 13 — canonical `cta-wrap-v2` pattern
- **Closing slide:** `prostate-cancer-visuals.html` slide 14 — brand close standard

### Large file crash risk
Very large HTML files (e.g. `statins.html`) can crash mid-build if too much is attempted in one turn. Strategy: build one file per turn, confirm successful delivery before proceeding to the next file.

### File fetch method (preferred)
GitHub raw URLs via `web_fetch` at session start:
`https://raw.githubusercontent.com/pls4286/helfschool/main/[filename].html`

### Dr Paul's preference
Dr Paul does not want to make manual edits to files. When corrections are needed to existing site files, Claude fetches the current file, applies all changes, and delivers the corrected file for download. Never ask Dr Paul to edit manually via the GitHub editor.

---

## 8. ARTICLE HTML STANDARDS

### Section structure (all condition articles)
1. What is it?
2. Key Terms box — navy background by default; series-colour gradient for Cancer Series — sits between sections 1 and 2
3. Why does it matter? — stat grid + prose paragraphs
4. What your doctor might discuss
5. What the research shows
6. "Putting it all together" — navy box by default; series-colour gradient for Cancer Series — italic text, bold closing line
7. References
8. Research flags ⚑ — for Dr Paul's review before upload

### Series-colour elements — Cancer Series rule — LOCKED APRIL 2026
In Cancer Series articles, three elements use `linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%)` instead of plain navy:
1. **Key Terms box**
2. **Putting it all together box**
3. **Research card stat box**

All three confirmed in `breast-cancer.html` and `prostate-cancer.html` (April 2026). Apply to all future Cancer Series articles from the start.

### Key Terms box standards
- Default (all series): Navy background `#1B2A4A`
- Cancer Series: `linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%)` — forest green gradient
- Title: Fraunces serif, minimum 1.05rem, `#fff`
- Term labels: minimum 0.88rem, `font-weight:700`, series-light accent colour
- Definitions: minimum 0.92rem, `rgba(255,255,255,0.90)` — opacity 0.75 or 0.80 not permitted
- Body text: colour `#2C2C2C`, explicit `font-weight:400`
- Pale colours `#374151`, `#4B5563`, `#555` not permitted anywhere in articles
- No `fadeUp` or `opacity:0` animations on article body sections
- Hero subtitle: minimum `rgba(255,255,255,0.85)`
- Hero meta items: minimum `rgba(255,255,255,0.80)`
- Hero breadcrumb: minimum `rgba(255,255,255,0.75)`

### Inline citations
- Every stat or claim in prose carries a superscript number linking to anchored reference `id="ref-N"`
- Format: `<sup><a href="#ref-1">1</a></sup>`
- Superscript link colour matches the series accent colour
- **Every stat in every stat grid card must carry a superscript citation. No exceptions.**

### Visuals research card body = 2–3 sentences maximum — LOCKED APRIL 2026

**⛔ EV-BODY WORD LIMIT — LOCKED APRIL 2026:**
- **Two stacked ev-cards: ≤ 30 words**
- **Single ev-card: ≤ 44 words**
- Canonical failure: cholesterol-visuals.html slides 7–9 — ev-body texts of 33–42 words all clipped.

### CTA slide = health-action "one thing" — LOCKED APRIL 2026
The CTA slide must function as a health-action moment — not a membership pitch. The membership pitch lives on the brand close slide only. Structure: Icon · Badge · Headline · 4 rows · Medical disclaimer.

### The reason for the stat must be in the ev-outcome line — LOCKED APRIL 2026

```
ev-stat-row:   24%
ev-outcome:    reduction in lung-cancer mortality / CT screening vs no screening
ev-conditions: high-risk smokers · 10-year follow-up · NELSON trial
```

"CT screening vs no screening" is WHY the number is 24%. It cannot be the smallest text. Must appear in ev-outcome (0.95rem weight 700), never relegated to ev-conditions (0.78rem).

### All stats require citations — in every location — LOCKED APRIL 2026
Every numerical figure in any helf.school file requires an inline superscript citation — regardless of location. Body prose, Key Terms, research cards, Putting it all together, myth panels, visuals slides, teleprompter scripts.

### Subtypes, stages, and formally named sets — always list, never inline prose — LOCKED APRIL 2026
Use `<ol class="subtype-list">` — never run together as comma-separated prose. Canonical: `lung-cancer.html` Section 1.

### Reference numbering — LOCKED APRIL 2026
References must display visible numbers. Use CSS `counter-reset` and `counter-increment` on `.ref-block`. Canonical: `prostate-cancer.html`.

### Article research card display standard — LOCKED APRIL 2026

```css
.research-card { grid-template-columns: 220px 1fr; border-radius: 10px; }
.ev-stat-box { background: linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%); padding: 1.1rem .9rem; overflow: hidden; }
.ev-kf-label { font-size: .72rem; font-weight: 700; color: var(--amber); text-transform: uppercase; }
.ev-stat-row { font-size: 3.2rem; font-weight: 900; color: #fff; line-height: 1.0; }
.ev-outcome { font-size: .95rem; font-weight: 700; color: rgba(255,255,255,0.95); }
.ev-conditions { font-size: .80rem; color: rgba(255,255,255,0.72); }
.ev-body p { font-size: .93rem; line-height: 1.72; }
```

**Stat box background: series-colour gradient — never plain navy. ev-stat-row: 3.2rem weight 900. ev-kf-label: always amber `#E8A84A`.**

### Research card stat standard — complete clinical conclusion rule — LOCKED APRIL 2026
Every research card stat box must state the complete clinical finding in terms immediately meaningful to a lay reader. The test: can a lay reader understand the clinical finding from the stat box alone, without reading the body text? If not, rewrite.

**Stat boxes show outcomes only — effect sizes, risk changes, response rates. NEVER: participant counts, study counts, cost figures, incomplete qualifiers.**

### Full references standard
Full citation block: authors · title · journal · year · vol · pages · DOI. Pill links: journal DOI and PubMed — verified by web search in same session only.

### Drug naming standard
Apply everywhere, on first mention per section:
- macrogol (Movicol, Laxido) · ispaghula husk (Fybogel) · senna (Senokot) · bisacodyl (Dulcolax)
- linaclotide (Constella) · prucalopride (Resolor) · atorvastatin (Lipitor) · semaglutide (Ozempic)
- infliximab (Remicade) · adalimumab (Humira) · prochlorperazine (Stemetil)
- betahistine (Serc) · cinnarizine (Stugeron) · lamotrigine (Lamictal) · levetiracetam (Keppra)
- sodium valproate (Epilim) · carbamazepine (Tegretol) · lacosamide (Vimpat) · topiramate (Topamax)
- donepezil (Aricept) · rivastigmine (Exelon) · galantamine (Reminyl) · memantine (Ebixa)
- trastuzumab (Herceptin) · letrozole (Femara) · anastrozole (Arimidex) · exemestane (Aromasin)
- goserelin (Zoladex) · leuprorelin (Prostap) · degarelix (Firmagon) · relugolix (Orgovyx)
- docetaxel (Taxotere) · abiraterone (Zytiga) · enzalutamide (Xtandi) · bicalutamide (Casodex)
- osimertinib (Tagrisso) · erlotinib (Tarceva) · gefitinib (Iressa)
- pembrolizumab (Keytruda) · pemetrexed (Alimta)

### Lay-clarification brackets — ALL medical terminology
Every medical or clinical term that a lay reader would not immediately understand must have a plain English definition in brackets on first use in each section.

**Statistical measures** (require lay clarification on first use per section):
- HR (hazard ratio) · RR (relative risk) · OR (odds ratio) · SMD (standardised mean difference)
- NNT (number needed to treat) · CI (confidence interval) · PAR (population-attributable risk)

### Inline lay definitions — safety-critical and Key Terms box terms
**Rule 1:** Safety-critical terms must always have an inline lay definition in the same sentence where the term first appears. A Key Terms box entry alone is not sufficient.

**Rule 2:** When a Key Terms box term appears in a structured list or criteria box, add **(see Key Terms below)** immediately after the term.

### Cite the paper's exact numerical expression — never convert or paraphrase — LOCKED APRIL 2026
Never convert between forms — do not turn ">30%" into "1 in 3" or "33%". Cross-check every instance of every figure for consistency against the source paper's exact wording before delivering any file.

---

## 9. VISUALS HTML STANDARDS

### CONFIRMED CANONICAL VISUALS REFERENCE — bowel-cancer-visuals.html (April 2026)

`bowel-cancer-visuals.html` is the first visuals file delivered with zero changes required. Confirmed canonical reference for all future visuals builds.

---

### VISUALS PRE-BUILD CHECKLIST — MANDATORY BEFORE WRITING ANY VISUALS HTML

**1. SLIDE POSITIONING — use explicit width/height, NOT inset:0**
```css
.slide {
  position:absolute; top:0; left:0; width:100%; height:100%;
  display:flex; flex-direction:column;
  opacity:0; visibility:hidden; pointer-events:none;
  transition:opacity .32s ease;
}
.slide.active { opacity:1; visibility:visible; pointer-events:all; }
```

**2. INTRO SLIDE — no space-between, stat grid with grid-template-rows:1fr**
```css
.intro-slide { padding:1rem 1.5rem .8rem; gap:.6rem; }
.intro-stat-grid { display:grid; grid-template-columns:1fr 1fr 1fr; grid-template-rows:1fr; gap:.65rem; flex:1; min-height:0; }
```

**3. ALL SIZES AT MAXIMUM FROM LINE ONE**
slide-title: 1.72rem · ic-icon: 1.55rem · ic-title: 1.12rem · ic-body: .93rem
ev-body p: .94rem · three-grid gap: .46rem · slide-header margin-bottom: .4rem

**4. ev-outcome MUST CARRY THE REASON — not just the finding**

**5. MONTHS SPELLED IN FULL — ev-stat-unit class**
```html
<div class="ev-stat-row">16.5</div><div class="ev-stat-unit">months</div>
```

**6. RESEARCH CARD EV-BODY = 2–3 SENTENCES MAXIMUM**
Two stacked ev-cards: ≤ 30 words. Single ev-card: ≤ 44 words.

**7. CTA SLIDE = HEALTH-ACTION "ONE THING" — not a membership pitch**

**8. NO RESEARCH OLDER THAN 12 YEARS**
Current year 2026 → nothing before 2014.

**9. EDUCATIONAL VOICE — pre-check before saving**
0 instances of forbidden phrases. Canonical phrase × 2: CTA slide + brand close.

**10. INTRO STAT CARDS — 3 cards, each with amber number + contextual label**
Label must be a full sentence explaining what the number means.

**11. INFO CARD BODY TEXT — TWO-TIER WORD LIMIT — LOCKED APRIL 2026**
- Cards WITHOUT `.ic-source`: ≤34 words maximum
- Cards WITH `.ic-source`: ≤23 words maximum
Canonical failure: lung-cancer-visuals.html April 2026, slides 4–7.

### VIEWPORT MAXIMISATION — MANDATORY RULE (LOCKED APRIL 2026)

**Every visual element must be as big as the parameters make possible.**

Required minimums/maximums:
- Slide padding: maximum `1rem 1.5rem 0.8rem`
- Slide header margin-bottom: `.4rem`
- Slide title: minimum `1.72rem`
- All body text: minimum `.93rem`
- Card/row gaps: maximum `.48rem`
- Card padding: `.82rem 1rem`
- Info/step row body line clamp: minimum 5 lines
- Ev-body paragraph: minimum `.94rem`, line clamp minimum 7 lines
- Card icons: minimum `1.55rem`
- Card titles: minimum `1.12rem`

**CTA slide confirmed working sizes:** Central icon `5.5rem` · Headline `clamp(2.8rem, 5.5vw, 4.2rem)`

### 3-CARD RULE — NEVER SHRINK TEXT TO FIT — LOCKED APRIL 2026
When a slide contains 6 cards, always split into two slides of 3 cards each. Never reduce font size or line clamp to fit. Canonical reference: `prostate-cancer-visuals.html` slides 3–10.

### 4-CARD RULE — LOCKED APRIL 2026
**Any slide with 4 cards must also split to ≤3 per slide. The QC label "⚠ 4-card (fragile)" is NOT a pass — it is a mandatory split.** Confirmed April 2026 after ibd-visuals.html 4-card treatment ladder clipped on filming viewport. QC item 38.

### Layout
- 3-card slides: `three-grid` class — `grid-template-rows: repeat(3, 1fr); gap: .55rem`
- 4/6-card slides are FORBIDDEN — always split
- Colour narrative: red = harm · amber = mechanism · green = action
- Cards: `min-height:0` + `overflow:hidden`
- Max 2 `ev-cards` per research slide
- CTA section: `cta-wrap-v2` class — `grid-template-rows: auto 1fr auto` — the ONLY correct CTA layout

### ev-stage MUST USE display:flex — NEVER display:grid — LOCKED APRIL 2026
```css
/* ✅ CORRECT */
.ev-stage { display: flex; flex-direction: column; gap: .95rem; flex: 1; min-height: 0; }
/* ❌ FORBIDDEN */
.ev-stage { display: grid; grid-template-rows: 1fr 1fr 1.5fr; }
```
Canonical failure: `stress-visuals.html` slide 7. Middle card clipped because 1fr row insufficient.

### ev-stat-box — EXACT SPECIFICATION (locked April 2026)
```css
.ev-stat-box { padding: .9rem .75rem; overflow: hidden; }
.ev-kf-label { margin-bottom: .35rem; }
.ev-stat-row { margin-bottom: .3rem; }
.ev-conditions { font-size: .78rem; line-height: 1.32; }
```
Do NOT increase padding on `.ev-stat-box`. Do NOT use `.ev-conditions` font size above `.78rem`.

### CTA slide standard — LOCKED APRIL 2026 — canonical: `prostate-cancer-visuals.html` slide 13
- `cta-wrap-v2` with `grid-template-rows: auto 1fr auto` — ONLY correct layout
- Central icon: minimum `5.5rem`
- Fraunces headline: minimum `clamp(2.8rem, 5.5vw, 4.2rem)`
- **No subline mentioning "free at helf.school"**
- 4 horizontal action rows in `.cta-rows-v2`
- `med-disclaimer` at bottom — `font-size:1rem` on `.med-disc-text` — never `.80rem`

### Closing slide standard — LOCKED APRIL 2026 — canonical: `prostate-cancer-visuals.html` slide 14
- `close-wrap` with `justify-content: flex-start` — NEVER `justify-content: center`
- helf.school logo · "Health Education" tagline · Brand headline
- Three brand pitch cards: 📚 articles · 🩺 Dr Paul credentials · 🔓 Start for free
- `med-disclaimer` at `font-size:1rem`
- Series label

### Readability standards — visuals
- Subtitle: minimum 0.75rem, `rgba(255,255,255,0.75)`
- Slide counter: minimum 0.85rem, `rgba(255,255,255,0.90)`
- Source attributions: minimum 0.75rem, `rgba(255,255,255,0.55)` on dark backgrounds
- Taglines + series label: minimum `rgba(255,255,255,0.70)`

### SERIES BACKGROUND COLOUR STANDARD — VISUALS — LOCKED APRIL 2026

| Series | Slide bg hex |
|---|---|
| Cancer | `#0e2418` |
| Cardiovascular | `#1a0808` |
| Neurological | `#0f0d1a` |
| Digestive | `#1a0e08` |
| Fatigue | `#081a14` |
| Practical Health | `#120e08` |

Near-black (`#050f08`, `#060e08`) breaks series identity — replace when any visuals file is opened.

### LAY IMPACT FIRST — VISUALS AND TELEPROMPTER STANDARD — LOCKED APRIL 2026

Three questions every visuals/teleprompter must answer: What is this? Does it affect me? Is there anything I can do about it?

#### Colour narrative (mandatory)
- **Red cards** — risk, harm, danger, mortality figures
- **Amber cards** — mechanism, process, how something works
- **Green cards** — positive outcomes, action, survival figures

#### No drug names in visuals or teleprompter
Describe treatments by class only: "immunotherapy" · "gene-targeted treatment" · "checkpoint inhibitor"

#### Teleprompter — Trial names: name, stat, meaning only
Format: name of trial → headline stat → one plain sentence. No hazard ratios, no confidence intervals.

#### Teleprompter — Three questions standard
1. What is this?
2. Does it affect me?
3. Is there anything I can do?

#### RETROFIT — apply when any visuals or teleprompter file is next opened
1. Colour narrative — replace uniform cards with red/amber/green
2. Remove drug names — replace with class descriptions
3. Check trial ev-body — reduce to 2–3 sentences max
4. Consider sequential animation for formal lists

---

## 10. TELEPROMPTER HTML STANDARDS

### Core technical spec
- RAF (requestAnimationFrame) auto-scroll
- Body font: 1.9rem
- Speed levels: `[0, 8, 14, 20, 28, 38, 50]`, default index 3 (speed 20)
- Controls: speed 1–6 · A+/A− font size · touch swipe
- Segment dots: bottom of screen
- Pause button: ⏸ — **NOT ▶ PLAY button**
- No Google Fonts — fully self-contained
- No topbar
- Segment IDs: `seg-N`

### Cue box standard
Cue box always **precedes** the script lines for its segment.
Dr Paul advances slide FIRST, then reads.
Label: `▶ ADVANCE NOW — then read`

### Cue box — paired slides
When two slides share a segment, cue box label reads the slide range: e.g. `Slides 3–4 — What is prostate cancer?`

### Video length standard
- Maximum 4–5 minutes
- Word count: approximately 600–750 words at ~150 words per minute

---

## 11. GRAPHICS AND ANIMATION STANDARDS

### Standalone animation files
- GIF capture sources only — never embedded directly in articles or presenter files

### GIF settings
Scale 0.62 · every 2nd frame · 120 colours · under 1.5MB total PPTX

### Video screen workflow
- Camera-ready HTML files: full-screen, responsive, auto-animate on load, bold for filming
- Presenter HTML: bold red `.diagram-cue` callout box shows filename
- Layout: `flex-start`, `6vh` top padding

---

## 12. QC CHECKLIST (run before every upload)

1. Readability — no pale text below colour minimums
2. References — full citation blocks with DOI; pill links verified in same session
3. Research flags ⚑ — all claims verified
4. Graphics — standalone animation file exists; presenter has matching inline visual
5. Article ↔ presenter consistency — all facts, study names, years, citations match exactly
6. Educational voice — no forbidden phrases; canonical phrase correct and in full throughout
7. Drug names — brand names in brackets after all generics
8. **Lay-clarification — ALL medical terminology in brackets on first use per section**
9. **Research card clinical conclusions — complete clinical conclusion test (LOCKED APRIL 2026)**
10. Research card stats — outcomes only; never participant/study counts
11. CTA slide — `cta-wrap-v2` with `grid-template-rows: auto 1fr auto`; `med-disc-text` at `font-size:1rem`
12. Closing slide — brand close structure; `justify-content: flex-start`; three pitch cards
13. Copyright year — 2026
14. Body text weight — `font-weight:400` throughout (never 300)
15. No `opacity:0` animations on article body sections
16. **ev-stat-box — `.ev-conditions` font is `.78rem`, padding is `.9rem .75rem`, `overflow:hidden` present**
17. **NICE guideline numbers — verify CG vs NG via web search in the same session**
18. **Safety-critical terms — inline lay definition in same sentence**
19. **Structured lists — Key Terms box terms in lists need "(see Key Terms below)"**
20. **VIEWPORT MAXIMISATION — content must fill at least 85% of visible area**
21. **PMID VERIFICATION — every PMID verified by web search in same session**
22. **STRICT SOURCE RULE — every stat traceable to approved source**
23. **EXACT FIGURE RULE — paper's exact numerical expression everywhere**
24. **STAT GRID CITATION RULE — every `.stat-prose` line has `ref-` superscript link**
25. **APPROVED SOURCE RETRIEVAL RULE — fetch directly from approved source page**
26. **CLOSING SLIDE DISCLAIMER — `justify-content: flex-start`; `med-disc-text` at `font-size:1rem`**
27. **CTA SLIDE DISCLAIMER — `font-size:1rem`; never `.80rem`**
28. **NO "FREE AT HELF.SCHOOL" ON VISUALS**
29. **3-CARD RULE — never 6 cards on one slide**
30. **REFERENCE NUMBERING — visible numbers via CSS counter**
31. **ALL STATS REQUIRE CITATIONS — every location**
32. **SUBTYPE/LIST FORMATTING — `<ol class="subtype-list">` for formally introduced sets**
33. **ev-outcome MUST CARRY THE REASON**
34. **DRUG BRAND NAMES — mandatory alongside all generic names**
35. **RESEARCH CURRENCY — no articles older than 12 years**
36. **LAY IMPACT FIRST — colour narrative, no drug names, three-question structure**
37. **ev-stage MUST USE display:flex — never display:grid**
38. **4-CARD SLIDES MUST SPLIT — "fragile" is NOT a passing QC result. Any slide with 4 or more cards must split to ≤3 cards per slide. Confirmed April 2026 after ibd-visuals.html 4-card treatment ladder clipped on Dr Paul's filming viewport. LOCKED APRIL 2026.**

---

## 13. FILE DELIVERY AND UPLOAD

### Downloading from Claude
**Primary route:** Artifact panel download button.
**Never Ctrl+S** — saves the webpage wrapper, not the source HTML.

### Uploading to GitHub
github.com/pls4286/helfschool/upload/main — sign in with Google if session expired. Individual HTML files, not zipped.

### File corruption pattern — know and ignore
Edge incognito uploads occasionally capture the Claude.ai loader HTML (~5,140 bytes). Verify content via GitHub raw URL before any assessment.

---

## 14. APPROVED RESEARCH SOURCES

BMJ · NICE guidelines · Cochrane Database · NEJM · The Lancet · JAMA · BMJ Best Practice · PubMed · NHS/NHS Digital · ONS · CDC · WHO · Global Burden of Disease Study · ESC/EAS guidelines · Alimentary Pharmacology & Therapeutics · European Heart Journal · QJM · Epilepsia · Seizure: European Journal of Epilepsy · JAMA Neurology · BJC Reports

**Cancer Research UK — approved April 2026** for UK cancer incidence, mortality, survival, and risk statistics. Always fetch their statistics pages directly.

**NOT approved:** Epilepsy Action · Alzheimer's Society · WCRF · Breast Cancer Now · any charity or advocacy website.

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
3. **Contains the specific stat or finding claimed**
4. URL/DOI resolves to the correct article
5. **PMID resolves to the correct paper — verified by web search. Never from memory.**
6. **The figure comes directly from the approved source page — LOCKED APRIL 2026**

**Derived statistics are not acceptable.** Never cite NICE CG99 for adult constipation — covers children only. Correct adult reference: NICE CKS at `cks.nice.org.uk/constipation`.

**NICE guideline number rule:** Always verify CG vs NG via web search before citing. Never from memory.

---

## 17. RETROFIT STATUS (retroactive standards across existing articles)

### Confirmed complete
- Educational voice: confirmed complete across Articles 01–26 (as built)
- **Cancer Series visuals + teleprompters (Articles 27–31) — ALL COMPLETE April 2026 ✅**
- **Cardiovascular Series visuals + teleprompters (Articles 01–07) — ALL COMPLETE April 2026 ✅**
  - CTA sequential animation applied ✅ · Brand close pitch cards applied ✅
  - `display:-webkit-box` fixed ✅ · 5/6-card slides split ✅ · ev-stage display:flex ✅
- **Practical Health Series visuals + teleprompters (Articles 08–12) — ALL COMPLETE April 2026 ✅**
- **Digestive Series retrofit — April 2026:**
  - acid-reflux (13): visuals + teleprompter ✅ retrofitted April 2026
  - bloating (15): visuals + teleprompter ✅ retrofitted April 2026
  - ibs (16): visuals + teleprompter ✅ retrofitted April 2026
  - **ibd (14): visuals + teleprompter ✅ full rebuild April 2026** — 12-slide deck; 5-card grids split 3+2; 4-card treatment ladder split 2+2 (Rule 38); series gradient ev-stat-box; sequential CTA; brand close; .cl-dot; webkit-box fixed
  - **coeliac (18): visuals + teleprompter ✅ full rebuild April 2026** — 12-slide deck; 5-card doc-grid split 3+2; series gradient; sequential CTA; brand close
  - **gallstones (19): visuals + teleprompter ✅ full structural rebuild April 2026** — pre-canonical architecture (inset:0, no nav dots, side-by-side ev-cards, quote-card close); rebuilt to canonical standard; 12-slide deck
  - **diverticular-disease (20): visuals + teleprompter ✅ full structural rebuild April 2026** — same pre-canonical architecture as gallstones; rebuilt to canonical standard; 10-slide deck; myth comparison preserved; risk/doc 5→3+2
  - **masld (17): ✅ visuals + teleprompter retrofit complete April 2026**
  - **constipation (21): ✅ visuals + teleprompter retrofit complete April 2026**

### Outstanding — to confirm and apply
- Research card complete clinical conclusion standard: outstanding across 01–23
- Stat grid citations: outstanding across all articles built before April 2026
- Visuals layout standard (3-card split, ev-stat-row): outstanding across 01–11
- Subtype list formatting: outstanding across all articles

---

## 18. KEY LEARNING POINTS (accumulated)

### NICE CG99 is for children only — never cite for adults
Adult constipation: **NICE CKS** at `cks.nice.org.uk/constipation`.

### Dr Paul's experience is 20+ years, not 30+
All references must read "20+ years" or "over twenty years as an NHS GP".

### Local link testing — expected not to work
Links are relative — work on live GitHub site, not from local downloaded file.

### Dr Paul prefers Claude to handle all file edits
Never ask Dr Paul to make manual edits.

### Conditions page — always rebuild, never patch

### Educational voice — systemic issue in older files
When fetching any older file for any purpose, audit for forbidden phrases and correct them.

### Teleprompter cue box — advance THEN read
Label: `▶ ADVANCE NOW — then read`

### Large file writing — use create_file not bash
For HTML files over ~400 lines, `create_file` is the correct tool.

### Constipation article — April 2026 research decisions
NICE CG99 excluded; Rome IV criteria; macrogol vs lactulose (Cochrane 2010, CD007570); fibre 77% vs 44% (Christodoulides 2016 APT). Fibre evidence is for fibre supplements, not dietary fibre from whole foods.

### Secondary source cited instead of primary — April 2026
Step 3 of pre-draft verification requires confirming the specific stat is in the specific paper — not just a plausible paper by the same author.

### Lay-clarification rule broadened — April 2026
Every medical term a lay reader would not immediately understand requires a definition in brackets on first use in each section.

### Safety-critical terms need inline lay definitions — April 2026
Inline lay definition in same sentence, not just a Key Terms entry.

### NICE guideline number verification — CG vs NG — LOCKED APRIL 2026
Always verify via web search in the same session. migraine.html delivered citing NICE NG150 (incorrect) instead of NICE CG150 (correct) April 2026.

### Visuals must maximise viewport space — LOCKED APRIL 2026
Slide padding max `1rem 1.5rem 0.8rem`; body text min `.90rem`; gaps max `.5rem`; slide title min `1.55rem`. Content must fill at least 85%.

### ev-stat-box text overflow — confirmed fix April 2026
`padding:.9rem .75rem` + `overflow:hidden`; `.ev-conditions` `font-size:.78rem; line-height:1.32`.

### Research card stat boxes must state complete clinical conclusions — LOCKED APRIL 2026
The test: read the stat box alone — does a lay reader understand what the research found? If not, rewrite. Never lead with ORs, RCT counts, participant counts, or cost figures.

### PMIDs must be verified by web search every time — LOCKED APRIL 2026
In April 2026, PMID 25088348 included for Thurman et al Epilepsia 2014 — correct PMID is 24903551. Mandatory process: search → find PubMed URL → use that PMID only. Never from memory.

### Charity and advocacy websites are not approved sources — LOCKED APRIL 2026
Epilepsy Action, Alzheimer's Society, WCRF, Breast Cancer Now not approved. Derived statistics not acceptable.

### Causal attributions require primary citations — April 2026
Causal claims require a specific primary citation. Inference not sufficient.

### NEAD — use neutral language — April 2026
Use neutral language: "episodes that resemble seizures but are not caused by abnormal electrical activity in the brain."

### Exact figure rule — never convert between numerical forms — LOCKED APRIL 2026
Kwan & Brodie reports "more than 30 percent" — not "1 in 3" or "33%". Always cite the paper's exact expression.

### Stat grid cards require inline citations — LOCKED APRIL 2026
Breast cancer (Article 27) — 3 of 4 stat grid cards delivered without citations. Caught by Dr Paul. The grep check is mandatory before delivery.

### Approved source retrieval — fetch from the approved source page directly — LOCKED APRIL 2026
breast-cancer (Article 27): 60,763 taken from WCRF page, incorrectly attributed to CRUK. CRUK page states "around 59,000." Always fetch the approved source directly.

### Cancer Series colour changed from rose to forest green — April 2026
Initial `#8A3A5A` rejected — contrast issues. Changed to `#2A5A3A` (forest green). Dark variant `#1A3A25`.

### Research card stat boxes use series colour, not navy — LOCKED APRIL 2026
ev-stat-box: series-colour gradient (series-dark to series), never plain navy.

### Never rebuild a project knowledge document from scratch — LOCKED APRIL 2026
Always use the existing document as the base. Rebuilding from memory loses content and introduces errors.

### Closing slide must be brand close, not stat repeat — LOCKED APRIL 2026
Last slide: logo · tagline · brand headline · three pitch cards · med-disclaimer · series label. NOT a repeat of research stats.

### Closing slide must use `justify-content: flex-start` — LOCKED APRIL 2026
`center` clips the logo. `flex-start` anchors visibly.

### CTA slide must use `cta-wrap-v2` with `grid-template-rows: auto 1fr auto` — LOCKED APRIL 2026
Only correct CTA layout. `justify-content: center` or `space-between` clip content.

### 6-card slides must be split to 3+3 — LOCKED APRIL 2026
Never reduce font size or line clamp to make 6 cards fit.

### prostate-cancer-visuals.html is canonical visuals reference — LOCKED APRIL 2026
Replaces `lifestyle-changes-visuals.html` as primary canonical reference.

### All stats require citations in every location — LOCKED APRIL 2026
If it's a number anywhere in the file, it needs a citation.

### Subtypes and formally named sets must be listed — LOCKED APRIL 2026
`<ol class="subtype-list">` for any formally introduced set. Canonical: `lung-cancer.html` (Article 29, April 2026).

### The reason for the stat must be in ev-outcome, not ev-conditions — LOCKED APRIL 2026
ev-outcome (0.95rem weight 700) carries the reason. ev-conditions (0.78rem) handles trial name and population only.

### ev-stage must use display:flex, never display:grid — LOCKED APRIL 2026
Canonical failure: `stress-visuals.html` slide 7. Flex distributes evenly; grid clips.

### close-logo `.dot` CSS bug — LOCKED APRIL 2026
Use `<span class="cl-dot">` not `<span class="dot">`. Nav dot CSS makes `.dot` tiny and invisible.

### disc footer visibility — LOCKED APRIL 2026
`.disc` must use `color:rgba(255,255,255,.65)` and `font-size:clamp(.65rem,1vw,.80rem)`.

### 5-card grids split to 3+2 — confirmed pattern April 2026
CSS pattern: `.sys-grid-2`, `.doc-grid-2`, `.mech-grid-2` with `grid-template-rows:repeat(2,1fr)`.

### Drug class descriptions for teleprompter — Digestive Series — April 2026
- amitriptyline → "low-dose gut-brain modulator"
- loperamide → "gut-slowing agent"
- rifaximin → "gut-targeted antibiotic"
- omeprazole/lansoprazole/esomeprazole → "proton pump inhibitor — a PPI"
- famotidine → "H2 receptor antagonist — a second type of acid-reducer"

### 4-card slides must split — "fragile" is not a QC pass — LOCKED APRIL 2026
Any slide with 4 or more cards must split to ≤3 per slide. Confirmed April 2026 after ibd-visuals.html 4-card treatment ladder clipped on filming viewport. Correction: split to 2+2. QC item 38.

### Gallstones and diverticular-disease were pre-canonical architecture — full rebuild required — April 2026
Both used: `position:absolute; inset:0`, no nav dots, side-by-side ev-cards (`1fr 1fr`), quote-card close, missing `-webkit-box`. Cannot be patched — full structural rebuild required. When any visuals file of this vintage is opened, expect full rebuild. Canonical: `prostate-cancer-visuals.html`.

### Project knowledge update protocol — LOCKED APRIL 2026
1. `web_fetch` live GitHub version
2. Write exact fetched content to `/home/claude/helf-school-project-knowledge.md`
3. `str_replace` only new session content
4. `wc -l` confirm new ≥ original
5. Deliver for download + upload to GitHub and Claude Project

---

## 19. OUTSTANDING TASKS (April 2026)

### Completed ✅
- Cancer Series visuals + teleprompters (27–31): all complete ✅
- Cardiovascular Series visuals + teleprompters (01–07): all complete ✅
- Practical Health Series visuals + teleprompters (08–12): all complete ✅
- Digestive Series — ALL COMPLETE ✅:
  - acid-reflux (13) ✅ · bloating (15) ✅ · ibs (16) ✅
  - ibd (14) ✅ full rebuild April 2026
  - coeliac (18) ✅ full rebuild April 2026
  - gallstones (19) ✅ full structural rebuild April 2026
  - diverticular-disease (20) ✅ full structural rebuild April 2026
  - **masld (17) ✅ retrofit complete April 2026**
  - **constipation (21) ✅ retrofit complete April 2026**

### Next priority — Neurological Series (Articles 22–26)
Same retrofit checklist as Digestive Series above.

### Practical Health Series extension
- Article 32: Breast Awareness
- Article 33: Testicular Awareness

### Verification outstanding
- `hypertension.html` references 5 & 6 — Cochrane PubMed IDs ⚑ unverified
- `helf-school-conditions.html` — hero stat needs updating to 31 articles live

### Retrofit backlog (apply when files next opened)
0. **LAY IMPACT FIRST** — colour narrative, remove drug names, three-question structure
1. **DRUG BRAND NAMES** — all generics need brand names alongside
2. **Research card colour** — ev-stat-box: navy → series-colour gradient
3. **Closing slide brand close** — stat-recap → brand close
4. **Research card display standard** — ev-stat-row to 3.2rem weight 900
5. **Disclaimer sizes** — med-disc-text 1rem on both CTA and closing slides
6. **Research card clinical conclusion standard** — 01–23
7. **Stat grid citations** — 01–11
8. **Subtype list formatting** — `<ol class="subtype-list">` where applicable

**TELEPROMPTER CONSISTENCY RULE — LOCKED APRIL 2026:** Whenever a visuals file is updated, the matching teleprompter must be reviewed slide-by-slide before either file is uploaded.

---

## 20. CONSTIPATION ARTICLE — VERIFIED REFERENCES (April 2026)

| Ref | Citation | DOI / URL | Used for |
|-----|----------|-----------|----------|
| 1 | NICE CKS Constipation (adults). Last revised 2023 | cks.nice.org.uk/constipation | Definition (Rome IV), red flags, laxative stepwise |
| 2 | Dowden A. Prescriber 2021 + BJHA 2025 | wchh.onlinelibrary.wiley.com/doi/10.1002/psb.1954 | NHS burden: ~83,000 admissions/yr; 18.6m prescriptions; ~£113m cost |
| 3 | Lee-Robichaud H et al. Cochrane 2010;(7):CD007570. PMID 20614462 | doi.org/10.1002/14651858.CD007570.pub2 | Macrogol superior to lactulose (10 RCTs, 868 participants) |
| 4 | Christodoulides S et al. APT 2016;44(2):103–116. PMID 27170558 | doi.org/10.1111/apt.13662 | Fibre: 77% response vs 44% placebo |
| 5 | NHS Inform. Constipation | nhsinform.scot/illnesses-and-conditions/stomach-liver-and-gastrointestinal-tract/constipation | Prevalence: 1 in 7 adults UK; women twice as often as men |

---

## 21. CLAUDE PROJECT FILE NOTES

The Claude project holds **visuals, teleprompter, and screen files only**. Article HTML files live on GitHub only. Exception: `mediterranean-diet.html` kept as canonical article template.

### Canonical reference files
| File | Purpose |
|------|---------|
| `mediterranean-diet.html` | Canonical article HTML template |
| `lifestyle-changes-teleprompter.html` | Canonical teleprompter (cue box standard) |
| `prostate-cancer-visuals.html` | **PRIMARY canonical visuals reference** |
| `lifestyle-changes-visuals.html` | Secondary visuals reference — 6-row grid pattern |
| `memory-dementia.html` | Canonical article research card layout (220px column) |
| `breast-cancer.html` | Canonical article research card display (3.2rem stat, series gradient) |
| `prostate-cancer.html` | Cancer Series article canonical — reference numbering via CSS counter |
| `lung-cancer.html` | Canonical: myth-busting panel; `<ol class="subtype-list">` pattern |

### Files confirmed in Claude project (April 2026)
**Teleprompters:** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd · ibs · bloating · coeliac · masld · acid-reflux · constipation · migraine · headaches · dizziness-vertigo · memory-dementia · epilepsy · prostate-cancer

**Visuals:** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd (screen) · ibs · bloating · coeliac · masld · acid-reflux · constipation · migraine · headaches · dizziness-vertigo · memory-dementia · epilepsy · prostate-cancer

**Screen files:** Ar_barretts-screen · Ar_sphincter-screen · ibd-gut-screen · bloating-gut-screen · bloating-fodmap-screen

---

## 22. SESSION START RULES (content of helf-school-session-start-rules.md)

### Rule 1 — Read before acting
Read both documents in full before any output. No exceptions.

### Rule 2 — Article inventory is the source of truth
Section 3 is authoritative. Do not infer status from file sizes or project file listings.

### Rule 3 — 5,140-byte files are NOT corrupted
Edge incognito loader stubs. Never flag as corrupted.

### Rule 4 — Never produce output before confirming understanding
Before building any file: (1) which file, (2) current status per inventory, (3) canonical reference checked.

### Rule 5 — Educational voice check on every file

### Rule 6 — Cross-check article ↔ teleprompter before delivery

### Rule 6A — Project knowledge always overrides session-start-rules on status

### Rule 7 — One large file per turn

### Rule 8 — Verify references before building
Run web searches to verify all planned citations. Fetch figures directly from approved source page.

### Rule 9 — Update project knowledge at session end
Upload to both GitHub AND the Claude Project.

### Rule 10 — NICE CG99 is children only

### Rule 11 — Research card complete clinical conclusion

### Rule 12 — Visuals must maximise viewport space
Body text minimum `.90rem`. Content must fill at least 85%.

### Rule 13 — PMIDs must be verified by web search every time

### Rule 14 — Strict source rule
Only approved sources. Derived statistics not acceptable.

### Rule 15 — Exact figure rule — LOCKED APRIL 2026
Use paper's exact numerical expression everywhere.

### Rule 16 — Stat grid citation rule — LOCKED APRIL 2026
Every `.stat-prose` line must carry a superscript citation.

### Rule 17 — Approved source retrieval rule — LOCKED APRIL 2026
Every figure must be retrieved directly from the approved source page.

### Rule 18 — Never rebuild the project knowledge document from scratch — LOCKED APRIL 2026

### Rule 19 — Cancer Series: three elements use series green, not navy — LOCKED APRIL 2026
Key Terms box · Putting it all together box · Research card stat box all use series gradient.

### Rule 20 — Closing slide: brand close, `justify-content: flex-start` — LOCKED APRIL 2026

### Rule 21 — CTA slide: `cta-wrap-v2` with `grid-template-rows: auto 1fr auto` — LOCKED APRIL 2026

### Rule 22 — 3-card rule: never 6 cards on one slide — LOCKED APRIL 2026

### Rule 23 — Dark variants confirmed: retrofit unblocked — April 2026

### Rule 24 — All stats require citations in every location — LOCKED APRIL 2026

### Rule 25 — Subtypes and formally named sets must be listed — LOCKED APRIL 2026
`<ol class="subtype-list">` — never inline comma-separated prose.

### Rule 26 — prostate-cancer-visuals.html is canonical visuals reference — LOCKED APRIL 2026

### Rule 27 — All stats require citations in every location — LOCKED APRIL 2026

### Rule 28 — Subtypes in lists only — LOCKED APRIL 2026

### Rule 29 — ev-outcome must carry the reason — LOCKED APRIL 2026

### Rule 30 — Visuals research card body = 2–3 sentences maximum — LOCKED APRIL 2026

### Rule 31 — CTA slide = health-action one thing — LOCKED APRIL 2026

### Rule 32 — Research currency: no articles older than 12 years — LOCKED APRIL 2026

### Rule 33 — Drug brand names alongside all generics — LOCKED APRIL 2026
Articles/visuals: `pembrolizumab (Keytruda)`. Teleprompter: class description approach.

### Rule 34 — Lay impact first: visuals and teleprompter — LOCKED APRIL 2026
Colour narrative mandatory. No drug names in visuals/teleprompter.

### Rule 35 — Series background colour: never near-black — LOCKED APRIL 2026
Cancer `#0e2418` · Cardiovascular `#1a0808` · Neurological `#0f0d1a` · Digestive `#1a0e08` · Fatigue `#081a14` · Practical `#120e08`

### Rule 36 — EV-card two-card height constraint — LOCKED APRIL 2026
Two stacked ev-cards: ev-body ≤ 30 words. Single ev-card: ev-body ≤ 44 words.

### Rule 37 — ev-stage MUST USE display:flex — NEVER display:grid — LOCKED APRIL 2026
Canonical failure: `stress-visuals.html` slide 7 (April 2026).

### Rule 38 — 4-card slides must split — LOCKED APRIL 2026
**Any slide with 4 or more cards must split to ≤3 cards per slide.** The QC label "⚠ 4-card (fragile)" is not a pass — it is a mandatory split. Confirmed April 2026 after ibd-visuals.html 4-card treatment ladder clipped on filming viewport.

---

## CONFIRMED FILE STATUS — UPDATED APRIL 2026

**AUTHORITY NOTE: If any entry below conflicts with Section 3, Section 3 is correct.**

### Cardiovascular Series (01–07) — ALL COMPLETE ✅

| File | Status |
|------|--------|
| hypertension.html + visuals + teleprompter | ✅ Confirmed correct (refs 5+6 ⚑ pending verification) |
| cholesterol.html + visuals + teleprompter | ✅ Confirmed correct |
| heart-attack-risk.html + visuals + teleprompter | ✅ Confirmed correct |
| statins.html + visuals + teleprompter | ✅ Confirmed correct |
| lifestyle-changes.html + visuals + teleprompter | ✅ Confirmed correct — CANONICAL REFERENCE |
| salt-blood-pressure.html + visuals + teleprompter | ✅ Confirmed correct |
| supplements-cholesterol.html + visuals + teleprompter | ✅ Confirmed correct |

### Practical Health Series (08–12) — COMPLETE ✅

| File | Status |
|------|--------|
| mediterranean-diet.html + visuals + teleprompter | ✅ All confirmed correct |
| sleep.html + visuals + teleprompter | ✅ All confirmed correct |
| exercise.html + visuals + teleprompter | ✅ All confirmed correct |
| stress.html + visuals + teleprompter | ✅ All confirmed correct |
| alcohol.html + visuals + teleprompter | ✅ All confirmed correct |

### Digestive Health Series (13–21) — ALL COMPLETE ✅

| File | Status |
|------|--------|
| acid-reflux + visuals + teleprompter | ✅ On GitHub · retrofitted April 2026 |
| ibd + visuals + teleprompter | ✅ On GitHub · full rebuild April 2026 |
| bloating + visuals + teleprompter | ✅ On GitHub · retrofitted April 2026 |
| ibs + visuals + teleprompter | ✅ On GitHub · retrofitted April 2026 |
| masld + visuals + teleprompter | ✅ On GitHub · **retrofit complete April 2026** |
| coeliac + visuals + teleprompter | ✅ On GitHub · full rebuild April 2026 |
| gallstones + visuals + teleprompter | ✅ On GitHub · full structural rebuild April 2026 |
| diverticular-disease + visuals + teleprompter | ✅ On GitHub · full structural rebuild April 2026 |
| constipation + visuals + teleprompter | ✅ Built April 2026 · **retrofit complete April 2026** |

### Neurological Series (22–26) — ALL BUILT ✅

| File | Status |
|------|--------|
| migraine + visuals + teleprompter | ✅ Built April 2026 — on GitHub |
| headaches + visuals + teleprompter | ✅ Built April 2026 — on GitHub |
| dizziness-vertigo + visuals + teleprompter | ✅ Built April 2026 — on GitHub |
| memory-dementia + visuals + teleprompter | ✅ Built April 2026 — on GitHub |
| epilepsy + visuals + teleprompter | ✅ Built April 2026 — on GitHub |

### Cancer Series (27–31) — ALL COMPLETE ✅

| File | Status |
|------|--------|
| breast-cancer + visuals + teleprompter | ✅ All 3 files built + retrofitted April 2026 |
| prostate-cancer + visuals + teleprompter | ✅ All 3 files built + retrofitted April 2026 — PRIMARY CANONICAL REFERENCE |
| lung-cancer + visuals + teleprompter | ✅ All 3 files built + retrofitted April 2026 |
| bowel-cancer + visuals + teleprompter | ✅ All 3 files built + retrofitted April 2026 — FIRST ZERO-CHANGE DELIVERY |
| melanoma + visuals + teleprompter | ✅ All 3 files built + retrofitted April 2026 |

### OUTSTANDING CITATION FLAGS
- hypertension.html refs 5 + 6 — Cochrane PubMed IDs flagged ⚑ unverified

---

## 23. ARTICLE-SPECIFIC NOTES — KNOWN ISSUES

### hypertension.html
References 5 and 6 — Cochrane PubMed IDs flagged ⚑ unverified.

### statins.html
Very large HTML file — has caused mid-build crashes. Handle in one dedicated turn.

### conditions page (helf-school-conditions.html)
Hero stat: 28 articles live now. Needs updating to 31 when all series complete.

### epilepsy.html — April 2026 decisions
NICE NG217 (April 2022, updated January 2025). Kwan & Brodie NEJM 2000: "more than 30 percent" not "1 in 3". SUDEP stat: ~1 in 1,000 per year (Thurman et al Epilepsia 2014, PMID 24903551). Misdiagnosis rate: 26.1% (Smith, Defalla & Chadwick QJM 1999, PMID 10209668). NEAD neutral language. Valproate teratogenicity inline definition present.

### breast-cancer.html — April 2026 decisions
Incidence "around 59,000" (CRUK direct, not WCRF 60,763). Screening age 50–70. NICE NG101 + CG81. 3 research cards: Marmot 2012 (PMID 23117178); EBCTCG tamoxifen 2011 (PMID 21802721); EBCTCG aromatase inhibitors 2015 (PMID 26211827). All 4 stat grid cards carry inline citations ✅. Overdiagnosis: 129 per 10,000 framing. Forest green gradient stat box — canonical standard.

### prostate-cancer.html — April 2026 decisions
Incidence ~57,900 (CRUK). 10-year survival 78.9%. Deaths ~12,200. NICE NG131. 3 research cards: ProtecT (PMID 36912538); CAP trial (PMID 38581198); STAMPEDE (PMID 26719232). Visuals: 14 slides (3-card split) — canonical reference for all future visuals. Teleprompter: 9 segments, 10 cue boxes, 712 words.

### lung-cancer.html — April 2026 decisions
Myth-busting panel (2×2 dark navy grid). 3 research cards: NELSON (PMID 31995683); KEYNOTE-024 (PMID 27718847); FLAURA (PMID 31751012). NSCLC subtypes as `<ol class="subtype-list">` — first use of this pattern, canonical.

### ibd-visuals.html — April 2026 full rebuild
12-slide deck. Harm/doc 5-card grids split 3+2. Treatment ladder 4-card → 2+2 (Rule 38 — mandatory split). Drug names → class descriptions. Teleprompter updated to 12-slide deck.

### coeliac-visuals.html — April 2026 full rebuild
12-slide deck. 5-card doc-grid split 3+2. ev-stat-box → series gradient. ev-outcome carries reason. Sequential CTA. Brand close. Teleprompter updated.

### gallstones-visuals.html — April 2026 full structural rebuild
Pre-canonical architecture: `inset:0` slides, no nav dots, side-by-side ev-cards, quote-card close, 5 webkit-box omissions. Full structural rebuild — cannot be patched. 12-slide deck. Teleprompter: 8 segments, cue boxes updated.

### diverticular-disease-visuals.html — April 2026 full structural rebuild
Same pre-canonical architecture as gallstones. Full structural rebuild. 10-slide deck. Myth comparison (2-col) preserved. Risk/doc 5→3+2. Sequential CTA. Brand close. Teleprompter: 7 segments, cue boxes updated.

---

## 24. PLANNING NOTES — NEXT SERIES

### Neurological Series (Articles 22–26) — COMPLETE APRIL 2026
Series colour: `#6B5EA8` (purple). All 3 files on GitHub ✅.

### Practical Health Series extension — Articles 32–33 (planned April 2026)

**Article 32 — Breast Awareness**
Practical Health series · slug: `breast-awareness`. Short practical article — NOT cancer biology. NICE/CRUK moved away from monthly BSE towards breast awareness. Cross-referenced from `breast-cancer.html` Section 3 — "Coming soon."

**Article 33 — Testicular Awareness**
Practical Health series · slug: `testicular-awareness`. Aimed at young men (peak: 20s–30s). Testicular cancer is the most common cancer in men aged 15–49 in the UK.

### Cancer Series (Articles 27–31) — ALL COMPLETE ✅ April 2026

**Possible future series:**
- Stroke and TIA (bridges cardiovascular)
- Parkinson's Disease (rising incidence, ageing population)

---

## 25. PROCESS NOTES — FILE CREATION IN CLAUDE

### Writing large HTML files
Use `create_file` for all HTML files. Bash heredocs fail on large HTML content.

### File already exists error
Run `rm /home/claude/filename.html` then retry `create_file`.

### Outputs directory
All files for Dr Paul must be copied to `/mnt/user-data/outputs/` and presented via `present_files`.

### QC before presenting
Always run bash QC checks before copying to outputs. Deliver only after QC passes.

**Standard QC bash commands:**
```bash
# Check ev-body word counts
python3 -c "
import re, sys
c=open(sys.argv[1]).read()
bodies=re.findall(r'class=\"ev-body\">(.*?)</div>',c,re.DOTALL)
for i,b in enumerate(bodies):
    t=re.sub(r'<[^>]+>','',b).strip(); w=len(t.split())
    print(f'ev-body {i+1}: {w}w {chr(10003) if w<=30 else chr(10007)}')
" filename.html

# Check ev-stage uses flex not grid
grep "ev-stage" filename.html

# Check forbidden phrases
grep -i "speak to your GP\|you should\|seek help" filename.html
```

### Research card stat box — writing guidance
1. Identify the clinically important finding
2. State as complete subject + finding: "The Epley manoeuvre / is safe & effective for BPPV"
3. Check: can a lay reader understand this from the stat box alone?
4. Never lead with ORs, RCT counts, CIs, or participant counts

### PMID verification — mandatory process
1. Search by author, title, journal, year
2. Find PubMed URL in search results
3. PMID is the number in that URL
4. Only then include the PMID. Never from memory.

### Project knowledge update — mandatory process — LOCKED APRIL 2026
1. **`web_fetch` the live version from GitHub** — never rely on the project copy which may be stale. URL: `https://raw.githubusercontent.com/pls4286/helfschool/main/helf-school-project-knowledge.md`
2. Write the exact fetched content to `/home/claude/helf-school-project-knowledge.md` — use Python append operations or `create_file`
3. `str_replace` to add only the new session content — never rewrite from scratch
4. Run `wc -l` on the new file and confirm it is equal to or greater than the previous version
5. Verify all 25 sections are present by scanning for each section heading
6. Never deliver a shorter version without explicit explanation and Dr Paul's confirmation
7. Deliver for download and re-upload to both GitHub and the Claude Project

### Subtype list — canonical CSS pattern — LOCKED APRIL 2026
```css
.article-wrap ol.subtype-list { counter-reset: subtype-counter; list-style: none; padding-left: 0; display: flex; flex-direction: column; gap: .45rem; margin: .6rem 0 1rem 0; }
.article-wrap ol.subtype-list li { counter-increment: subtype-counter; display: flex; gap: .7rem; align-items: flex-start; font-size: 1rem; line-height: 1.72; color: var(--text); font-weight: 400; }
.article-wrap ol.subtype-list li::before { content: counter(subtype-counter); background: var(--series); color: #fff; font-size: .72rem; font-weight: 700; width: 1.45rem; height: 1.45rem; border-radius: 50%; display: flex; align-items: center; justify-content: center; flex-shrink: 0; margin-top: .22rem; }
```
HTML: `<ol class="subtype-list"><li><strong>Name</strong> — definition text.</li></ol>`

### Approved source figure retrieval — mandatory process — LOCKED APRIL 2026
1. Identify which approved source should hold the figure
2. Search for that approved source page specifically
3. Retrieve the figure from that page
4. Use only the figure stated on the approved source page
5. If an unapproved page attributes a figure to an approved source, do not use it — fetch the approved source directly

---

*End of document. Update at the end of every session. Download via Artifact panel. Upload to both GitHub (pls4286/helfschool/main) and the Claude Project to take effect in future sessions.*
---

## 17. RETROFIT STATUS (retroactive standards across existing articles)

### Confirmed complete
- Educational voice: confirmed complete across Articles 01–26 (as built)
- Article HTML retrofits (Articles 13–18): confirmed complete
- Visuals and teleprompters (Articles 13–18): confirmed built
- **Cancer Series visuals + teleprompters (Articles 27–31) — ALL COMPLETE April 2026 ✅**
  - breast-cancer-visuals + teleprompter ✅
  - prostate-cancer-visuals + teleprompter ✅
  - lung-cancer-visuals + teleprompter ✅
  - bowel-cancer-visuals + teleprompter ✅
  - melanoma-visuals + teleprompter ✅
- **Cardiovascular Series visuals + teleprompters (Articles 01–07) — ALL COMPLETE April 2026 ✅**
  - CTA sequential animation applied ✅
  - Brand close pitch cards applied ✅
  - `display:-webkit-box` fixed on all body elements ✅
  - 5-card and 6-card slides split to max 3 cards per slide ✅
  - ev-card padding reduced to 1.1rem, ev-body clamp:4 ✅
  - Teleprompter slide numbers updated to match ✅
- **Practical Health Series visuals + teleprompters (Articles 08–12) — ALL COMPLETE April 2026 ✅**
  - Articles 10 (exercise), 11 (stress), 12 (alcohol) completed this session ✅
  - ev-stage display:flex enforced (Rule 37) — stress-visuals slide 7 clipping resolved ✅
- **Digestive Series — ALL COMPLETE April 2026 ✅:**
  - ibd (14): visuals + teleprompter ✅ full retrofit April 2026 — 12-slide deck
  - coeliac (18): visuals + teleprompter ✅ full retrofit April 2026 — 12-slide deck
  - gallstones (19): visuals + teleprompter ✅ **full structural rebuild** April 2026 — 12-slide deck
  - diverticular-disease (20): visuals + teleprompter ✅ **full structural rebuild** April 2026 — 10-slide deck
  - **masld (17): ✅ retrofit complete April 2026**
  - **constipation (21): ✅ retrofit complete April 2026**

### Outstanding — to confirm and apply
- Research card stat standard (outcomes only, not counts): outstanding across 01–11
- **Research card complete clinical conclusion standard: outstanding across 01–23** — audit when next opened
- Inline citations (superscripts linking to refs): outstanding across 01–11
- **Stat grid citations: outstanding across all articles built before April 2026**
- CTA sequential animation: outstanding across Neurological series visuals
- **Closing slide brand close standard: outstanding across Neurological series 22–26**
- Visuals layout standard (3-card split, ev-stat-row): outstanding across 01–11
- Key terms / hero visibility standards: outstanding across 01–11
- Teleprompter cue box standard: confirm per-file which were built before standard was set
- **Subtype list formatting: outstanding across all articles**
- **`display:-webkit-box` + `clamp:4` audit: outstanding across Neurological visuals** — `.sys-body`, `.doc-body`, `.mech-body` must have `line-clamp:4` — NEVER `line-clamp:2`.
- **5/6-card grid split: outstanding across Neurological visuals**
- **ev-stage display:flex audit: outstanding across Neurological visuals**

---

## 18. KEY LEARNING POINTS (accumulated)

### NICE CG99 is for children only — never cite for adults
NICE CG99 covers constipation in **children and young people only**. Adult constipation: **NICE CKS** at `cks.nice.org.uk/constipation`.

### Dr Paul's experience is 20+ years, not 30+
All references must read "20+ years" or "over twenty years as an NHS GP".

### Local link testing — expected not to work
When Dr Paul opens a downloaded HTML file locally and clicks article links, they appear broken. Expected — links are relative and work on the live GitHub site.

### Dr Paul prefers Claude to handle all file edits
Never ask Dr Paul to make manual edits. Claude fetches, applies all changes, delivers the corrected file for download and re-upload.

### Conditions page — always rebuild, never patch
When helf-school-conditions.html needs significant changes, rebuild from scratch.

### Educational voice — systemic issue in older files
When fetching any older file for any purpose, audit for forbidden phrases and correct them as part of the work.

### Teleprompter cue box — advance THEN read
The cue box precedes the script for its segment. Label: `▶ ADVANCE NOW — then read`.

### Large file writing — use create_file not bash
For HTML files over ~400 lines, `create_file` is the correct tool.

### Constipation article — April 2026 research decisions
- NICE CG99 explicitly excluded (children only)
- Rome IV criteria used as the clinical framework
- Laxative stepwise shown as 4 numbered steps with all brand names included
- Toileting position (footstool) included — evidence-based, often overlooked practical point
- Research card 1: macrogol vs lactulose (Cochrane 2010, CD007570)
- Research card 2: fibre supplementation response rate 77% vs 44% (Christodoulides 2016)
- Important distinction: fibre evidence is for fibre supplements not dietary fibre from whole foods

### Secondary source cited instead of primary — April 2026
In headaches article, Reference 5 was a consensus document, not the actual case-control study.

### Lay-clarification rule broadened — April 2026
Every medical or clinical term a lay reader would not immediately understand requires a plain English definition in brackets on first use in each section.

### Safety-critical terms need inline lay definitions — April 2026
Inline lay definition in same sentence, not just a Key Terms entry.

### NICE guideline number verification — CG vs NG — LOCKED APRIL 2026
Always verify via web search in the same session. In April 2026, migraine.html delivered citing NICE NG150 (incorrect) instead of NICE CG150 (correct).

### Visuals must maximise viewport space — LOCKED APRIL 2026
Slide padding max `1rem 1.5rem 0.8rem`; body text min `.90rem`; gaps max `.5rem`; slide title min `1.55rem`. Test: content must fill at least 85%.

### ev-stat-box text overflow — confirmed fix April 2026
`.ev-stat-box` `padding:.9rem .75rem` + `overflow:hidden`; `.ev-conditions` `font-size:.78rem; line-height:1.32`.

### Research card stat boxes must state complete clinical conclusions — LOCKED APRIL 2026
The research section exists to tell readers what medicine has found — in terms they can understand. Every research card stat box must state the complete clinical finding as it is relevant to the patient. The test: read the stat box alone. Does a lay reader understand what the research found? If not, rewrite.

### PMIDs must be verified by web search every time — LOCKED APRIL 2026
Mandatory process: (1) search for the paper by author, title, journal, year; (2) find a PubMed URL in the search results; (3) the PMID is the number in that URL; (4) only then include the PMID in the file. Never from memory.

### Charity and advocacy websites are not approved sources — LOCKED APRIL 2026
Epilepsy Action, Alzheimer's Society, WCRF, Breast Cancer Now, and similar organisations are not in the approved source list. Derived statistics are also not acceptable.

### Causal attributions require primary citations — April 2026
Causal claims require a specific primary citation confirming that causal relationship. Inference from context is not sufficient.

### NEAD — use neutral language — April 2026
Non-epileptic attack disorder (NEAD) should not be described as "typically a manifestation of psychological distress." Use neutral language.

### Drug-resistant epilepsy — cite the paper's exact figure — April 2026
Kwan & Brodie NEJM 2000 reports "more than 30 percent" — not "1 in 3" or "33%".

### Exact figure rule — never convert between numerical forms — LOCKED APRIL 2026
When a paper reports a statistic, use its exact numerical expression everywhere.

### Stat grid cards require inline citations — LOCKED APRIL 2026
Every `.stat-prose` line in the Why does it matter? stat grid must carry a superscript inline citation. In the breast cancer article (Article 27), three of four stat grid cards were presented without citations. Caught by Dr Paul during review.

### Approved source retrieval — fetch from the approved source page directly — LOCKED APRIL 2026
A figure found on an unapproved page that attributes its data to an approved source must NOT be used. Fetch the approved source page directly. In the breast cancer article, 60,763 was taken from the WCRF page. The Cancer Research UK page directly states "around 59,000." Caught by Dr Paul.

### Cancer Series colour changed from rose to forest green — April 2026
Initial colour `#8A3A5A` (deep rose) was rejected — contrast issues. Changed to `#2A5A3A` (forest green) with dark variant `#1A3A25`.

### Research card stat boxes use series colour, not navy — LOCKED APRIL 2026
The ev-stat-box background must use the series colour gradient (series-dark to series), not plain navy.

### Article research card display standard confirmed — April 2026
ev-stat-row: 3.2rem weight 900. Canonical reference: `breast-cancer.html`.

### Series dark variants must be confirmed before retrofit — April 2026
All dark variants are now confirmed for all series (see Section 2). Research card colour retrofit is fully unblocked.

### Closing slide disclaimer must use .closing-disclaimer class at 1rem — LOCKED APRIL 2026
The closing slide disclaimer must use the `.closing-disclaimer` / `.closing-disclaimer-text` classes at `font-size:1rem`, not the `.cta-disclaimer` class at `.80rem`.

### Cancer Series — three elements use series green, not navy — LOCKED APRIL 2026
In Cancer Series articles, the Key Terms box, Putting it all together box, and research card stat boxes all use forest green gradient.

### CTA slide must not reference "free at helf.school" — LOCKED APRIL 2026
helf.school is a subscription service. Caught by Dr Paul reviewing breast-cancer-visuals.html in April 2026.

### CTA disclaimer text size locked at 1rem — LOCKED APRIL 2026
CTA slide disclaimer text must be `font-size:1rem`. Never `.80rem`.

### Cancer Series established — April 2026
Series E. Articles 27–31. Colour `#2A5A3A` (forest green). Dark variant `#1A3A25`.

### Never rebuild a project knowledge document from scratch — LOCKED APRIL 2026
Always use the existing document as the base and merge new content into it. Never rebuild from memory.

### Closing slide must be brand close, not stat repeat — LOCKED APRIL 2026
The last slide is the helf.school brand close: logo · tagline · brand headline · three pitch cards · med-disclaimer · series label. It is NOT a repeat of the research statistics.

### Closing slide must use `justify-content: flex-start` — LOCKED APRIL 2026
`flex-start` anchors the logo visibly. Canonical reference: `prostate-cancer-visuals.html` slide 14.

### CTA slide must use `cta-wrap-v2` with `grid-template-rows: auto 1fr auto` — LOCKED APRIL 2026
This is the only correct CTA layout. `justify-content: center` or `justify-content: space-between` both cause content to clip.

### 6-card slides must be split to 3+3 — LOCKED APRIL 2026
Always split to two slides of 3 cards each. Never reduce font size or line clamp to make 6 cards fit.

### Reference numbering must be visible — LOCKED APRIL 2026
Use CSS `counter-reset` and `counter-increment` on `.ref-block` with a `::before` pseudo-element.

### prostate-cancer-visuals.html is new canonical visuals reference — LOCKED APRIL 2026
Replaces `lifestyle-changes-visuals.html` as the primary canonical reference.

### All stats require citations in every location — LOCKED APRIL 2026
Every numerical figure requires an inline superscript citation regardless of location.

### Subtypes and formally named sets must be listed, not written in prose — LOCKED APRIL 2026
Use `<ol class="subtype-list">` for any set introduced with a counted phrase. Canonical: `lung-cancer.html`.

### The reason for the stat must be in ev-outcome, not ev-conditions — LOCKED APRIL 2026
The comparison that produced the stat must appear in the `ev-outcome` line (0.95rem weight 700), not relegated to `ev-conditions` (0.78rem).

### ev-stage must use display:flex, never display:grid — LOCKED APRIL 2026
`stress-visuals.html` middle card clipped because grid 1fr row was insufficient. Flex distributes evenly.

### close-logo `.dot` CSS bug — LOCKED APRIL 2026
Using `<span class="dot">.</span>` inside `.close-logo` applies navigation dot CSS, making it tiny and invisible. Always use `<span class="cl-dot">.</span>` with `.cl-dot{color:var(--coral)}`. Fixed in acid-reflux, bloating, and IBS visuals April 2026.

### disc footer visibility — LOCKED APRIL 2026
The `.disc` footer bar must use `color:rgba(255,255,255,.65)` and `font-size:clamp(.65rem,1vw,.80rem)`. Fixed in acid-reflux, bloating, IBS visuals April 2026.

### 5-card grids split to 3+2 — confirmed pattern April 2026
When a visuals slide has 5 cards, split to 3+2 across two slides. CSS pattern: `.sys-grid-2`, `.doc-grid-2`, `.mech-grid-2` with `grid-template-rows:repeat(2,1fr)`.

### Drug class descriptions for teleprompter — Digestive Series — April 2026
- amitriptyline → "low-dose gut-brain modulator"
- loperamide → "gut-slowing agent" or "bowel-slowing agent"
- rifaximin → "gut-targeted antibiotic"
- omeprazole/lansoprazole/esomeprazole → "proton pump inhibitor — a PPI"
- famotidine → "H2 receptor antagonist — a second type of acid-reducer"

### IBS teleprompter — non-sequential slide references — April 2026
The IBS teleprompter was written with mechanisms (old slide 9) discussed in seg-2 BEFORE the doctor segment (old slide 4). Cue boxes updated to reflect new slide numbering in the 14-slide deck.

### 4-card slides must split — "fragile" is NOT a passing QC result — LOCKED APRIL 2026
Any slide grid with 4 cards must be split to 2+2 across two slides. Discovered when ibd-visuals.html treatment ladder (4 cards) was confirmed clipping on Dr Paul's filming viewport. "Fragile" is a failure — not an acceptable QC pass. QC item 38 now enforces this.

### Pre-canonical architecture pattern — full structural rebuild required — LOCKED APRIL 2026
When any visuals file uses `position:absolute; inset:0`, has no nav dots (uses `.dot` not `.nav-dot`), uses side-by-side ev-cards (1fr 1fr), or has a quote-card closing — a full structural rebuild is required. Patching is not possible. Both `gallstones-visuals.html` and `diverticular-disease-visuals.html` were this vintage — both required full structural rebuild April 2026.

### Project knowledge update protocol — LOCKED APRIL 2026
Mandatory process at every session end:
1. `web_fetch` the live version from GitHub — never rely on the project copy which may be stale
2. Write the fetched content to `/home/claude/helf-school-project-knowledge.md` using `create_file` or Python append
3. `str_replace` to add only the new session content — never rewrite from scratch
4. `bash wc -l` to confirm new line count ≥ original
5. Deliver for download and re-upload to both GitHub and the Claude Project

---

## 19. OUTSTANDING TASKS (April 2026)

### Completed ✅
- Cancer Series visuals + teleprompters (27–31): all retrofitted ✅
- Cardiovascular Series visuals + teleprompters (01–07): all retrofitted ✅
- Practical Health Series visuals + teleprompters (08–12): all retrofitted ✅
  - Articles 10–12 (exercise, stress, alcohol) completed April 2026
  - New rule confirmed: ev-stage must use display:flex, never display:grid (Rule 37)
- **Digestive Series — ALL COMPLETE April 2026 ✅:**
  - acid-reflux (13) ✅ · bloating (15) ✅ · ibs (16) ✅
  - ibd (14) ✅ full retrofit April 2026 — 12-slide deck
  - coeliac (18) ✅ full retrofit April 2026 — 12-slide deck
  - gallstones (19) ✅ full structural rebuild April 2026 — 12-slide deck
  - diverticular-disease (20) ✅ full structural rebuild April 2026 — 10-slide deck
  - **masld (17) ✅ retrofit complete April 2026**
  - **constipation (21) ✅ retrofit complete April 2026**

### Next priority — Neurological Series (Articles 22–26)
Same retrofit checklist as Digestive Series above.

Each file needs:
1. CTA sequential animation (replace static cta-rows-v2)
2. Brand close pitch cards (replace stat-recap close)
3. `display:-webkit-box` on ALL body elements (sys-body/doc-body/mech-body) — AND set `line-clamp:4`
4. Split any 4+ card slides to max 3 cards per slide (4-card = mandatory split, not "fragile")
5. ev-card: reduce padding to 1.1rem, ev-body clamp:4 if two cards per slide
6. **ev-stage: confirm `display:flex` — fix if `display:grid` found**
7. Check for pre-canonical architecture (inset:0, no nav dots) — if found, full structural rebuild required

### Practical Health Series extension
- Article 32: Breast Awareness
- Article 33: Testicular Awareness

### Verification outstanding
- `hypertension.html` references 5 & 6 — Cochrane PubMed IDs flagged ⚑ unverified
- `helf-school-conditions.html` — hero stat needs updating to 31 articles live

### Retrofit backlog (apply when files next opened)
All dark variants confirmed April 2026 — retrofit is fully unblocked.

0. **LAY IMPACT FIRST RETROFIT — Rule 34 — LOCKED APRIL 2026** — When any visuals or teleprompter file is opened for any reason, apply: (a) colour narrative; (b) remove drug names; (c) trim teleprompter trial references; (d) consider sequential animation for formal lists. Priority: Cancer (27–30) and Cardiovascular (01–07).

**TELEPROMPTER CONSISTENCY RULE — LOCKED APRIL 2026:** Whenever a visuals file is updated for any reason, the matching teleprompter must be reviewed slide-by-slide before either file is uploaded.

1. **DRUG BRAND NAMES RETROFIT — Rule 33 — HIGHEST URGENCY — LOCKED APRIL 2026**

**Cardiovascular Series (Articles 01–05):**
- `hypertension.html` / visuals / teleprompter — ACE inhibitors: ramipril (Tritace/Altace), lisinopril (Zestril), perindopril (Coversyl) · ARBs: losartan (Cozaar), candesartan (Amias), valsartan (Diovan) · calcium channel blockers: amlodipine (Norvasc) · beta-blockers: bisoprolol (Cardicor), atenolol · thiazides: indapamide (Natrilix), bendroflumethiazide (Aprinox)
- `cholesterol.html` / visuals / teleprompter — statins: atorvastatin (Lipitor), rosuvastatin (Crestor), simvastatin (Zocor) · ezetimibe (Ezetrol) · PCSK9 inhibitors: evolocumab (Repatha), alirocumab (Praluent)
- `heart-attack-risk.html` / visuals / teleprompter — clopidogrel (Plavix), ticagrelor (Brilique), warfarin (Coumadin), rivaroxaban (Xarelto), apixaban (Eliquis), edoxaban (Lixiana), dabigatran (Pradaxa)

**Cancer Series (Articles 27–31):**
- `breast-cancer.html` / visuals / teleprompter — trastuzumab (Herceptin), pertuzumab (Perjeta), olaparib (Lynparza), tamoxifen (Nolvadex/Tamofen), palbociclib (Ibrance), ribociclib (Kisqali), abemaciclib (Verzenios), fulvestrant (Faslodex)
- `prostate-cancer.html` / visuals / teleprompter — enzalutamide (Xtandi), abiraterone (Zytiga), docetaxel (Taxotere), olaparib (Lynparza), cabazitaxel (Jevtana)
- `lung-cancer.html` / visuals / teleprompter — CHECK: erlotinib (Tarceva), gefitinib (Iressa), bevacizumab (Avastin), nivolumab (Opdivo), atezolizumab (Tecentriq)
- `bowel-cancer.html` / visuals / teleprompter — pembrolizumab (Keytruda) ✅, bevacizumab (Avastin) ✅, cetuximab (Erbitux) ✅, panitumumab (Vectibix) ✅

**Other series:** Grep pattern: `egrep -i "mab|tinib|ciclib|pril|sartan|statin|oxacin|vir|mycin" [filename]`

2. **Research card colour retrofit** — ev-stat-box background: navy → series-colour gradient.
3. **Closing slide brand close retrofit** — apply across all 26 visuals files.
4. **Key Terms + Putting it all together** — navy → series-colour gradient. Decision outstanding: extend to all series or Cancer-only?
5. **Research card display standard** — ev-stat-row to 3.2rem weight 900 across all articles.
6. **Closing/CTA disclaimer sizes** — `med-disc-text` 1rem per file.
7. **No "free at helf.school"** — grep CTA subline per visuals file.
8. **Research card clinical conclusion standard** — 01–23.
9. **Stat grid citations** — 01–11 only.
10. **Inline citations** — 01–11 only.
11. **CTA slide standard** — 01–11 only.
12. **Visuals layout standard** — 01–11 only.
13. **Subtype list formatting** — apply `<ol class="subtype-list">` to any article containing formally introduced sets.
