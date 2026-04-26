# helf.school — Project Knowledge
**Last updated: April 2026**

---

## ⚠️ DOCUMENT INTEGRITY — CLAUDE MUST READ THIS BEFORE ANY SESSION WORK

**This document has 25 numbered sections. Minimum expected line count: ~800 lines.**

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

8. **Stat grid citation audit — LOCKED APRIL 2026** — run `grep -A 3 "stat-prose"` before presenting any article and confirm every `.stat-prose` instance has a `ref-` link. Every stat grid card must carry a superscript inline citation. No exceptions.

**For every visuals file, additionally run:**

9. **ev-stat-box check** — `.ev-conditions` font is `.78rem`, padding is `.9rem .75rem`, `overflow:hidden` present. ev-conditions text is short enough to fit 220px column.

10. **animate-ready check** — all animated cards have `animate-ready` class. No hardcoded `opacity:0` on card elements.

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
Each series uses its own colour on research card stat box backgrounds (gradient from series-dark to series). Dark variants must be agreed before retrofitting existing articles. Currently confirmed:

| Series | Primary | Dark variant | Status |
|--------|---------|-------------|--------|
| Cardiovascular | `#C8423A` | `#8A2020` | Proposed — to confirm |
| Neurological | `#6B5EA8` | `#4A4080` | Proposed — to confirm |
| Digestive | `#D47C3A` | `#8A4A1A` | Proposed — to confirm |
| Fatigue | `#3A8A7A` | `#1A5A4A` | Proposed — to confirm |
| Medical Decision | `#2E6BA8` | `#1A3A6A` | Proposed — to confirm |
| Practical Health | `#7A6A2E` | `#4A3A1A` | Proposed — to confirm |
| Cancer | `#2A5A3A` | `#1A3A25` | ✅ Confirmed April 2026 |

**Outstanding: Dr Paul to confirm dark variants for all series before retrofit begins.**

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
Article 21: all three files confirmed on GitHub ✅

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
All five articles: all three files confirmed on GitHub ✅

| # | Title | Slug | Status |
|---|-------|------|--------|
| 22 | Migraine | migraine | All 3 files built April 2026 ✅ — on GitHub |
| 23 | Headaches — Types and Red Flags | headaches | All 3 files built April 2026 ✅ — on GitHub |
| 24 | Dizziness and Vertigo | dizziness-vertigo | All 3 files built April 2026 ✅ — on GitHub |
| 25 | Memory, Cognition and Dementia | memory-dementia | All 3 files built April 2026 ✅ — on GitHub |
| 26 | Epilepsy — What It Is and How It's Managed | epilepsy | All 3 files built April 2026 ✅ — on GitHub |

### Series E — Cancer (Articles 27–31) — ESTABLISHED APRIL 2026
Series colour: `#8A3A5A` (deep rose).

| # | Title | Slug | Status |
|---|-------|------|--------|
| 27 | Breast Cancer | breast-cancer | All 3 files built April 2026 ✅ — upload to GitHub outstanding |
| 28 | Prostate Cancer | prostate-cancer | Not yet built |
| 29 | Lung Cancer | lung-cancer | Not yet built |
| 30 | Bowel (Colorectal) Cancer | bowel-cancer | Not yet built |
| 31 | Melanoma and Skin Cancer | melanoma | Not yet built |

**Total articles with all 3 files on GitHub: 26. Article 27 article HTML built — upload to GitHub outstanding.**

---

## 4. SITE FILES — CURRENT STATUS

| File | Status | Notes |
|------|--------|-------|
| index.html | Rebuilt April 2026 | 20+ years corrected; voice fixed; 2026 |
| helf-school-conditions.html | Rebuilt April 2026 | Needs rebuilding — now 26 articles + Cancer series |
| helf-school-membership.html | On GitHub | Pricing: £0 / £6pm or £60pa / £150 lifetime |

### helf-school-conditions.html — needs full rebuild (April 2026)
Currently shows 20 live articles across 3 series. Needs full rebuild to show:
- All 26 articles live across 4 series (Cardiovascular, Practical Health, Digestive, Neurological)
- Cancer series shown as coming soon
- Filter chips updated to include all 4 live series
- Hero stats updated: 4 series · 26 articles live

### index.html — April 2026 corrections applied
1. Hero h1: "Understanding your heart" → "Understanding your health"
2. Hero subtitle: "cardiovascular health" → "your health"
3. Hero trust item: full canonical phrase
4. Disclaimer banner: full canonical phrase
5. Why helf.school pillar: **30+ years → 20+ years** (primary fix)
6. Footer disclaimer: full canonical phrase
7. Copyright © 2025 → © 2026
8. Disclaimer doc date: March 2025 → April 2026 · Version 1.0 → 1.1
9. Article template voice: full canonical phrase
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
3. Why does it matter? — stat grid + prose paragraphs
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
- Term labels: minimum 0.88rem, `font-weight:700`, accent colour (series accent)
- Definitions: minimum 0.92rem, `rgba(255,255,255,0.90)` — opacity 0.75 or 0.80 not permitted for definition text
- 1–2 boxes; alphabetical order within each box

### Inline citations
- Every stat or claim in prose carries a superscript number linking to anchored reference `id="ref-N"`
- Format: `<sup><a href="#ref-1">1</a></sup>`
- Superscript link colour matches the series accent colour
- **This rule applies to stat grid `.stat-prose` text as well as body prose — every stat in every stat grid card must carry a superscript citation. No exceptions. Confirmed and locked April 2026.**

### Article research card display standard — LOCKED APRIL 2026

**Canonical reference: `memory-dementia.html` (layout) + `breast-cancer.html` (colour principle)**

These values apply to article HTML files only. The visuals ev-stat-box has a separate locked specification in Section 9.

