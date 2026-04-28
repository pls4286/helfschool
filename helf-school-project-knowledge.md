# helf.school — Project Knowledge
**Last updated: April 2026**

---

## ⚠️ DOCUMENT INTEGRITY — CLAUDE MUST READ THIS BEFORE ANY SESSION WORK

**This document has 25 numbered sections. Minimum expected line count: ~1300 lines.**

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
Each series uses its own colour on research card stat box backgrounds (gradient from series-dark to series). Dark variants must be agreed before retrofitting existing articles. Currently confirmed:

| Series | Primary | Dark variant | Status |
|--------|---------|-------------|--------|
| Cardiovascular | `#C8423A` | `#8A2020` | ✅ Confirmed April 2026 |
| Neurological | `#6B5EA8` | `#4A4080` | ✅ Confirmed April 2026 |
| Digestive | `#D47C3A` | `#8A4A1A` | ✅ Confirmed April 2026 |
| Fatigue | `#3A8A7A` | `#1A5A4A` | ✅ Confirmed April 2026 |
| Medical Decision | `#2E6BA8` | `#1A3A6A` | ✅ Confirmed April 2026 |
| Practical Health | `#7A6A2E` | `#4A3A1A` | ✅ Confirmed April 2026 |
| Cancer | `#2A5A3A` | `#1A3A25` | ✅ Confirmed April 2026 |

**All dark variants confirmed April 2026. Research card colour retrofit is now unblocked across all 26 articles.**

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

### Series B — Practical Health (Articles 08–12, extended to 32–33)
All three files confirmed complete and on GitHub for articles 08–12. Educational voice retrofit confirmed complete.
Articles 32–33 planned — extending the Practical Health series. Same series colour `#7A6A2E`.

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
Series colour: `#2A5A3A` (forest green). Dark variant: `#1A3A25`. **Note: initial proposed colour `#8A3A5A` (deep rose) was rejected — contrast issues. Forest green confirmed April 2026.**

| # | Title | Slug | Status |
|---|-------|------|--------|
| 27 | Breast Cancer | breast-cancer | All 3 files built April 2026 ✅ — upload to GitHub outstanding |
| 28 | Prostate Cancer | prostate-cancer | All 3 files built April 2026 ✅ — upload to GitHub outstanding |
| 29 | Lung Cancer | lung-cancer | Article HTML built April 2026 ✅ — visuals and teleprompter outstanding |
| 30 | Bowel (Colorectal) Cancer | bowel-cancer | Not yet built |
| 31 | Melanoma and Skin Cancer | melanoma | Not yet built |

**Total articles with article HTML on GitHub or built: 29. Articles 27, 28, 29 built — Articles 27 and 28 upload to GitHub outstanding. Article 29 visuals and teleprompter outstanding.**

---

## 4. SITE FILES — CURRENT STATUS

| File | Status | Notes |
|------|--------|-------|
| index.html | Rebuilt April 2026 | 20+ years corrected; voice fixed; 2026 |
| helf-school-conditions.html | Rebuilt April 2026 | Updated April 2026 — 28 articles live, Article 28 linked, Cancer series coming soon |
| helf-school-membership.html | On GitHub | Pricing: £0 / £6pm or £60pa / £150 lifetime |

### helf-school-conditions.html — April 2026 rebuild
Rebuilt April 2026 to show all 26 articles live across 4 series + Cancer series (Articles 27–28 live, 29–31 coming soon). Updated again April 2026 to mark Article 28 (Prostate Cancer) as live. Hero stat: 28 articles live now.

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
- **Visuals HTML:** `prostate-cancer-visuals.html` — **NEW PRIMARY CANONICAL REFERENCE confirmed April 2026.** Demonstrates: 3-card split slides, canonical `cta-wrap-v2` CTA (slide 13), brand close (slide 14), ev-card research cards with series gradient stat box. `lifestyle-changes-visuals.html` remains a secondary reference for the 6-row grid pattern.
- **Teleprompter HTML:** `lifestyle-changes-teleprompter.html` (canonical for cue box standard)
- **CTA slide:** `prostate-cancer-visuals.html` slide 13 — canonical `cta-wrap-v2` pattern
- **Closing slide:** `prostate-cancer-visuals.html` slide 14 — brand close standard

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
2. Key Terms box — navy background by default; **series-colour gradient for Cancer Series** — sits between sections 1 and 2
3. Why does it matter? — stat grid + prose paragraphs
4. What your doctor might discuss
5. What the research shows
6. "Putting it all together" — navy box by default; **series-colour gradient for Cancer Series** — italic text, bold closing line
7. References
8. Research flags ⚑ — for Dr Paul's review before upload

### Series-colour elements — Cancer Series rule — LOCKED APRIL 2026
In Cancer Series articles, three elements use `linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%)` instead of plain navy:
1. **Key Terms box** — `.key-terms { background: linear-gradient(...) }`
2. **Putting it all together box** — `.putting-together { background: linear-gradient(...) }`
3. **Research card stat box** — `.ev-stat-box { background: linear-gradient(...) }`

All three are confirmed in `breast-cancer.html` and `prostate-cancer.html` (April 2026). Apply to all future Cancer Series articles (29–31) from the start. Retrofit to other series when dark variant colours are confirmed (see Section 2 dark variants table).

### Key Terms box standards
- Default (all series): Navy background `#1B2A4A`
- **Cancer Series: `linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%)`** — forest green gradient, confirmed April 2026
- Title: Fraunces serif, minimum 1.05rem, `#fff`
- Term labels: minimum 0.88rem, `font-weight:700`, series-light accent colour
- Definitions: minimum 0.92rem, `rgba(255,255,255,0.90)` — opacity 0.75 or 0.80 not permitted for definition text
- 1–2 boxes; alphabetical order within each box
- Body text: colour `#2C2C2C`, explicit `font-weight:400`
- Pale colours `#374151`, `#4B5563`, `#555` not permitted anywhere in articles
- No `fadeUp` or `opacity:0` animations on article body sections — content must be immediately visible on load
- Hero subtitle: minimum `rgba(255,255,255,0.85)`; below this not permitted
- Hero meta items: minimum `rgba(255,255,255,0.80)`
- Hero breadcrumb: minimum `rgba(255,255,255,0.75)`
- Values of 0.60 or below not permitted for hero/breadcrumb text

### Inline citations
- Every stat or claim in prose carries a superscript number linking to anchored reference `id="ref-N"`
- Format: `<sup><a href="#ref-1">1</a></sup>`
- Superscript link colour matches the series accent colour
- **This rule applies to stat grid `.stat-prose` text as well as body prose — every stat in every stat grid card must carry a superscript citation. No exceptions. Confirmed and locked April 2026.**

### The reason for the stat must be in the ev-outcome line — LOCKED APRIL 2026

**The comparison, intervention, or condition that produced the stat number — the REASON it is what it is — must appear in the `ev-outcome` line. It must never be relegated to `ev-conditions` where it sits at 0.78rem, the least prominent text in the stat box.**

The three stat box lines work as a strict hierarchy:
- `ev-stat-row` — the headline number (24%, 10.3 mo, 38.6 mo) at 3.2rem weight 900
- `ev-outcome` — the finding AND the reason: what changed AND what caused it / what it was compared to — at 0.95rem weight 700
- `ev-conditions` — population, dataset, trial name only — at 0.78rem

**Correct — reason in the ev-outcome line:**
```
ev-stat-row:   24%
ev-outcome:    reduction in lung-cancer mortality / CT screening vs no screening
ev-conditions: high-risk smokers · 10-year follow-up · NELSON trial
```

**Incorrect — reason buried in ev-conditions (smallest text):**
```
ev-stat-row:   24%
ev-outcome:    reduction in lung-cancer mortality
ev-conditions: CT screening vs no screening — high-risk smokers at 10 years (NELSON trial)
```

"CT screening vs no screening" is WHY the number is 24%. It cannot be the smallest text. A reader who sees only ev-stat-row and ev-outcome must immediately understand both the finding AND the reason — the stat and its cause — without needing to read the conditions line. The conditions line handles trial name and population only.

This rule strengthens the existing complete clinical conclusion standard. The prior instruction required the reason to be in the stat box — this instruction specifies it must be in ev-outcome, not ev-conditions.

**Canonical reference:** `lung-cancer.html` Article 29 research cards (April 2026):
- `24% / reduction in lung-cancer mortality / CT screening vs no screening`
- `10.3 mo / median PFS / pembrolizumab vs 6.0 months on chemotherapy`
- `38.6 mo / median overall survival / osimertinib vs 31.8 months on standard EGFR therapy`

**This applies equally to visuals ev-stat-boxes.** The same hierarchy applies: ev-outcome carries both the finding and the reason; ev-conditions carries trial/population context only.

### All stats require citations — in every location — LOCKED APRIL 2026

**Every numerical figure, percentage, or quantitative claim in any helf.school file requires an inline superscript citation — regardless of location.**

This applies universally to: body prose paragraphs, Key Terms box definitions, stat grid cards (covered separately by the stat grid citation rule), research card stat boxes and body text, Putting it all together box, discussion cards, myth panel evidence text, visuals slide text, and teleprompter scripts. No stat goes uncited anywhere.

**This rule was confirmed after Dr Paul identified in `lung-cancer.html` (Article 29, April 2026):**
1. An uncited statement "It is the most common cause of cancer death in the UK" in body prose paragraph 1
2. An uncited NSCLC proportion figure (80 to 85%) in body prose paragraph 2

Both were in body prose — locations previously assumed to be less rigorously checked than stat grid cards. Both were corrected. The rule is now explicit for all locations.

**Process before delivering any file:** scan every paragraph and every text element for numerical figures and percentages. Every one must have a superscript citation or be flagged ⚑.

### Subtypes, stages, and formally named sets — always list, never inline prose — LOCKED APRIL 2026

**When article body prose introduces a formally numbered or named set of items using a phrase such as "three main subtypes", "four stages", "two types of", or "the following five", those items must be presented in a numbered or bulleted HTML list — never run together as a comma-separated sequence within a prose paragraph.**

**The rule:** if you can count the items in the introductory sentence, they go in a list.

**Implementation:** use `<ol class="subtype-list">` with the canonical CSS pattern first introduced in `lung-cancer.html` (Article 29, April 2026):
- Numbered circle markers in series colour
- Bold term name followed by em-dash and definition
- Full body size (`.88rem` to `1rem`)

This applies to: cancer subtypes, disease subtypes, stages, treatment types, diagnostic criteria, risk factor categories, symptom categories, and any other formally introduced set of items with a count.

**Canonical reference:** `lung-cancer.html` Section 1 — NSCLC subtypes (adenocarcinoma, squamous cell carcinoma, large cell carcinoma) presented as a 3-item `<ol class="subtype-list">` (April 2026).

**Why this rule exists:** NSCLC subtypes were written as inline comma-separated prose in the first draft of `lung-cancer.html`. Dr Paul identified this as a formatting failure — distinct named items need visual separation so readers can find and refer back to individual items. Confirmed April 2026.

### Reference numbering — LOCKED APRIL 2026
References must display visible numbers. Use CSS `counter-reset` and `counter-increment` on `.ref-block` with a `::before` pseudo-element rendering the number to the left of the border. Delivered without visible numbering in April 2026 — caught by Dr Paul during review. Confirmed canonical: `prostate-cancer.html`.

### Article research card display standard — LOCKED APRIL 2026

**Canonical reference: `memory-dementia.html` (layout) + `breast-cancer.html` + `prostate-cancer.html` (colour principle)**

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
- "2.7% / prostate cancer-specific mortality at 15 years / similar across monitoring, surgery, and radiotherapy"
- "0.69% / prostate cancer mortality with PSA screening / vs 0.78% without screening"
- "81 months / median overall survival — docetaxel + hormone therapy / vs 71 months alone"

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
- goserelin (Zoladex)
- leuprorelin (Prostap)
- degarelix (Firmagon)
- relugolix (Orgovyx)
- docetaxel (Taxotere)
- abiraterone (Zytiga)
- enzalutamide (Xtandi)
- bicalutamide (Casodex)
- osimertinib (Tagrisso)
- erlotinib (Tarceva)
- gefitinib (Iressa)
- pembrolizumab (Keytruda)
- pemetrexed (Alimta)

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