```css
/* Research card layout */
.research-card { grid-template-columns: 220px 1fr; border-radius: 10px; border: 1px solid rgba(series,0.18); }

/* Stat box — series colour gradient, NOT navy */
.ev-stat-box {
  background: linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%);
  padding: 1.1rem .9rem;
  justify-content: flex-start;
  overflow: hidden;
}
.ev-kf-label { font-size: .72rem; font-weight: 700; color: var(--amber); text-transform: uppercase; letter-spacing: .07em; }
.ev-stat-row { font-size: 3.2rem; font-weight: 900; color: #fff; line-height: 1.0; }
.ev-outcome { font-size: .95rem; font-weight: 700; color: rgba(255,255,255,0.95); line-height: 1.3; }
.ev-conditions { font-size: .80rem; line-height: 1.35; color: rgba(255,255,255,0.72); }

/* Body */
.ev-body { background: #fff; padding: 1.1rem 1.2rem; }
.ev-body p { font-size: .93rem; line-height: 1.72; }
.ev-source { font-size: .78rem; color: rgba(44,44,44,0.55); font-style: italic; }
```

**Key rules:**
- **Stat box background: series-colour gradient** — each series uses its own dark-to-mid gradient, never plain navy. The amber kf-label pops beautifully against any series colour.
- **ev-stat-row: 3.2rem weight 900** — the headline stat must dominate the stat box. This is health education — the finding must be unmissable.
- **ev-kf-label: always amber `#E8A84A`** — consistent accent across all series, regardless of series colour.
- **Column: 220px** — confirmed from memory-dementia canonical.
- These values apply to articles only. For visuals, see Section 9 locked spec.

**Why the stat number must be large:** The research section is where readers learn what medicine has found. The stat box is the headline — it must lead with the clinically important finding in a size and weight that commands attention. A 2.2rem number at 220px reads as a supporting detail, not a headline. 3.2rem reads as news.
Every `.stat-prose` line in the Why does it matter? stat grid must carry a superscript inline citation. Run `grep -A 3 "stat-prose"` before presenting any article and confirm every instance has a `ref-` link. Not optional, not limited to "the obvious stats." Every card, every time.

**Why this rule was added:** In the breast cancer article (Article 27, April 2026), three of four stat grid cards were delivered without citations. Caught by Dr Paul during review — not by the pre-output audit. Now explicit in the QC checklist.

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
- "20% reduction in breast cancer mortality / in women invited to screening"
- "~⅓ reduction in breast cancer mortality / throughout first 15 years in ER-positive disease"

**Incorrect examples — statistical machinery or incomplete findings:**
- "11" with label "RCTs — Epley effective"
- "OR 2.67"
- "Safe & effective" without stating WHAT is safe and effective
- "Moderate to strong evidence" without stating WHAT has that evidence level
- Participant counts, study counts, or cost figures as the headline stat

**Stat boxes show outcomes only — effect sizes, risk changes, response rates, or complete qualitative clinical conclusions. NEVER:**
- Participant counts ("868 participants", "2,441 participants")
- Study counts ("10 RCTs", "39 studies")
- Cost figures ("£113m", "£2.3bn")
- Incomplete qualifiers

**Good stat box examples:**
- `~30% CV event reduction` · `77% response vs 44% placebo` · `PEG superior across 4 outcomes` · `+12% / +30% mortality risk` · `The Epley manoeuvre / is safe & effective for BPPV` · `Vestibular rehabilitation / has moderate to strong evidence`

**Bad stat box examples:**
- `1.38M participants` · `87 RCTs` · `£168m NHS cost` · `11 RCTs` · `OR 2.67` · `Safe & effective` (without subject) · `Moderate to strong evidence` (without subject)

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
- trastuzumab (Herceptin)
- letrozole (Femara)
- anastrozole (Arimidex)
- exemestane (Aromasin)

### Lay-clarification brackets — ALL medical terminology
**The general rule:** Every medical or clinical term that a lay reader would not immediately understand must have a plain English definition in brackets on first use in each section. This applies to anatomical terms, physiological terms, symptom descriptors, drug class names, procedural terms, and diagnostic labels — not just statistical measures.

Examples of terms requiring lay clarification:
- Anatomical: periorbital (around the eye) · temporal (at the temple) · ipsilateral (same side) · bilateral (both sides)
- Symptoms: lacrimation (tearing) · rhinorrhoea (runny nose) · ptosis (drooping eyelid) · miosis (pupil constriction) · conjunctival redness (redness of the white of the eye)
- Clinical: teratogenic (capable of causing harm to a developing foetus) · hepatotoxic (toxic to the liver) · tachycardia (fast heart rate)
- Drug classes: tricyclic antidepressant · beta-blocker · prokinetic antiemetic · aromatase inhibitor · selective oestrogen receptor modulator

**Why this keeps failing:** Earlier versions of this rule listed only statistical terms. Any term not on the explicit list was not caught at QC. The rule is now general: if a lay reader might not know it, it needs a definition in brackets on first use.

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

**Why this rule exists:** Multiple visuals files were delivered in April 2026 with text too small and gaps too large, leaving slides that looked sparse and underused the screen. Dr Paul explicitly noted the content was too small and the space was not being used well. This is a fundamental presentation quality issue — visuals are for filming and presenting, and undersized content reads poorly on camera.

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

**The complete clinical conclusion rule applies equally to visuals ev-stat-boxes.** The stat box in every research card in every visuals file must state the complete clinical finding — not ORs, RCT counts, or incomplete qualifiers. The same test applies: can a lay reader understand the clinical finding from the stat box alone?