**MAXIMUM SIZE MANDATE — LOCKED APRIL 2026: Every visual element must be as big as the parameters make possible. The permitted parameters (max padding, min text size, max gap) define the floor — not the target. Push every element to the largest size that fits without overflow. Dr Paul's instruction: "visuals on each slide must be as big as parameters make possible."**

The fixed viewport is `100vw × 100vh` minus the 52px topbar and 32px dots bar = approximately `calc(100vh - 84px)` of usable vertical space. Every slide must use this space aggressively. Content that occupies only 60–70% of the screen with large empty areas is a failure.

**Required minimums/maximums — apply to every slide:**
- Slide padding: maximum `1rem 1.5rem 0.8rem` — never `1.8rem` or more top padding
- Slide header margin-bottom: `.4rem` — never `.55rem` or more
- Slide title: minimum `1.72rem` — never `1.35rem`
- Slide subtitle margin-bottom: maximum `.4rem` — never `.6rem`
- All body text in cards and rows: minimum `.93rem` — never `.90rem` if space allows more
- Card/row gaps: maximum `.48rem` — never `.7rem` or `.9rem` between items
- Card padding: `.82rem 1rem` — tight but readable; never `.9rem 1.1rem` or larger
- Info/step row body line clamp: minimum 5 lines — never 4 lines (wastes space)
- Ev-body paragraph: minimum `.94rem`, line clamp minimum 7 lines
- Card icons: minimum `1.55rem`
- Card titles: minimum `1.12rem`

**The maximum-size principle:** Start from the largest font size that fills the space and reduce only if content overflows. Never start from the minimum and accept empty space. If a card has visible empty space below its text, the font is too small or the line clamp is too low.

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

### 3-CARD RULE — NEVER SHRINK TEXT TO FIT — LOCKED APRIL 2026

**When a slide contains 6 cards, always split into two slides of 3 cards each. Never reduce font size or line clamp to make 6 cards fit.**

This rule was confirmed April 2026 after multiple 6-card slides were delivered with text cut off at the bottom of cards. The correct approach: split to 3+3, label slides "(1 of 2)" and "(2 of 2)". 3-card slides use `-webkit-line-clamp:4` so body text can breathe fully.

Articles with 6 informational points (what is it, risk factors, diagnosis, treatment) will produce two slides each — typically resulting in 14-slide decks rather than 10. This is correct and expected.

**Canonical reference for 3-card layout:** `prostate-cancer-visuals.html` (slides 3–10).

### Layout
- **3-card slides: `three-grid` class** — `grid-template-rows: repeat(3, 1fr); gap: .55rem` — fills viewport
- **6-card slides are FORBIDDEN** — always split to 3+3
- Stats: 2.5–3.6rem font size
- Colour narrative: red = harm · amber = mechanism · green = action
- Cards: `min-height:0` + `overflow:hidden`
- Max 2 `ev-cards` per research slide
- CTA section: `cta-wrap-v2` class — `grid-template-rows: auto 1fr auto` — the ONLY correct CTA layout
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

### CTA slide standard — LOCKED APRIL 2026 — canonical: `prostate-cancer-visuals.html` slide 13
- **`cta-wrap-v2` class with `grid-template-rows: auto 1fr auto`** — this is the ONLY correct layout. `auto 1fr auto` means: badge/headline takes natural height, 4 rows expand to fill remaining space, disclaimer anchors at bottom. Nothing is ever clipped. **Never use `justify-content: center` or `justify-content: space-between` on the CTA slide — both clip content.**
- Full-screen with radial gold-glow background + pulsing icon halo (3.2s drop-shadow)
- **Central icon: minimum `5.5rem`** — the icon must dominate the slide visually.
- **Fraunces headline: minimum `clamp(2.8rem, 5.5vw, 4.2rem)`**
- **No subline mentioning "free at helf.school"** — helf.school is a subscription service. **LOCKED APRIL 2026.**
- 4 horizontal action rows in `.cta-rows-v2` — `grid-template-rows: 1fr 1fr 1fr 1fr`
- **`med-disclaimer` at bottom — `font-size:1rem` on `.med-disc-text`** — never `.80rem`
- **`cta-glow` radial gradient overlay** — gold glow behind content
- Reference: `prostate-cancer-visuals.html` slide 13

### Closing slide standard — NEW STANDARD LOCKED APRIL 2026 — canonical: `prostate-cancer-visuals.html` slide 14

The closing slide is now the **helf.school brand close** — NOT a repeat of the research stats from the CTA slide.

**Structure:**
- `close-wrap` with `justify-content: flex-start` — **NEVER `justify-content: center`** (clips the logo at top when content height approaches viewport height)
- **helf.school logo** — large Fraunces, with coral dot
- **"Health Education" tagline** — uppercase
- **Brand headline** — e.g. "Evidence-based. Built by a doctor."
- **Three brand pitch cards:**
  1. 📚 Article count and series breadth
  2. 🩺 Dr Paul's credentials — "retired NHS GP with over 20 years of experience"
  3. 🔓 Start for free — Explorer tier
- **`med-disclaimer`** at `font-size:1rem`
- **Series label** — e.g. "Cancer Series · Article 28 · Prostate Cancer"

**Why this standard was adopted:** The previous closing slide repeated the research stats already shown on the CTA slide. Dr Paul identified this as redundant — the closing slide should be the brand impression, not a stat recap. Confirmed April 2026.

**`justify-content: flex-start` is mandatory** — `center` clips the logo at the top when total content height is close to the viewport height. `flex-start` anchors the logo visibly and any overflow falls off the bottom.

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

### Cue box — paired slides — CONFIRMED APRIL 2026
When two slides share a segment (e.g. slides 3–4 on the same topic), the cue box label reads the slide range: e.g. `Slides 3–4 — What is prostate cancer?`. The final cue box in the last segment advances to the closing slide. Confirmed in `prostate-cancer-teleprompter.html` April 2026.

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
11. CTA slide — `cta-wrap-v2` with `grid-template-rows: auto 1fr auto`; `med-disc-text` at `font-size:1rem`
12. Closing slide — brand close structure; `justify-content: flex-start`; three pitch cards; `med-disc-text` at `font-size:1rem`; series label
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
26. **CLOSING SLIDE DISCLAIMER SIZE — LOCKED APRIL 2026:** The closing slide must use `justify-content: flex-start` and `med-disc-text` at `font-size:1rem`. Brand close structure — three pitch cards (articles / Dr Paul / free tier). Never stat repeat. Never `justify-content: center` — clips logo at top.
27. **CTA SLIDE DISCLAIMER SIZE — LOCKED APRIL 2026:** CTA disclaimer text must be `font-size:1rem`, `color:rgba(255,255,255,0.90)`. Never `.80rem`. Run a grep check before presenting any visuals file.
28. **NO "FREE AT HELF.SCHOOL" ON VISUALS — LOCKED APRIL 2026:** The subline on the CTA slide must not reference being "free at helf.school" — helf.school is a subscription service and this is inaccurate. "Start for free" (the £0 Explorer tier) is permitted as a card label. "Free to read — always" is not permitted. Check the CTA slide subline before presenting any visuals file.
29. **3-CARD RULE — LOCKED APRIL 2026:** Never 6 cards on one slide. Always split to 3+3. Canonical: `prostate-cancer-visuals.html` slides 3–10.
30. **REFERENCE NUMBERING — LOCKED APRIL 2026:** References must display visible numbers via CSS counter. Never deliver a reference list without visible numbering. Canonical: `prostate-cancer.html`.
31. **ALL STATS REQUIRE CITATIONS — EVERY LOCATION — LOCKED APRIL 2026:** Before presenting any article, visuals, or teleprompter file, scan every paragraph and text element for numerical figures and percentages. Every stat in every location — body prose, Key Terms box, stat grid cards, research card text, Putting it all together box, discussion cards, myth panel evidence text, visuals slides — must carry an inline superscript citation. No exceptions. This rule was confirmed after Dr Paul identified two uncited stats in `lung-cancer.html` Article 29 body prose (April 2026).
32. **SUBTYPE/LIST FORMATTING — LOCKED APRIL 2026:** When body prose introduces a formally counted or named set of items ("three main subtypes", "four stages", "two types of"), those items must appear in a `<ol class="subtype-list">` numbered list — never as comma-separated inline prose. Grep for phrases like "three main", "four types", "two subtypes" before presenting any article. Canonical: `lung-cancer.html` Section 1 (Article 29, April 2026).
33. **ev-outcome MUST CARRY THE REASON — LOCKED APRIL 2026:** Before presenting any article or visuals file with research cards, check every ev-outcome line. It must state BOTH the finding AND the comparison/intervention that produced the stat number. "24%" is not enough — "reduction in lung-cancer mortality / CT screening vs no screening" is correct. The comparison must never appear only in ev-conditions. Read ev-stat-row + ev-outcome together: if a reader can't understand the stat AND its cause from those two lines alone, rewrite ev-outcome. Canonical: `lung-cancer.html` Article 29 research cards (April 2026).

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

BMJ · NICE guidelines · Cochrane Database · NEJM · The Lancet · JAMA · BMJ Best Practice · PubMed · NHS/NHS Digital · ONS · CDC · WHO · Global Burden of Disease Study · ESC/EAS guidelines · Alimentary Pharmacology & Therapeutics · European Heart Journal · QJM · Epilepsia · Seizure: European Journal of Epilepsy · JAMA Neurology · BJC Reports (British Journal of Cancer Reports, Springer Nature — added April 2026 for LCINS Article 29 ref 6)

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
- CTA slide high-impact standard (`cta-wrap-v2`, gold-glow, 4 action rows): outstanding across 01–11
- **Closing slide brand close standard: outstanding across 01–26** — all previously built visuals files use the old stat-recap closing slide. Retrofit when files are next opened.
- Visuals layout standard (3-card split, ev-stat-row): outstanding across 01–11
- Key terms / hero visibility standards: outstanding across 01–11
- Teleprompter cue box standard: confirm per-file which were built before standard was set
- **Subtype list formatting: outstanding across all articles** — apply `<ol class="subtype-list">` pattern when any article is next opened and contains formally introduced sets of items. Canonical: `lung-cancer.html` (April 2026).

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
Initial colour `#8A3A5A` (deep rose) was proposed and approved but rendered poorly — the monochromatic dark rose/pink scheme gave insufficient contrast between card backgrounds and text. Changed to `#2A5A3A` (forest green) with dark variant `#1A3A25`. Forest green is distinct from existing teal `#3A8A7A` and olive `#7A6A2E`. **The Article Inventory previously showed `#8A3A5A` — this was an error in the document. Corrected April 2026.**

### Research card stat boxes use series colour, not navy — LOCKED APRIL 2026
The ev-stat-box background in article research cards must use the series colour gradient (series-dark to series), not plain navy. Established when building breast-cancer.html for the Cancer Series. The amber kf-label contrasts effectively against any series colour. This principle makes each series visually distinctive and reinforces series identity throughout the article. Each series needs a confirmed dark variant colour before this standard can be retrofitted. See Section 2 for the dark variant table.

### Article research card display standard confirmed — April 2026
The research card stat box in articles must be visually commanding. ev-stat-row: 3.2rem weight 900. The stat box is the headline — it must lead with the clinically important finding in a size that commands attention. Canonical reference: `breast-cancer.html`. See Section 8 for the full CSS specification.

### Series dark variants must be confirmed before retrofit — April 2026
The series-coloured stat box gradient requires a dark variant for each series. Proposed variants are in Section 2. Dr Paul must confirm each dark variant before the research card colour retrofit is applied to existing articles.
Cancer Research UK is approved for UK cancer incidence, mortality, survival, and risk statistics. Always fetch their statistics pages directly.