### CTA slide standard (all visuals files)
- Full-screen with radial gold-glow background + pulsing icon halo (3.2s drop-shadow)
- **Central icon: minimum `5.5rem`** — the icon must dominate the slide visually. Never `3.2rem` or smaller — it disappears on screen.
- **Fraunces headline: minimum `clamp(2.8rem, 5.5vw, 4.2rem)`** — this is the most important text on the slide. Never `clamp(2.2rem, 4.5vw, 3.2rem)` — too small.
- **No subline mentioning "free at helf.school"** — helf.school is a subscription service. The subline must not reference being free. Remove `.cta-sub` text entirely or use a non-pricing line. **LOCKED APRIL 2026.**
- 4 action cards (NOT chips) — emoji + Fraunces bold label, gradient + gold border
- **Card emoji icons: minimum `2.2rem`** — never `1.4rem`
- **Card title text: minimum `.96rem`** — never `.84rem`
- **"Start for free" card is permitted** — there is a genuine £0 Explorer tier. "Free to read — always" is NOT permitted — it implies all content is permanently free.
- **CTA disclaimer box — LOCKED APRIL 2026:**
  - `.cta-disclaimer`: `max-width:720px` · `border:1.5px solid rgba(255,255,255,0.35)` · `padding:1rem 1.3rem` · `background:rgba(255,255,255,0.05)`
  - Icon: `font-size:1.3rem`
  - Text: `font-size:1rem` · `color:rgba(255,255,255,0.90)` · `line-height:1.6`
  - Never `.80rem` for CTA disclaimer text — too small to read on screen
- Reference: `hypertension-visuals.html` · `breast-cancer-visuals.html` (Cancer Series canonical)

### Closing slide standard (all visuals files)
- **Logo text: minimum `2.8rem`** — never `2rem`. This is the final brand impression.
- **Tagline: minimum `1.05rem`** — never `.9rem`
- **Link/series label: minimum `1rem`** — never `.85rem`
- **Closing slide disclaimer — LOCKED APRIL 2026 — use `.closing-disclaimer` class, NOT `.cta-disclaimer`:**
  - `.closing-disclaimer`: `max-width:680px` · `border:1.5px solid rgba(255,255,255,0.40)` · `border-radius:10px` · `padding:1rem 1.3rem` · `background:rgba(255,255,255,0.05)`
  - Icon: `.closing-disclaimer-icon` at `font-size:1.4rem`
  - Text: `.closing-disclaimer-text` at `font-size:1rem` · `color:rgba(255,255,255,0.90)` · `line-height:1.6` · `font-weight:400`
  - Never use `.cta-disclaimer` class on closing slide — it uses `.80rem` text, which is too small
  - **Why this rule exists:** The closing slide disclaimer is the last thing the audience sees. It must be readable. Multiple files were delivered with `.80rem` disclaimer text on the closing slide — confirmed too small in April 2026.