### Closing slide disclaimer must use .closing-disclaimer class at 1rem — LOCKED APRIL 2026
The closing slide disclaimer must use the `.closing-disclaimer` / `.closing-disclaimer-text` classes at `font-size:1rem`, not the `.cta-disclaimer` class at `.80rem`. The closing slide is the final thing the audience sees — it must be clearly readable on camera. Multiple files were delivered with the wrong class reused from the CTA slide. QC item 26 now checks this.

### Cancer Series — three elements use series green, not navy — LOCKED APRIL 2026
In Cancer Series articles, the Key Terms box, Putting it all together box, and research card stat boxes all use `linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%)` — forest green gradient — instead of plain navy. This creates a consistent series identity throughout the article. Confirmed in `breast-cancer.html` April 2026. Apply from the start in articles 28–31.

### CTA slide must not reference "free at helf.school" — LOCKED APRIL 2026
The subline on the CTA slide must not say "Evidence-based health education — free at helf.school" or any variation. helf.school is a subscription service. "Start for free" is permitted as a card label — there is a genuine £0 Explorer tier. "Free to read — always" is not permitted. This was caught by Dr Paul reviewing breast-cancer-visuals.html in April 2026. QC item 28 now checks this.

### CTA disclaimer text size locked at 1rem — LOCKED APRIL 2026
CTA slide disclaimer text must be `font-size:1rem`, `color:rgba(255,255,255,0.90)`. Never `.80rem` — too small to read on screen. QC item 27 enforces this.

### Cancer Series established — April 2026
Series E. Articles 27–31. Colour `#2A5A3A` (forest green, confirmed April 2026 — initial rose colour `#8A3A5A` rejected due to contrast issues). Dark variant `#1A3A25`.

### Never rebuild a project knowledge document from scratch — LOCKED APRIL 2026
When updating the project knowledge document, always use the existing document as the base and merge new content into it. Never rebuild from memory. The existing document is always larger and more complete than what Claude can reconstruct from memory in a session. Rebuilding from memory loses content and introduces errors. The correct process: read the existing document → identify what is new → add new content to the existing document → verify the new version is equal to or larger than the old one.

### Closing slide must be brand close, not stat repeat — LOCKED APRIL 2026
The last slide of every visuals deck is the **helf.school brand close**: logo · "Health Education" tagline · brand headline · three pitch cards (articles, Dr Paul credentials, free tier) · `med-disclaimer` · series label. It is NOT a repeat of the research statistics shown on the CTA slide. Confirmed April 2026 when Dr Paul identified stat repeat as redundant. Canonical reference: `prostate-cancer-visuals.html` slide 14.

### Closing slide must use `justify-content: flex-start` — LOCKED APRIL 2026
`justify-content: center` clips the logo at the top when total content height is close to viewport height. `flex-start` anchors the logo visibly. Confirmed April 2026 after multiple deliveries clipped the helf.school logo. Canonical reference: `prostate-cancer-visuals.html` slide 14.

### CTA slide must use `cta-wrap-v2` with `grid-template-rows: auto 1fr auto` — LOCKED APRIL 2026
This is the only correct CTA layout. `auto 1fr auto` ensures: top badge/headline takes natural height, middle rows expand to fill remaining space, bottom disclaimer always fully visible. `justify-content: center` or `justify-content: space-between` both cause content to clip. Confirmed after multiple CTA slide deliveries with cut-off content April 2026.

### 6-card slides must be split to 3+3 — LOCKED APRIL 2026
When a visuals slide has 6 informational cards, always split into two slides of 3 cards each. Never reduce font size or line clamp to make 6 cards fit. Text cut-off on 6-card slides confirmed as a recurring problem April 2026. 3-card slides use `-webkit-line-clamp:4` allowing body text to breathe. Canonical reference: `prostate-cancer-visuals.html` slides 3–10.

### Reference numbering must be visible — LOCKED APRIL 2026
References must display visible numbers. Use CSS `counter-reset` and `counter-increment` on `.ref-block` with a `::before` pseudo-element to render the number to the left of the border. Delivered without visible numbering once in April 2026 — caught by Dr Paul.

### prostate-cancer-visuals.html is new canonical visuals reference — LOCKED APRIL 2026
`prostate-cancer-visuals.html` replaces `lifestyle-changes-visuals.html` as the primary canonical visuals reference. It demonstrates: 3-card split slides (slides 3–10), canonical `cta-wrap-v2` CTA (slide 13), brand close (slide 14), `ev-card` research cards with forest green gradient stat box, correct `#stage` padding and `#topbar` structure.

### All stats require citations in every location — LOCKED APRIL 2026
Dr Paul identified in `lung-cancer.html` (Article 29, April 2026): (1) "It is the most common cause of cancer death in the UK" — no inline citation in body prose paragraph 1; (2) "around 85% of all lung cancers are NSCLC" — no inline citation in body prose paragraph 2. Both were body prose statements, not stat grid cards. This confirmed that the citation requirement applies universally to every location where a numerical claim appears — not just stat grid cards. The QC checklist now includes item 31 covering all locations. Pre-output audit item 9 was added to enforce this. The rule: if it's a number, it needs a citation.

### Subtypes and formally named sets must be listed, not written in prose — LOCKED APRIL 2026
Dr Paul identified that NSCLC subtypes (adenocarcinoma, squamous cell carcinoma, large cell carcinoma) were written as inline comma-separated prose in the first draft of `lung-cancer.html` Section 1. The rule is now explicit: any set of items introduced with a counted phrase ("three main subtypes", "four stages") must be presented as a numbered or bulleted list using `<ol class="subtype-list">`. The CSS pattern for this list was first introduced in `lung-cancer.html` (Article 29, April 2026): numbered circle markers in series colour, bold term + em-dash + definition, full body size. QC item 32 enforces this at delivery.

### The reason for the stat must be in ev-outcome, not ev-conditions — LOCKED APRIL 2026
The comparison or intervention that produced a research card stat — the REASON the number is what it is — must appear in the `ev-outcome` line (0.95rem weight 700), not relegated to `ev-conditions` (0.78rem, the smallest text in the box). "CT screening vs no screening" is WHY the number is 24% — it must be prominently visible. The complete clinical conclusion rule already required the reason to be somewhere in the stat box; this rule specifies it must be in ev-outcome specifically. Confirmed and locked April 2026 when Dr Paul identified that the comparison was appearing in ev-conditions rather than ev-outcome across multiple research cards. Canonical: `lung-cancer.html` Article 29 (April 2026): "reduction in lung-cancer mortality / CT screening vs no screening" in ev-outcome; "high-risk smokers · 10-year follow-up · NELSON trial" in ev-conditions.

---

## 19. OUTSTANDING TASKS (April 2026)

### Immediate — uploads outstanding
- Upload `breast-cancer.html`, `breast-cancer-visuals.html`, `breast-cancer-teleprompter.html` to GitHub
- Upload `prostate-cancer.html`, `prostate-cancer-visuals.html`, `prostate-cancer-teleprompter.html` to GitHub
- Upload `helf-school-conditions.html` to GitHub (updated: Article 28 now live, hero stat 28)

### Cancer Series — Article 29 (Lung Cancer) — in progress
- `lung-cancer.html` — built April 2026 ✅ (includes myth-busting panel, numbered subtype list, 7 references, 4 research flags)
- `lung-cancer-visuals.html` — not yet built
- `lung-cancer-teleprompter.html` — not yet built
- **Research flags outstanding in lung-cancer.html:**
  1. NSCLC/SCLC proportion (80 to 85%) — cited to NICE NG122, confirm this figure appears in NG122 text; if not, use NICE TA1043 or flag for primary epidemiological source
  2. EGFR mutation prevalence (10–15%) and ALK rearrangement (3–5%) — confirm in NICE NG122
  3. Stage 3 and stage 4 five-year survival figures — not yet added; available on CRUK survival page
  4. PD-L1 "approximately 23 to 28%" figure — verified from KEYNOTE-024 paper, no flag needed

### Cancer Series — next articles to build
- Article 30: Bowel (Colorectal) Cancer
- Article 31: Melanoma and Skin Cancer

### Practical Health Series extension — next articles to build
- Article 32: Breast Awareness (cross-referenced from breast-cancer.html — marked "Coming soon")
- Article 33: Testicular Awareness

### Verification
- `hypertension.html` references 5 & 6 — Cochrane PubMed IDs flagged ⚑ unverified

### Retrofit backlog (Articles 01–26 — apply when files next opened)
All dark variants confirmed April 2026 — retrofit is fully unblocked. Apply per series as files are next opened. Priority order:

1. **Research card colour retrofit** ← highest priority, highest visual impact — ev-stat-box background: navy → series-colour gradient. Spec: `linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%)`. Dark variants confirmed for all series (see Section 2). Apply across all 26 articles.
2. **Closing slide brand close retrofit** — stat-recap closing → brand close (logo / pitch cards / disclaimer). Apply across all 26 visuals files.
3. **Key Terms + Putting it all together** — navy → series-colour gradient. Cancer Series standard confirmed. Decision outstanding: extend to all series or Cancer-only? If extending, same gradient spec applies.
4. **Research card display standard** — ev-stat-row to 3.2rem weight 900 across all articles.
5. **Closing/CTA disclaimer sizes** — closing: `med-disc-text` 1rem; CTA: `med-disc-text` 1rem. Quick grep check per file.
6. **No "free at helf.school"** — grep CTA subline per visuals file.
7. **Research card clinical conclusion standard** — 01–23.
8. **Stat grid citations** — 01–11 only.
9. **Inline citations** — 01–11 only.
10. **CTA slide standard** — 01–11 only.
11. **Visuals layout standard** — 01–11 only.
12. **Subtype list formatting** — apply `<ol class="subtype-list">` to any article containing formally introduced sets of items (subtypes, stages, types). Canonical: `lung-cancer.html`.

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
| `prostate-cancer-visuals.html` | **PRIMARY canonical visuals reference** — 3-card splits, `cta-wrap-v2`, brand close, ev-card research cards. Confirmed April 2026. |
| `lifestyle-changes-visuals.html` | Secondary visuals reference — 6-row grid pattern (still valid for mechanism/info slides where appropriate) |
| `hypertension-visuals.html` | Legacy CTA slide reference (superseded by prostate-cancer-visuals.html) |
| `memory-dementia.html` | Canonical article research card layout (220px column, flex-start) |
| `breast-cancer.html` | Canonical article research card display (3.2rem stat, series gradient background) |
| `prostate-cancer.html` | Cancer Series article canonical — reference numbering via CSS counter |
| `lung-cancer.html` | Canonical article for: myth-busting panel design; `<ol class="subtype-list">` numbered list pattern |

### Files confirmed in Claude project (April 2026)
**Teleprompters (all series):** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd · ibs · bloating · coeliac · masld · acid-reflux · constipation · migraine · headaches · dizziness-vertigo · memory-dementia · epilepsy · prostate-cancer

**Visuals (all series):** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd (screen) · ibs · bloating · coeliac · masld · acid-reflux · constipation · migraine · headaches · dizziness-vertigo · memory-dementia · epilepsy · prostate-cancer

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

### Rule 19 — Cancer Series: three elements use series green, not navy — LOCKED APRIL 2026
In Cancer Series articles (27–31), three elements must use `linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%)` — the forest green gradient — instead of plain navy:
1. **Key Terms box**
2. **Putting it all together box**
3. **Research card stat box**
Cancer Series colours: `--series: #2A5A3A` · `--series-dark: #1A3A25`. Apply from the start when building articles 28–31.

### Rule 20 — Closing slide: brand close, `justify-content: flex-start` — LOCKED APRIL 2026
The closing slide must be the helf.school brand close — NOT a stat repeat. `justify-content: flex-start` is mandatory — never `center`. Structure: logo · tagline · brand headline · three pitch cards (articles / Dr Paul / free tier) · `med-disclaimer` · series label. Canonical: `prostate-cancer-visuals.html` slide 14.