- Background: gradient from series dark colour to `#0d0d1a`

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
- Camera-ready HTML files (e.g. `ar-sphincter-screen.html`): full-screen, responsive, auto-animate on load, bold for filming
- Presenter HTML: bold red `.diagram-cue` callout box shows filename to open on second screen facing camera
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
8. **Lay-clarification — ALL medical terminology in brackets on first use per section, not just statistical terms. Anatomical, physiological, symptom, drug class, and diagnostic terms all require plain English definitions. Statistical terms (HR, RR, OR, SMD, NNT, CI, PAR) are included in this rule.**
9. **Research card clinical conclusions — complete clinical conclusion test (LOCKED APRIL 2026):** Every research card stat box must state the complete clinical finding in patient-relevant terms. The stat box (label + stat row + outcome + conditions together) must answer: WHAT was studied, WHAT was found, and WHY it matters to someone with that condition. The test: can a lay reader understand the clinical finding from the stat box alone? Statistical machinery (OR values, RCT counts, confidence intervals) must never appear as the headline finding. Incomplete qualifiers ("Safe & effective" without subject; "Moderate to strong evidence" without subject) are not permitted.
10. Research card stats — outcomes only; never participant/study counts or cost figures as headline stat
11. CTA slide — disclaimer box present with full canonical phrase
12. Closing slide — same disclaimer box present
13. Copyright year — 2026
14. Body text weight — `font-weight:400` throughout (never 300 in body)
15. No `opacity:0` animations on article body sections — content immediately visible
16. **ev-stat-box — `.ev-conditions` font is `.78rem`, padding is `.9rem .75rem`, `overflow:hidden` present — check before delivery on every visuals file**
17. **NICE guideline numbers — verify CG vs NG via web search in the same session. Never cite from memory.**
18. **Safety-critical terms — any term like teratogenic, hepatotoxic, nephrotoxic must have an inline lay definition in the same sentence, not just a Key Terms entry**
19. **Structured lists and criteria boxes — any Key Terms box term appearing in a list or criteria box must have "(see Key Terms below)" added immediately after it**
20. **VIEWPORT MAXIMISATION — open every slide in a browser before delivering. Content must fill at least 85% of the visible area. Slide padding maximum `1rem 1.5rem 0.8rem`. Body text minimum `.90rem`. Card/row gaps maximum `.5rem`. Slide title minimum `1.55rem`. If slides look sparse or content is small, increase font sizes and reduce gaps before delivering.**
21. **PMID VERIFICATION — every PMID must be verified by web search in the same session. A PubMed URL must be found in search results confirming the PMID resolves to the correct paper. Never include a PMID from memory or inference.**
22. **STRICT SOURCE RULE — every stat, claim, and causal attribution must be traceable to an approved source. Charity and advocacy websites (Epilepsy Action, Alzheimer's Society, WCRF, etc.) are not approved. Derived figures (calculating deaths from a prevalence rate) are not acceptable — only cite figures explicitly stated in the approved source. If a stat cannot be traced, omit it.**
23. **EXACT FIGURE RULE — use the paper's exact numerical expression everywhere. Never convert between forms (">30%" must not become "1 in 3" or "33%"; "1 in 1,000" must not become "0.1%"). Cross-check stat grid, research cards, Key Terms, body prose, Putting It Together, and teleprompter for consistency before delivering any file.**
24. **STAT GRID CITATION RULE — LOCKED APRIL 2026:** Run `grep -A 3 "stat-prose"` before presenting any article. Every `.stat-prose` line must have a `ref-` superscript link. All stat grid cards. No exceptions. A stat grid card with no citation is a QC failure regardless of how obvious the stat appears.
25. **APPROVED SOURCE RETRIEVAL RULE — LOCKED APRIL 2026:** Every figure must be retrieved directly from the approved source page, not from a secondary or aggregator page that attributes the figure to an approved source. If a stat is found on an unapproved page (e.g. WCRF) that cites Cancer Research UK, fetch the Cancer Research UK page directly and use the figure stated there. Example of failure: breast cancer article (April 2026) used 60,763 (WCRF) instead of "around 59,000" (Cancer Research UK directly).
26. **CLOSING SLIDE DISCLAIMER SIZE — LOCKED APRIL 2026:** The closing slide must use the `.closing-disclaimer` class with `.closing-disclaimer-text` at `font-size:1rem`. Never use the `.cta-disclaimer` class on the closing slide — it uses `.80rem` text, which is too small. The disclaimer is the last thing the audience sees and must be clearly readable.
27. **CTA SLIDE DISCLAIMER SIZE — LOCKED APRIL 2026:** CTA disclaimer text must be `font-size:1rem`, `color:rgba(255,255,255,0.90)`. Never `.80rem`. Run a grep check on both disclaimer classes before presenting any visuals file.
28. **NO "FREE AT HELF.SCHOOL" ON VISUALS — LOCKED APRIL 2026:** The subline on the CTA slide must not reference being "free at helf.school" — helf.school is a subscription service and this is inaccurate. "Start for free" (the £0 Explorer tier) is permitted as a card label. "Free to read — always" is not permitted. "Evidence-based health education — free at helf.school" is not permitted. Check the CTA slide subline before presenting any visuals file.

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

BMJ · NICE guidelines · Cochrane Database · NEJM · The Lancet · JAMA · BMJ Best Practice · PubMed · NHS/NHS Digital · ONS · CDC · WHO · Global Burden of Disease Study · ESC/EAS guidelines · Alimentary Pharmacology & Therapeutics · European Heart Journal · QJM · Epilepsia · Seizure: European Journal of Epilepsy · JAMA Neurology

**Cancer Research UK — approved April 2026** for UK cancer incidence, mortality, survival, and risk statistics. Where Cancer Research UK cites a primary source (e.g. ONS data or a specific trial), cite the primary where practical. For Cancer Research UK's own published statistics, cite Cancer Research UK directly and fetch their statistics pages directly — never rely on a secondary page that attributes data to them.

No non-peer-reviewed sources, commercial health sites, or forum content permitted.

**NOT approved (explicit list):** Epilepsy Action · Alzheimer's Society · Alzheimer's Research UK · World Cancer Research Fund (WCRF) · Breast Cancer Now · any charity or advocacy website · any secondary source that cites a primary paper without being that primary paper.

**WCRF specifically:** The WCRF website publishes cancer statistics attributed to Cancer Research UK and NHS Digital. These must NOT be cited as Cancer Research UK figures. Always fetch the Cancer Research UK statistics page directly. Example of failure: breast cancer article (April 2026) used WCRF's 60,763 instead of Cancer Research UK's "around 59,000."

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
5. **PMID resolves to the correct paper — a PubMed URL must be found in search results confirming the PMID. Never include a PMID from memory or inference.**
6. **The figure comes directly from the approved source page, not from a secondary page attributing it to an approved source — LOCKED APRIL 2026**

**Step 3 is the step that fails most often.** Finding a paper by the same author on the same topic is not sufficient. The specific numerical claim must be traceable to that specific paper. If the stat appears in a secondary source (a review, a guidance document, an editorial) that itself cites a primary paper, cite the primary paper — not the secondary source.

**Step 5 is a new rule confirmed April 2026.** Claude has repeatedly generated plausible-sounding but incorrect PMIDs. Every PMID must be verified by web search before inclusion.

**Step 6 was added April 2026** after 60,763 (from WCRF) was used instead of "around 59,000" (from Cancer Research UK directly). Always search for and fetch the approved source page itself.

**Derived statistics are not acceptable.** If a source provides a prevalence rate but not an absolute count, do not calculate and cite an absolute figure. Only cite figures explicitly stated in the approved source.

Never include an unverified link. Never assume a study exists based on a plausible-sounding citation. Never cite NICE CG99 for adult constipation — it covers children and young people only. The correct adult reference is NICE CKS at `cks.nice.org.uk/constipation`.

**NICE guideline number rule:** Always verify the exact NICE guideline number — including whether it is CG or NG — via web search before citing. CG and NG are different series and different documents. Never cite a NICE guideline number from memory.

---

## 17. RETROFIT STATUS (retroactive standards across existing articles)

### Confirmed complete
- Educational voice: confirmed complete across Articles 01–26 (as built)
- Article HTML retrofits (Articles 13–18): confirmed complete
- Visuals and teleprompters (Articles 13–18): confirmed built

### Outstanding — to confirm and apply
- Research card stat standard (outcomes only, not counts): outstanding across 01–11
- **Research card complete clinical conclusion standard: outstanding across 01–23** — all previously built articles should have research card stat boxes audited against the complete clinical conclusion rule when they are next opened for any edit
- Inline citations (superscripts linking to refs): outstanding across 01–11
- **Stat grid citations: outstanding across all articles built before April 2026** — apply when next opened
- CTA slide high-impact standard (disclaimer box, gold-glow, 4 action cards): outstanding across 01–11
- Visuals layout standard (horizontal rows, ev-stat-row): outstanding across 01–11
- Key terms / hero visibility standards: outstanding across 01–11
- Teleprompter cue box standard: confirm per-file which were built before standard was set

---

## 18. KEY LEARNING POINTS (accumulated)

### NICE CG99 is for children only — never cite for adults
NICE CG99 covers constipation in **children and young people only**. For adult constipation the correct reference is **NICE CKS** at `cks.nice.org.uk/constipation`. Citing CG99 for an adult article is a meaningful clinical error.

### Dr Paul's experience is 20+ years, not 30+
All references to clinical experience must read "20+ years" or "over twenty years as an NHS GP". The incorrect "30+" was on the live index.html and was corrected April 2026.

### Local link testing — expected not to work
When Dr Paul opens a downloaded HTML file locally and clicks article links, they appear broken. This is expected and correct — links are correctly coded as relative and work on the live GitHub site.

### Dr Paul prefers Claude to handle all file edits
Never ask Dr Paul to make manual edits to files via the GitHub editor. When corrections are needed, Claude fetches the file, applies all changes, and delivers the corrected file for download and re-upload.

### Conditions page — always rebuild, never patch
When helf-school-conditions.html needs significant changes, rebuild from scratch. The old version had deeply structural problems. Partial patching would miss cascading issues.

### Educational voice — systemic issue in older files
index.html had directive language in three locations. When fetching any older file for any purpose, audit for forbidden phrases and correct them as part of the work.

### Teleprompter cue box — advance THEN read
The cue box precedes the script for its segment. Dr Paul advances the slide first, then reads the script — the viewer sees the slide before Dr Paul speaks. Cue box label: `▶ ADVANCE NOW — then read`.

### Large file writing — use create_file not bash
For HTML files over ~400 lines, `create_file` is the correct tool. Bash heredocs fail on large HTML because of shell character escaping.

### File already exists — delete and retry
If `create_file` reports "file already exists", delete the existing placeholder (`rm /home/claude/filename.html`) and retry.

### Constipation article — April 2026 research decisions
- NICE CG99 explicitly excluded (children only)
- Rome IV criteria used as the clinical framework
- Laxative stepwise shown as 4 numbered steps with all brand names included
- Toileting position (footstool) included — evidence-based, often overlooked practical point
- Research card 1: macrogol vs lactulose (Cochrane 2010, CD007570)
- Research card 2: fibre supplementation response rate 77% vs 44% (Christodoulides 2016)
- Important distinction: fibre evidence is for fibre supplements not dietary fibre from whole foods

### Secondary source cited instead of primary research paper — April 2026
In the headaches article (Article 23), Reference 5 was incorrectly cited as Kernick et al BJGP 2008;58(557):880 — a consensus imaging guidance document. The correct paper was Kernick et al BJGP 2007;57(542):695 — the actual case-control study. The error occurred because the pre-draft check confirmed the 2008 paper existed and was by the same author on the same topic — but did not verify that the specific stat was in that paper. **The rule strengthened as a result:** Step 3 of the pre-draft verification rule now explicitly requires confirming the specific stat is in the specific paper.

### Lay-clarification rule broadened — April 2026
The original lay-clarification rule listed only statistical terms. This caused anatomical and clinical terms to slip through QC in the headaches article. The rule has been broadened: **every medical or clinical term a lay reader would not immediately understand requires a plain English definition in brackets on first use in each section.** This is now a general rule, not a list of specific terms.

### Safety-critical terms need inline lay definitions — April 2026
Any clinical term that carries significant implications for the reader must have an inline lay definition in the same sentence, not just a Key Terms box entry. Confirmed when "teratogenic" appeared in the migraine article without a lay explanation.

### Structured lists — Key Terms terms need "(see Key Terms below)" — LOCKED APRIL 2026
When a medical term from the Key Terms box appears in a structured list or criteria box, add "(see Key Terms below)" immediately after the term.

### NICE guideline number verification — CG vs NG — LOCKED APRIL 2026
NICE uses two guideline series: **CG** (pre-~2014) and **NG** (from ~2014 onwards). These are entirely separate documents. In April 2026, migraine.html was delivered citing NICE NG150 (incorrect) instead of NICE CG150 (correct). Always verify via web search in the same session.

### Visuals must maximise viewport space — LOCKED APRIL 2026
Multiple visuals files were delivered with text too small and gaps too large. Dr Paul explicitly identified this as a problem. Fix: slide padding maximum `1rem 1.5rem 0.8rem`; body text minimum `.90rem`; gaps maximum `.5rem`; line clamp minimum 3 lines; slide title minimum `1.55rem`. Test: open every slide in a browser — content must fill at least 85%. See Section 9 and QC item 20.

### ev-stat-box text overflow — confirmed fix April 2026
The confirmed fix: `.ev-stat-box` `padding:.9rem .75rem` + `overflow:hidden`; `.ev-conditions` `font-size:.78rem; line-height:1.32`. Do not increase either value.

### session-start-rules.md status table conflict — April 2026
The session-start-rules.md file fell out of sync with project knowledge multiple times in April 2026. Fix applied: Rule 6A added — project knowledge always overrides session-start-rules on status.

### Research card stat boxes must state complete clinical conclusions — LOCKED APRIL 2026
**This is a health education site, not a statistics journal.** The research section exists to tell readers what medicine has found about their condition — in terms they can understand and use. Every research card stat box must state the complete clinical finding as it is relevant to the patient. The failure mode: stat boxes showing "11" (RCTs) and "OR 2.67" as the headline finding. These are statistical machinery — they tell the reader nothing. The test: read the stat box alone. Does a lay reader understand what the research found about their condition? If not, rewrite. See Section 8 and QC item 9.

### PMIDs must be verified by web search every time — LOCKED APRIL 2026
Claude has repeatedly generated plausible-sounding but incorrect PMIDs. In April 2026, PMID 25088348 was included for Thurman et al Epilepsia 2014 — the correct PMID is 24903551. Mandatory process: (1) search for the paper by author, title, journal, year; (2) find a PubMed URL in the search results; (3) the PMID is the number in that URL; (4) only then include the PMID in the file. Never include a PMID from memory. No exceptions.

### Charity and advocacy websites are not approved sources — LOCKED APRIL 2026
Epilepsy Action, Alzheimer's Society, Alzheimer's Research UK, WCRF, Breast Cancer Now, and similar organisations are not in the approved source list. Stats and claims derived from charity websites must not be included. Derived statistics are also not acceptable — only figures explicitly stated in an approved source may be cited. If a stat cannot be traced to an approved source, omit it.

### Causal attributions require primary citations — April 2026
Causal claims (e.g. "driven partly by disability discrimination") require a specific primary citation confirming that causal relationship. Inference from context is not sufficient. If the causal attribution cannot be cited, it must be removed.

### NEAD — use neutral language — April 2026
Non-epileptic attack disorder (NEAD) should not be described as "typically a manifestation of psychological distress." Use neutral language: "episodes that resemble seizures but are not caused by abnormal electrical activity in the brain."

### Drug-resistant epilepsy — cite the paper's exact figure — April 2026
Kwan & Brodie NEJM 2000 reports "more than 30 percent" — not "1 in 3" or "33%". Always cite the paper's exact language.

### Exact figure rule — never convert between numerical forms — LOCKED APRIL 2026
When a paper reports a statistic, use its exact numerical expression everywhere. Never convert between forms. Cross-check all instances before delivering any file.

### Stat grid cards require inline citations — LOCKED APRIL 2026
Every `.stat-prose` line in the Why does it matter? stat grid must carry a superscript inline citation. In the breast cancer article (Article 27, April 2026), three of four stat grid cards were presented without citations. Caught by Dr Paul during review — not by the pre-output audit. The QC checklist now includes an explicit grep check (item 24). Every card, every time, no exceptions.

### Approved source retrieval — fetch from the approved source page directly — LOCKED APRIL 2026
A figure found on an unapproved page (e.g. WCRF) that attributes its data to an approved source (e.g. Cancer Research UK) must NOT be used. Fetch the approved source page directly and use the figure stated there. In the breast cancer article (Article 27), 60,763 was taken from the WCRF page and incorrectly attributed to Cancer Research UK. The Cancer Research UK page directly states "around 59,000." Caught by Dr Paul. The correct process: search → find the approved source page → retrieve the figure from that page → use only that figure.

### Cancer Series colour changed from rose to forest green — April 2026
Initial colour `#8A3A5A` (deep rose) was proposed and approved but rendered poorly — the monochromatic dark rose/pink scheme gave insufficient contrast between card backgrounds and text. Changed to `#2A5A3A` (forest green) with dark variant `#1A3A25`. Forest green is distinct from existing teal `#3A8A7A` and olive `#7A6A2E`.

### Research card stat boxes use series colour, not navy — LOCKED APRIL 2026
The ev-stat-box background in article research cards must use the series colour gradient (series-dark to series), not plain navy. Established when building breast-cancer.html for the Cancer Series. The amber kf-label contrasts effectively against any series colour. This principle makes each series visually distinctive and reinforces series identity throughout the article. Each series needs a confirmed dark variant colour before this standard can be retrofitted. See Section 2 for the dark variant table.

### Article research card display standard confirmed — April 2026
The research card stat box in articles must be visually commanding. ev-stat-row: 3.2rem weight 900. The stat box is the headline — it must lead with the clinically important finding in a size that commands attention. Canonical reference: `breast-cancer.html`. See Section 8 for the full CSS specification.

### Series dark variants must be confirmed before retrofit — April 2026
The series-coloured stat box gradient requires a dark variant for each series. Proposed variants are in Section 2. Dr Paul must confirm each dark variant before the research card colour retrofit is applied to existing articles.
Cancer Research UK is approved for UK cancer incidence, mortality, survival, and risk statistics. Always fetch their statistics pages directly.

### Closing slide disclaimer must use .closing-disclaimer class at 1rem — LOCKED APRIL 2026
The closing slide disclaimer must use the `.closing-disclaimer` / `.closing-disclaimer-text` classes at `font-size:1rem`, not the `.cta-disclaimer` class at `.80rem`. The closing slide is the final thing the audience sees — it must be clearly readable on camera. Multiple files were delivered with the wrong class reused from the CTA slide. QC item 26 now checks this.

### CTA slide must not reference "free at helf.school" — LOCKED APRIL 2026
The subline on the CTA slide must not say "Evidence-based health education — free at helf.school" or any variation. helf.school is a subscription service. "Start for free" is permitted as a card label — there is a genuine £0 Explorer tier. "Free to read — always" is not permitted. This was caught by Dr Paul reviewing breast-cancer-visuals.html in April 2026. QC item 28 now checks this.

### CTA disclaimer text size locked at 1rem — LOCKED APRIL 2026
CTA slide disclaimer text must be `font-size:1rem`, `color:rgba(255,255,255,0.90)`. Never `.80rem` — too small to read on screen. QC item 27 enforces this.

### Cancer Series established — April 2026
Series E. Articles 27–31. Colour `#2A5A3A` (forest green, confirmed April 2026 — initial rose colour `#8A3A5A` rejected due to contrast issues). Dark variant `#1A3A25`.

### Never rebuild a project knowledge document from scratch — LOCKED APRIL 2026
When updating the project knowledge document, always use the existing document as the base and merge new content into it. Never rebuild from memory. The existing document is always larger and more complete than what Claude can reconstruct from memory in a session. Rebuilding from memory loses content and introduces errors. The correct process: read the existing document → identify what is new → add new content to the existing document → verify the new version is equal to or larger than the old one.

---

## 19. OUTSTANDING TASKS (April 2026)

### Immediate
- Upload `breast-cancer.html` and `breast-cancer-visuals.html` to GitHub
- Rebuild `helf-school-conditions.html` to show all 26 articles live + Cancer series coming soon
- **Agree dark variant colours for all 6 existing series** — required before research card colour retrofit. See Section 2 table for proposed values. Dr Paul to confirm each.

### Cancer Series — next articles to build
- Article 28: Prostate Cancer
- Article 29: Lung Cancer
- Article 30: Bowel (Colorectal) Cancer
- Article 31: Melanoma and Skin Cancer

### Verification
- `hypertension.html` references 5 & 6 — Cochrane PubMed IDs flagged ⚑ unverified

### Retrofit backlog (Articles 01–26 — apply when files next opened)
- **Research card colour retrofit** — ev-stat-box background to change from navy to series-colour gradient across all 26 articles. Requires dark variant confirmation first.
- **Research card display standard** — ev-stat-row to 3.2rem weight 900 across all articles.
- Research card clinical conclusion standard — apply across 01–23
- Research card stat standard (outcomes only, not counts) — 01–11
- Stat grid citations — all pre-April 2026 articles
- Inline citations (superscripts) — 01–11
- CTA slide standard — 01–11
- Visuals layout standard — 01–11
- Key terms / hero visibility standards — 01–11
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
| `memory-dementia.html` | Canonical article research card layout (220px column, flex-start) |
| `breast-cancer.html` | Canonical article research card display (3.2rem stat, series gradient background) |

### Files confirmed in Claude project (April 2026)
**Teleprompters (all series):** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd · ibs · bloating · coeliac · masld · acid-reflux · constipation · migraine · headaches · dizziness-vertigo · memory-dementia · epilepsy

**Visuals (all series):** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd (screen) · ibs · bloating · coeliac · masld · acid-reflux · constipation · migraine · headaches · dizziness-vertigo · memory-dementia · epilepsy

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
**If the file status table in session-start-rules.md conflicts with Section 3 of this document, this document (project knowledge) is correct.** Never flag work as outstanding based on session-start-rules.md alone.

### Rule 7 — One large file per turn
Build very large HTML files one per turn. Wait for confirmation before proceeding to the next file.

### Rule 8 — Verify references before building
Run web searches to verify all planned citations before building any article HTML. Fetch figures directly from the approved source page — not from a secondary page that attributes the figure to an approved source.

### Rule 9 — Update project knowledge at session end
Update this document and session-start-rules.md together. Dr Paul uploads both to GitHub AND the Claude Project.

### Rule 10 — NICE CG99 is children only
Never cite NICE CG99 in any adult article. Correct adult constipation reference: NICE CKS at cks.nice.org.uk/constipation.

### Rule 11 — Research card complete clinical conclusion
Before presenting any article or visuals file, audit every research card stat box against the complete clinical conclusion rule (Section 8, QC item 9). The stat box must state WHAT was studied and WHAT was found in patient-relevant terms. Statistical machinery (ORs, RCT counts, CIs) must never be the headline finding. The test: can a lay reader understand the clinical finding from the stat box alone?

### Rule 12 — Visuals must maximise viewport space
Every visuals slide must fill the available viewport. Slide padding maximum `1rem 1.5rem 0.8rem`. Body text minimum `.90rem`. Gaps maximum `.5rem`. Slide title minimum `1.55rem`. Open every slide in a browser before delivering — content must fill at least 85% of the visible area.

### Rule 13 — PMIDs must be verified by web search every time
Every PMID must be found in a web search result before inclusion. Mandatory process: (1) search for paper by author/title/journal/year; (2) find PubMed URL in results; (3) PMID is the number in that URL; (4) only then include it. Never from memory. No exceptions.

### Rule 14 — Strict source rule
Only approved sources (Section 14) may be cited. Charity/advocacy websites are not approved. WCRF is not approved even when it cites Cancer Research UK. Derived statistics are not acceptable. Causal attributions require a primary citation. If a stat cannot be traced to an approved source, omit it.

### Rule 15 — Exact figure rule — LOCKED APRIL 2026
Use the paper's exact numerical expression everywhere. Never convert between forms. Cross-check stat grid, research cards, Key Terms, body prose, Putting It Together, and teleprompter before delivering any file.

### Rule 16 — Stat grid citation rule — LOCKED APRIL 2026
Every `.stat-prose` line in the Why does it matter? stat grid must carry a superscript inline citation. Run `grep -A 3 "stat-prose"` before presenting any article and confirm every instance has a `ref-` link. All stat grid cards. No exceptions.

### Rule 17 — Approved source retrieval rule — LOCKED APRIL 2026
Every figure must be retrieved directly from the approved source page, not from a secondary or aggregator page. If a figure appears on WCRF or any other unapproved page attributed to Cancer Research UK, fetch the Cancer Research UK page and use the figure stated there.

### Rule 18 — Never rebuild the project knowledge document from scratch — LOCKED APRIL 2026
When updating the project knowledge document, always use the existing document as the base. Read it fully, identify what is new from the current session, and merge new content into it. Never rebuild from memory. A rebuilt-from-memory version will always be shorter and less complete than the existing document.

---

## 23. ARTICLE-SPECIFIC NOTES — KNOWN ISSUES

### hypertension.html
References 5 and 6 — Cochrane PubMed IDs flagged ⚑ unverified. These need verification via web search before the article can be confirmed fully complete.

### statins.html
Very large HTML file — has caused mid-build crashes in previous sessions. If this file needs to be rebuilt or significantly edited, handle it in one dedicated turn.

### conditions page (helf-school-conditions.html)
Needs full rebuild to show all 26 articles live plus Cancer series coming soon. Rebuild — do not patch.

### index.html
Rebuilt April 2026 with all 12 corrections listed in Section 4. "About Dr Paul" section correctly reads "NHS GP · 20+ years".

### dizziness-vertigo.html
Article HTML built April 2026. Research flags noted: NICE CKS Vertigo (last revised 2022 — check for updates); betahistine/Ménière's evidence contested (BEMED 2016 trial); 92-week UK delay figure cited via von Brevern 2007 rather than primary UK source.

### epilepsy.html — April 2026 decisions
- NICE NG217 (April 2022, updated January 2025) used as primary clinical reference
- Kwan & Brodie NEJM 2000: figure is "more than 30%" not "1 in 3" — all instances corrected
- SUDEP stat: ~1 in 1,000 per year (Thurman et al Epilepsia 2014, PMID 24903551) — no derived UK death count
- Misdiagnosis rate: 26.1% from Smith, Defalla & Chadwick QJM 1999 (PMID 10209668)
- NEAD described neutrally — not attributed to psychological distress
- Disability/unemployment paragraph removed — Epilepsy Action not an approved source
- Valproate: teratogenicity inline lay definition present; MHRA Valproate Pregnancy Prevention Programme referenced
- 6 references total; all PMIDs verified by web search in session

### breast-cancer.html — April 2026 decisions
- Cancer Series Article 27. Colour `#2A5A3A` (forest green, dark variant `#1A3A25`). Initial rose colour `#8A3A5A` rejected — contrast issues.
- Incidence: "around 59,000" — Cancer Research UK directly (NOT WCRF's 60,763)
- Male incidence: "around 420" — Cancer Research UK directly
- Screening age: 50 to 70 (Cancer Research UK) — not 50 to 71
- NICE NG101 (updated February 2025) and CG81
- 3 research cards: Marmot 2012 (PMID 23117178); EBCTCG tamoxifen 2011 (PMID 21802721); EBCTCG aromatase inhibitors 2015 (PMID 26211827)
- All 4 stat grid cards carry inline citations ✅
- Overdiagnosis: uses Marmot paper's per-10,000 framing (129 per 10,000) — not the derived 4,000 annual figure
- Research card stat box: forest green gradient, 3.2rem stat number — new canonical standard
- All 3 files built April 2026 ✅ — upload to GitHub outstanding
- Remaining research flags: triple-negative ~15%, HER2-positive ~15–20%, EBCTCG 2015 ~40% derivation

---

## 24. PLANNING NOTES — NEXT SERIES

### Neurological Series (Articles 22–26) — COMPLETE APRIL 2026
Series colour: `#6B5EA8` (purple)

### Cancer Series (Articles 27–31) — IN PROGRESS
Series colour: `#2A5A3A` (forest green). Dark variant: `#1A3A25`. Confirmed April 2026.

| # | Title | Slug | Status |
|---|-------|------|--------|
| 27 | Breast Cancer | breast-cancer | All 3 files built April 2026 ✅ — upload to GitHub outstanding |
| 28 | Prostate Cancer | prostate-cancer | Not yet built |
| 29 | Lung Cancer | lung-cancer | Not yet built |
| 30 | Bowel (Colorectal) Cancer | bowel-cancer | Not yet built |
| 31 | Melanoma and Skin Cancer | melanoma | Not yet built |

**Possible future series:**
- Stroke and TIA (bridges cardiovascular)
- Parkinson's Disease (rising incidence, ageing population)

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

### Research card stat box — writing guidance
When writing research card stat boxes, follow this sequence:
1. Identify the clinically important finding — what does this research tell someone with this condition?
2. State it as a complete subject + finding: "The Epley manoeuvre / is safe & effective for BPPV"
3. Check: can a lay reader understand this from the stat box alone?
4. Put supporting detail (effect sizes, study scale, comparator) in the body text and `.ev-conditions` line
5. Never lead with ORs, RCT counts, confidence intervals, or participant counts

### PMID verification — mandatory process
1. Search for the paper by author, title, journal, year
2. Find a PubMed URL in the search results
3. The PMID is the number in that URL
4. Only then include the PMID in the file
5. Never include a PMID from memory — it will be wrong

### Approved source figure retrieval — mandatory process — LOCKED APRIL 2026
1. Identify which approved source should hold the figure
2. Search for that approved source page specifically
3. Retrieve the figure from that page
4. Use only the figure stated on the approved source page
5. If an unapproved page (WCRF, charity site) quotes a figure and attributes it to an approved source, do not use the unapproved page's figure — fetch the approved source directly
6. If the approved source page gives a different figure (e.g. "around 59,000" vs WCRF's "60,763"), always use the approved source's figure

### Project knowledge update — mandatory process — LOCKED APRIL 2026
1. Read the existing project knowledge document in full before writing a single word of the update
2. Identify what is new from the current session only
3. Add new content to the existing document — do not rewrite or abbreviate existing sections
4. Run `wc -l` on the new file and confirm it is equal to or greater than the previous version
5. Verify all 25 sections are present
6. Never deliver a shorter version without explicit explanation and Dr Paul's confirmation

---

*End of document. Update at the end of every session. Download via Artifact panel. Upload to both GitHub (pls4286/helfschool/main) and the Claude Project to take effect in future sessions.*