### Rule 21 — CTA slide: `cta-wrap-v2` with `grid-template-rows: auto 1fr auto` — LOCKED APRIL 2026
Only correct CTA layout. `auto 1fr auto` guarantees: top takes natural height, middle rows fill remaining space, bottom disclaimer always visible. Never `justify-content: center` or `space-between` — both clip content. Canonical: `prostate-cancer-visuals.html` slide 13.

### Rule 22 — 3-card rule: never 6 cards on one slide — LOCKED APRIL 2026
Always split to 3+3. Label "(1 of 2)" and "(2 of 2)". 3-card slides use `-webkit-line-clamp:4`. Canonical: `prostate-cancer-visuals.html` slides 3–10.

### Rule 23 — Dark variants confirmed: retrofit unblocked — April 2026

| Series | Primary | Dark variant |
|--------|---------|-------------|
| Cardiovascular | `#C8423A` | `#8A2020` |
| Neurological | `#6B5EA8` | `#4A4080` |
| Digestive | `#D47C3A` | `#8A4A1A` |
| Fatigue | `#3A8A7A` | `#1A5A4A` |
| Medical Decision | `#2E6BA8` | `#1A3A6A` |
| Practical Health | `#7A6A2E` | `#4A3A1A` |
| Cancer | `#2A5A3A` | `#1A3A25` |

### Rule 24 — All stats require citations in every location — LOCKED APRIL 2026
Every numerical figure, percentage, or quantitative claim in any helf.school file requires an inline superscript citation — regardless of location. This covers: body prose paragraphs, Key Terms box definitions, stat grid cards, research card text, Putting it all together box, discussion cards, myth panel evidence text, visuals slide text, and teleprompter scripts. Before presenting any file, scan every paragraph and text element for uncited numerical claims. No exceptions. Confirmed after Dr Paul identified two uncited body prose stats in `lung-cancer.html` Article 29 (April 2026).

### Rule 25 — Subtypes and formally named sets must be listed — LOCKED APRIL 2026
When article body prose introduces a formally counted or named set of items using a phrase like "three main subtypes", "four stages", "two types of", those items must be presented in a numbered or bulleted HTML list (`<ol class="subtype-list">`) — never as inline comma-separated prose. Canonical reference: `lung-cancer.html` Section 1 NSCLC subtypes (Article 29, April 2026). Apply this pattern when retrofitting or building any article that contains formally introduced sets of items.

---

## CONFIRMED FILE STATUS — UPDATED APRIL 2026

**AUTHORITY NOTE: If any entry below conflicts with the article inventory in Section 3, Section 3 is correct.**

### Cardiovascular Series (01–07) — ALL COMPLETE ON GITHUB ✅

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

### Digestive Health Series (13–21) — ALL BUILT ✅

| File | Status |
|------|--------|
| acid-reflux.html + visuals + teleprompter | ✅ On GitHub |
| ibd.html + visuals + teleprompter | ✅ On GitHub |
| bloating.html + visuals + teleprompter | ✅ On GitHub |
| ibs.html + visuals + teleprompter | ✅ On GitHub |
| masld.html + visuals + teleprompter | ✅ On GitHub |
| coeliac.html + visuals + teleprompter | ✅ On GitHub |
| gallstones.html + visuals + teleprompter | ✅ On GitHub |
| diverticular-disease.html + visuals + teleprompter | ✅ On GitHub |
| constipation.html + visuals + teleprompter | ✅ Built April 2026 — on GitHub |

### Neurological Series (22–26) — ALL BUILT ✅

| File | Status |
|------|--------|
| migraine.html + visuals + teleprompter | ✅ Built April 2026 — on GitHub |
| headaches.html + visuals + teleprompter | ✅ Built April 2026 — on GitHub |
| dizziness-vertigo.html + visuals + teleprompter | ✅ Built April 2026 — on GitHub |
| memory-dementia.html + visuals + teleprompter | ✅ Built April 2026 — on GitHub |
| epilepsy.html + visuals + teleprompter | ✅ Built April 2026 — on GitHub |

### Cancer Series (27–31) — IN PROGRESS

| File | Status |
|------|--------|
| breast-cancer.html + visuals + teleprompter | ✅ All 3 files built April 2026 — upload to GitHub outstanding |
| prostate-cancer.html + visuals + teleprompter | ✅ All 3 files built April 2026 — upload to GitHub outstanding |
| lung-cancer.html | ✅ Article HTML built April 2026 — visuals and teleprompter outstanding |
| bowel-cancer.html + visuals + teleprompter | Not yet built |
| melanoma.html + visuals + teleprompter | Not yet built |

### OUTSTANDING CITATION FLAGS
- hypertension.html refs 5 + 6 — Cochrane PubMed IDs flagged ⚑ unverified

---

## 23. ARTICLE-SPECIFIC NOTES — KNOWN ISSUES

### hypertension.html
References 5 and 6 — Cochrane PubMed IDs flagged ⚑ unverified. These need verification via web search before the article can be confirmed fully complete.

### statins.html
Very large HTML file — has caused mid-build crashes in previous sessions. If this file needs to be rebuilt or significantly edited, handle it in one dedicated turn.

### conditions page (helf-school-conditions.html)
Rebuilt April 2026 — shows 28 articles live across 5 series (Articles 27–28 live in Cancer series, 29–31 coming soon). Hero stat: 28 articles live now.

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
- Cross-reference signpost box added in Section 3 after symptoms paragraph — signposts forthcoming Article 32 (Breast Awareness, Practical Health series), marked "Coming soon"

### prostate-cancer.html — April 2026 decisions
- Cancer Series Article 28. Colour `#2A5A3A` (forest green, dark variant `#1A3A25`)
- Incidence: "~57,900" — Cancer Research UK directly (2019/2021–2022)
- 10-year survival: "78.9%" — Cancer Research UK (2018)
- Deaths: "~12,200" — Cancer Research UK (2021–2023)
- NICE NG131 (Prostate cancer: diagnosis and management) — primary clinical reference
- 3 research cards: ProtecT (Hamdy NEJM 2023, PMID 36912538); CAP trial (Martin JAMA 2024, PMID 38581198); STAMPEDE (James Lancet 2016, PMID 26719232)
- PSA "3 in 4 will not have cancer" — cited Cancer Research UK (citing NICE NG12) as ref 6
- Biopsy wording: NICE NG131 acknowledges shift to transperineal; does not formally recommend one approach over the other — wording corrected from overstated original
- ADT side effects: cited NICE NG131
- LHRH antagonists named: degarelix (Firmagon), relugolix (Orgovyx)
- All 4 stat grid cards carry inline citations ✅
- References numbered via CSS counter ✅
- All PMIDs verified by web search in session ✅
- All 3 files built April 2026 ✅ — upload to GitHub outstanding
- Visuals: 14 slides (3-card split pattern) — new canonical reference for all future visuals
- Teleprompter: 9 segments, 10 cue boxes, 712 words

### lung-cancer.html — April 2026 decisions
- Cancer Series Article 29. Colour `#2A5A3A` (forest green, dark variant `#1A3A25`)
- **Myth-busting panel** at top of article body (before Section 1) — 2×2 dark navy grid; 4 myths vs evidence panels; confirmed citation for each
- 3 research cards: NELSON (de Koning NEJM 2020, PMID 31995683); KEYNOTE-024 (Reck NEJM 2016, PMID 27718847); FLAURA OS (Ramalingam NEJM 2020, PMID 31751012)
- 7 references total: CRUK stats (ref 1); NICE NG122 (ref 2); NELSON (ref 3); KEYNOTE-024 (ref 4); FLAURA (ref 5); Khan et al BJC Reports 2023 PMID 39516402 (ref 6 — never-smokers 15%); Doll et al BMJ 2004 PMID 15213107 (ref 7 — cessation halves hazard at age 50)
- Incidence ~49,300 · deaths ~32,800 · 10-year survival 11.1% · 79% preventable — all from CRUK ref 1 directly
- 72% caused by smoking / 79% total preventable fraction: both cited from CRUK ref 1, clearly distinguished in Section 1 paragraph 3
- NSCLC subtypes presented as `<ol class="subtype-list">` numbered list — first use of this pattern ← canonical
- **Research flags outstanding:** NSCLC/SCLC proportion needs confirmation in NICE NG122 text; EGFR/ALK prevalence needs confirmation in NICE NG122; stage 3/4 survival figures not yet added; PD-L1 23–28% verified from KEYNOTE-024 ✅
- Article HTML built April 2026 ✅ — visuals and teleprompter outstanding

---

## 24. PLANNING NOTES — NEXT SERIES

### Neurological Series (Articles 22–26) — COMPLETE APRIL 2026
Series colour: `#6B5EA8` (purple)

### Practical Health Series extension — Articles 32–33 (planned April 2026)

**Article 32 — Breast Awareness**
- Practical Health series · slug: `breast-awareness` · colour: `#7A6A2E`
- Short practical article — NOT a cancer biology article. Covers: what breast tissue normally looks and feels like, changes that are clinically recognised as worth discussing with a GP, how breast awareness fits alongside the NHS screening programme
- Key clinical distinction to observe: NICE and Cancer Research UK moved away from recommending scheduled monthly breast self-examination (Cochrane evidence found no mortality benefit from formal BSE routines) towards breast awareness — knowing what's normal for you and noticing changes. The article must reflect this distinction.
- Sources: NICE NG101, Cancer Research UK, NHS
- Cross-referenced from `breast-cancer.html` Section 3 — "Coming soon in the Practical Health series"

**Article 33 — Testicular Awareness**
- Practical Health series · slug: `testicular-awareness` · colour: `#7A6A2E`
- Short practical article aimed primarily at young men (peak age for testicular cancer: 20s–30s)
- Covers: what is normal, changes to notice (painless lump or swelling, change in size or shape, heaviness), why early detection matters
- Sources: Cancer Research UK, NHS, NICE
- Testicular cancer is the most common cancer in men aged 15–49 in the UK — a strong health education hook

### Cancer Series (Articles 27–31) — IN PROGRESS
Series colour: `#2A5A3A` (forest green). Dark variant: `#1A3A25`. Confirmed April 2026.

| # | Title | Slug | Status |
|---|-------|------|--------|
| 27 | Breast Cancer | breast-cancer | All 3 files built April 2026 ✅ — upload to GitHub outstanding |
| 28 | Prostate Cancer | prostate-cancer | All 3 files built April 2026 ✅ — upload to GitHub outstanding |
| 29 | Lung Cancer | lung-cancer | Article HTML built April 2026 ✅ — visuals and teleprompter outstanding |
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

### Subtype list — canonical CSS pattern — LOCKED APRIL 2026
When body prose introduces a formally counted set of items, use this pattern (first introduced `lung-cancer.html` April 2026):
```css
.article-wrap ol.subtype-list { counter-reset: subtype-counter; list-style: none; padding-left: 0; display: flex; flex-direction: column; gap: .45rem; margin: .6rem 0 1rem 0; }
.article-wrap ol.subtype-list li { counter-increment: subtype-counter; display: flex; gap: .7rem; align-items: flex-start; font-size: 1rem; line-height: 1.72; color: var(--text); font-weight: 400; }
.article-wrap ol.subtype-list li::before { content: counter(subtype-counter); background: var(--series); color: #fff; font-size: .72rem; font-weight: 700; width: 1.45rem; height: 1.45rem; border-radius: 50%; display: flex; align-items: center; justify-content: center; flex-shrink: 0; margin-top: .22rem; }
```
HTML: `<ol class="subtype-list"><li><strong>Name</strong> — definition text.</li></ol>`

### Project knowledge update — mandatory process — LOCKED APRIL 2026
1. Read the existing project knowledge document in full before writing a single word of the update
2. Identify what is new from the current session only
3. Add new content to the existing document — do not rewrite or abbreviate existing sections
4. Run `wc -l` on the new file and confirm it is equal to or greater than the previous version
5. Verify all 25 sections are present
6. Never deliver a shorter version without explicit explanation and Dr Paul's confirmation

---

*End of document. Update at the end of every session. Download via Artifact panel. Upload to both GitHub (pls4286/helfschool/main) and the Claude Project to take effect in future sessions.*
