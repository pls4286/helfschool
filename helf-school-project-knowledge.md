# helf.school — Project Knowledge
**Last updated: May 2026**

---

## ⚠️ DOCUMENT INTEGRITY — CLAUDE MUST READ THIS BEFORE ANY SESSION WORK

**This document has 25 numbered sections. Minimum expected line count: ~1760 lines.**

When updating this document at the end of any session, Claude MUST:
1. Run `wc -l` on the new file before presenting it to Dr Paul
2. Confirm the new line count is **equal to or greater than** the previous version
3. Verify all 25 sections are present by scanning for each section heading
4. **Never deliver a shorter version without explicitly stating which sections were reduced, why, and receiving Dr Paul’s confirmation before delivery**

If the new line count is lower and Claude cannot account for every removed line, the file is incomplete. Do not deliver it. Identify what is missing and restore it first.

Dr Paul cannot be expected to check line counts or audit section completeness himself. This is entirely Claude’s responsibility. Delivering a shorter file without explanation is a failure.

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

### Platform strategy — decided May 2026
**Recommended platform: Ghost Pro** (~£25/month Creator tier). Handles membership, Stripe payments, article gating, and newsletter natively. No developer required.

**Content model (confirmed May 2026):**
- One article per week (full production: research → article HTML → visuals → teleprompter → film → edit)
- Fortnightly newsletter — health headline analysis: current media story + evidence behind it + what the reality actually is
- No community forum — insufficient hours to moderate safely; dropped in favour of one-way newsletter + comments
- Videos hosted on YouTube (free), embedded per article

**Paywall model — Option 3: partial preview (confirmed May 2026)**
- Every article: first section free (What is it? + Key Terms) — indexed by Google, visible to all
- Full article (Why does it matter / What your doctor might discuss / What the research shows / Putting it all together) — members only
- Videos: members only
- Rationale: all articles indexed by Google (maximum SEO surface area), quality evident from free preview, clear incentive to join at the natural paywall break point

**Revenue model:**
- £0 Explorer · £6/month or £60/year Member · £150 Lifetime
- Lifetime tier: push hard at launch — 20 early adopters = £3,000 upfront
- Break-even: ~5 paying members covers Ghost Pro costs

**Video production workflow (confirmed May 2026):**
- Session 1: Film talking head reading teleprompter straight through. One take. No visuals yet.
- Session 2: Screen-record visuals file. Advance each slide slowly, hold several seconds. No audio.
- DaVinci Resolve edit: talking head on track 1 throughout. Visuals on track 2 — cut in wherever the spoken words match each slide. Teleprompter filming guide used as editing reference.

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
Articles 32–33 extending the Practical Health series. Same series colour `#7A6A2E`.

| # | Title | Slug | Status |
|---|-------|------|--------|
| 08 | The Mediterranean Diet | mediterranean-diet | All 3 files on GitHub ✅ |
| 09 | Sleep and Your Health | sleep | All 3 files on GitHub ✅ |
| 10 | Exercise — the Evidence Base | exercise | All 3 files on GitHub ✅ |
| 11 | Stress and the Body | stress | All 3 files on GitHub ✅ |
| 12 | Alcohol — What the Evidence Shows | alcohol | All 3 files on GitHub ✅ |
| 32 | Breast Awareness — What to Look For | breast-awareness | Visuals + teleprompter built ✅ — article HTML status unconfirmed |
| 33 | Testicular Awareness — What to Look For | testicular-awareness | All 3 files built May 2026 ✅ |

### Series C — Digestive Health (Articles 13–21)
Articles 13–20: all three files confirmed complete and on GitHub. Educational voice retrofit confirmed complete.
Article 21: all three files confirmed on GitHub ✅

| # | Title | Slug | Status |
|---|-------|------|--------|
| 13 | Acid Reflux and GORD | acid-reflux | All 3 files on GitHub ✅ |
| 14 | IBD — Crohn’s & Ulcerative Colitis | ibd | All 3 files on GitHub ✅ |
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
| 26 | Epilepsy — What It Is and How It’s Managed | epilepsy | All 3 files built April 2026 ✅ — on GitHub |

### Series E — Cancer (Articles 27–31) — ESTABLISHED APRIL 2026
Series colour: `#2A5A3A` (forest green). Dark variant: `#1A3A25`. **Note: initial proposed colour `#8A3A5A` (deep rose) was rejected — contrast issues. Forest green confirmed April 2026.**

| # | Title | Slug | Status |
|---|-------|------|--------|
| 27 | Breast Cancer | breast-cancer | All 3 files built April 2026 ✅ — on GitHub ✅ |
| 28 | Prostate Cancer | prostate-cancer | All 3 files built April 2026 ✅ — on GitHub ✅ |
| 29 | Lung Cancer | lung-cancer | All 3 files built April 2026 ✅ — on GitHub ✅ |
| 30 | Bowel (Colorectal) Cancer | bowel-cancer | All 3 files built April 2026 ✅ — on GitHub ✅ |
| 31 | Melanoma and Skin Cancer | melanoma | All 3 files built April 2026 ✅ — on GitHub ✅ |

**Total articles with all 3 files on GitHub: 33 (including Articles 32–33). All complete ✅.**

---

## 4. SITE FILES — CURRENT STATUS

| File | Status | Notes |
|------|--------|-------|
| index.html | Updated May 2026 | Stat cards updated to broader health audience; 774 lines |
| helf-school-conditions.html | Updated May 2026 | 33 articles live across 6 series |
| helf-school-membership.html | On GitHub | Pricing: £0 / £6pm or £60pa / £150 lifetime |

### helf-school-conditions.html — May 2026 update
Updated May 2026 to show all 33 articles live. Hero stat: 33 articles live.

### index.html — May 2026 update
Stat cards updated from cardiovascular-only to broader health audience:
1. Card 1: "1 in 2 people in the UK will receive a cancer diagnosis" (CRUK)
2. Card 2: "15M people in the UK living with at least one long-term health condition" (NHS England)
3. Cards 3–4 unchanged (3 min GP consultation / ∞ time on helf.school)

### index.html — April 2026 corrections (previously applied)
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

### Educational voice — practical guidance

**Describing what medicine knows:** "Clinically recognised as a time-sensitive condition — 111/urgent GP exists for this" rather than "Call 111 immediately."

**Describing what services exist:** "The NHS screening programme invites women aged 50–70" rather than "Ask your GP about breast screening."

**Describing shared decisions:** "NICE describes this as a decision to be made with full information about benefits and risks" rather than "Discuss this with your doctor."

**The distinction that matters:** helf.school tells readers what medicine knows. It never tells them what to do. The reader decides what to do with the information — that is the essence of empowerment.

---

## 6. VIDEO INTRO STANDARD (Segment 1, ~15–18 seconds)

Every video opens with this exact intro:

> "I’m Dr Paul — I spent over twenty years as an NHS GP before I retired in 2019. Today I want to talk to you about [TOPIC]. Now, I do have to say upfront — what I’m giving you here is health education, not medical advice. Anything personally relevant is a conversation for you to have with your GP or healthcare professional. Right — let’s get into it."

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

### Dr Paul’s preference
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
8. Research flags ❖ — for Dr Paul’s review before upload

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

### Visuals research card body = 2–3 sentences maximum — LOCKED APRIL 2026

**The ev-body of every research card in visuals files must contain no more than 2–3 sentences: (1) what was compared, (2) the headline finding, (3) one sentence of clinical context. No trial design detail, no population breakdown, no secondary endpoints. The full explanation is in the article. Viewers are lay people watching a video.**

**⛔ EV-BODY WORD LIMIT — LOCKED APRIL 2026:**
- **Two stacked ev-cards: ≤ 30 words** — the ev-det panel is ~441px wide at 768px filming viewport. At 1.05rem × 1.5 line-height, that gives 7–8 words/line × 4 lines = ~30 words max. Exceeding this clips the text mid-sentence on screen.
- **Single ev-card: ≤ 44 words** (more vertical height available, same width constraint)
- Run the ev-body QC script (in session-start-rules Rule 36) before presenting any visuals file with research cards.
- **Canonical failure:** cholesterol-visuals.html slides 7–9 — ev-body texts of 33–42 words all clipped. Caught by Dr Paul April 2026.

Canonical examples (lung-cancer-visuals.html, April 2026):
- NELSON: "The NELSON trial randomised 15,789 long-term smokers to CT screening or no screening. After 10 years, the screened group had 24% lower lung-cancer mortality. This is the evidence behind the NHS targeted screening programme now rolling out."
- KEYNOTE-024: "Pembrolizumab compared with chemotherapy. 10.3 months vs 6.0 months PFS. Overall survival also significantly better, with fewer serious side effects."
- FLAURA: "Osimertinib vs standard EGFR drugs. Median overall survival 38.6 months versus 31.8 months. Now the preferred first-line treatment for EGFR-mutated NSCLC."

### CTA slide = health-action "one thing" — LOCKED APRIL 2026

**The CTA slide (second-to-last slide in every visuals file) must function as a health-action moment — not a membership pitch. It identifies the single most actionable implication from the video content, framed in the descriptive educational voice. The membership pitch lives on the brand close slide only.**

Structure:
- Icon (large, thematic)
- Badge: "The evidence is clear on one thing" (or equivalent for the topic)
- Headline: the most important action-oriented finding from the video
- 4–5 rows: relevant health facts the viewer can act on (symptoms to know / screening / risk reduction / helf.school link)
- Medical disclaimer (canonical phrase)

**Educational voice requirement:** Every CTA row must describe what the evidence shows or what programmes exist — never instruct the viewer directly.

Canonical reference: `lung-cancer-visuals.html` slide 10 (April 2026).

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

**Canonical reference:** `lung-cancer.html` Article 29 research cards (April 2026).

**This applies equally to visuals ev-stat-boxes.**

### All stats require citations — in every location — LOCKED APRIL 2026

**Every numerical figure, percentage, or quantitative claim in any helf.school file requires an inline superscript citation — regardless of location.**

This applies universally to: body prose paragraphs, Key Terms box definitions, stat grid cards, research card stat boxes and body text, Putting it all together box, discussion cards, myth panel evidence text, visuals slide text, and teleprompter scripts. No stat goes uncited anywhere.

**Process before delivering any file:** scan every paragraph and every text element for numerical figures and percentages. Every one must have a superscript citation or be flagged ❖.

### Subtypes, stages, and formally named sets — always list, never inline prose — LOCKED APRIL 2026

**When article body prose introduces a formally numbered or named set of items using a phrase such as "three main subtypes", "four stages", "two types of", or "the following five", those items must be presented in a numbered or bulleted HTML list — never run together as a comma-separated sequence within a prose paragraph.**

**Implementation:** use `<ol class="subtype-list">` with the canonical CSS pattern first introduced in `lung-cancer.html` (Article 29, April 2026).

**Canonical reference:** `lung-cancer.html` Section 1 — NSCLC subtypes (adenocarcinoma, squamous cell carcinoma, large cell carcinoma) presented as a 3-item `<ol class="subtype-list">` (April 2026).

### Reference numbering — LOCKED APRIL 2026
References must display visible numbers. Use CSS `counter-reset` and `counter-increment` on `.ref-block` with a `::before` pseudo-element rendering the number to the left of the border. Canonical: `prostate-cancer.html`.

### Article research card display standard — LOCKED APRIL 2026

**Canonical reference: `memory-dementia.html` (layout) + `breast-cancer.html` + `prostate-cancer.html` (colour principle)**

```css
.research-card { grid-template-columns: 220px 1fr; border-radius: 10px; border: 1px solid rgba(series,0.18); }
.ev-stat-box {
  background: linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%);
  padding: 1.1rem .9rem; justify-content: flex-start; overflow: hidden;
}
.ev-kf-label { font-size: .72rem; font-weight: 700; color: var(--amber); text-transform: uppercase; letter-spacing: .07em; }
.ev-stat-row { font-size: 3.2rem; font-weight: 900; color: #fff; line-height: 1.0; }
.ev-outcome { font-size: .95rem; font-weight: 700; color: rgba(255,255,255,0.95); line-height: 1.3; }
.ev-conditions { font-size: .80rem; line-height: 1.35; color: rgba(255,255,255,0.72); }
.ev-body { background: #fff; padding: 1.1rem 1.2rem; }
.ev-body p { font-size: .93rem; line-height: 1.72; }
.ev-source { font-size: .78rem; color: rgba(44,44,44,0.55); font-style: italic; }
```

**Key rules:**
- **Stat box background: series-colour gradient** — each series uses its own dark-to-mid gradient, never plain navy.
- **ev-stat-row: 3.2rem weight 900** — the headline stat must dominate the stat box.
- **ev-kf-label: always amber `#E8A84A`** — consistent accent across all series.
- **Column: 220px** — confirmed from memory-dementia canonical.

Every `.stat-prose` line in the Why does it matter? stat grid must carry a superscript inline citation. Run `grep -A 3 "stat-prose"` before presenting any article and confirm every instance has a `ref-` link.

### Research card stat standard

**The stat box must convey the clinically important and relevant finding — not statistical machinery.**

**The complete clinical conclusion rule — LOCKED APRIL 2026:**

Every research card stat box must state the complete clinical finding in terms that are immediately meaningful to a lay reader. The stat box must answer:
1. **WHAT** was studied or found
2. **WHAT** the finding means for someone with that condition
3. Enough context for the finding to stand alone without the body text

**The test:** Can a lay reader understand the clinical finding from the stat box alone, without reading the body text? If not, rewrite.

**Correct examples — complete clinical conclusions:**
- "The Epley manoeuvre / is a safe & effective treatment for BPPV"
- "77% response rate / vs 44% placebo"
- "Macrogol superior / to lactulose across all outcomes"
- "20% reduction in breast cancer mortality / in women invited to screening"
- "~⅓ reduction in breast cancer mortality / throughout first 15 years in ER-positive disease"
- "2.7% / prostate cancer-specific mortality at 15 years / similar across monitoring, surgery, and radiotherapy"
- "81 months / median overall survival — docetaxel + hormone therapy / vs 71 months alone"

**Stat boxes show outcomes only — effect sizes, risk changes, response rates, or complete qualitative clinical conclusions. NEVER:**
- Participant counts ("868 participants", "2,441 participants")
- Study counts ("10 RCTs", "39 studies")
- Cost figures ("£113m", "£2.3bn")
- Incomplete qualifiers

### Full references standard
- Full citation block: authors · title · journal · year · vol · pages · DOI
- Pill links: journal DOI and PubMed — verified by web search in same session only
- Reference block `border-left` colour matches series accent
- Inline citations (superscripts) must link to corresponding `id="ref-N"` anchor

### Research flags ❖
- Unverified claims flagged ❖ for Dr Paul’s review
- Pre-draft rule: before building any article HTML, verify every cited study
- Never include an unverified link in a delivered file


### Accessibility and body text rules (all articles)

**Body text colour:** All body text must be `#2C2C2C` with explicit `font-weight:400`.

**Pale colours not permitted:** `#374151`, `#4B5563`, `#555` are not permitted anywhere in articles. These appear grey enough to read on a monitor but are too pale for accessibility standards.

**No opacity:0 or fadeUp animations on article body sections:** Content must be immediately visible on page load. Animations are only permitted on: decorative elements, stat counter animations, and explicitly interactive components.

**Font weight 300 is banned:** DM Sans weight 300 is never used anywhere. Minimum body weight is 400.

### Structural decisions for Digestive and Neurological articles

**Digestive articles:** Default Key Terms box (navy) and Putting it all together box (navy). Series colour gradient NOT applied — that is Cancer Series only unless a future decision extends it.

**Neurological articles:** Same as Digestive — navy Key Terms and Putting it all together boxes. Series gradient not applied.

**Cancer articles:** Series gradient applied to Key Terms box, Putting it all together box, AND research card stat boxes. All three confirmed locked April 2026.

### NICE guideline number rule (applies everywhere)

Before citing any NICE guideline, always verify via web search in the same session:
1. Is the guideline CG or NG?
2. What is the exact number?
3. Does the guideline cover the correct condition?
4. Is this the adult version or children’s?

Common errors caught:
- NICE CG99: covers constipation in **children and young people only** — NOT adults
- NICE NG150 vs CG150: migraine guidance is CG150 (not NG150) — caught April 2026
- NICE NG217: epilepsy in children, young people AND adults — covers all ages

### Research card display — white background on right panel (articles)

The right panel of the research card in articles uses a white background (`background: #fff`) with dark text (`color: var(--text)` = `#2C2C2C`). This is intentional and correct — the white panel creates contrast against the series-coloured stat box. Never change the right panel to a dark background.

### Complete clinical conclusion test — application

The test has two parts:
1. **The stat box test:** Read only the ev-kf-label + ev-stat-row + ev-outcome + ev-conditions. Can a lay reader understand what was found? If not, the stat box fails.
2. **The body text test:** Read only the ev-body/ev-body-panel. Does it explain WHY this matters to someone with this condition, in plain English? If not, the body fails.

Both must pass before the card can be delivered. Statistical machinery in the stat box (OR values, RCT counts, hazard ratios as the headline finding) always fails part 1.

### Teleprompter length enforcement

Target: 600–750 words at ~150 wpm = 4–5 minutes. Process:
1. Write first draft
2. Run word count: `wc -w [file]` or estimate from line count (× ~8 words/line on script text)
3. If over 750 words: identify the longest segment and cut 30–40 words from it
4. If under 600 words: identify which of the three questions (what is it / does it affect me / what can be done) is underweight and expand it

The most common over-length failure: Segment 5 (research) runs long because trial details are included. Cut all trial design description — name + stat + one sentence meaning only.
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
**The general rule:** Every medical or clinical term that a lay reader would not immediately understand must have a plain English definition in brackets on first use in each section.

Examples of terms requiring lay clarification:
- Anatomical: periorbital (around the eye) · temporal (at the temple) · ipsilateral (same side) · bilateral (both sides)
- Symptoms: lacrimation (tearing) · rhinorrhoea (runny nose) · ptosis (drooping eyelid) · miosis (pupil constriction) · conjunctival redness (redness of the white of the eye)
- Clinical: teratogenic (capable of causing harm to a developing foetus) · hepatotoxic (toxic to the liver) · tachycardia (fast heart rate)
- Drug classes: tricyclic antidepressant · beta-blocker · prokinetic antiemetic · aromatase inhibitor · selective oestrogen receptor modulator

**Statistical measures** (also require lay clarification on first use per section):
- HR (hazard ratio — HR 1.23 = 23% higher risk)
- RR (relative risk)
- OR (odds ratio)
- SMD (standardised mean difference — effect size)
- NNT (number needed to treat)
- CI (confidence interval)
- PAR (population-attributable risk)

### Inline lay definitions — safety-critical and Key Terms box terms
**Rule 1 — Safety-critical terms:** Any clinical term that carries significant implications for the reader must always have an **inline lay definition** in the same sentence where the term first appears. A Key Terms box entry alone is not sufficient.

**Rule 2 — Structured lists and criteria boxes:** When a medical term that appears in the Key Terms box also appears in a structured list or diagnostic criteria box — add **(see Key Terms below)** immediately after the term.

### Cite the paper’s exact numerical expression — never convert or paraphrase — LOCKED APRIL 2026
When a paper reports a statistic, use its exact wording and numerical form in every location it appears. Never convert between forms — do not turn ">30%" into "1 in 3", "33%", or "around a third"; do not turn "1 in 1,000" into "0.1%". The conversion introduces inaccuracy and misrepresents the source.

---



---

## VISIBILITY MINIMUMS (apply to all files — never go below these)

**Source attributions:**
- Minimum 0.75rem; `rgba(255,255,255,0.55)` on dark / `#2C2C2C` on light
- `.source-tag` style at `rgba(255,255,255,0.25)` not permitted

**Key Terms box:**
- Header: minimum 1.05rem, `#fff`
- Term labels: minimum 0.88rem, weight 700
- Definition text: minimum 0.92rem, `rgba(255,255,255,0.90)` — opacity 0.75 or 0.80 not permitted

**Animation/diagram text:**
- Labels: minimum 13px, `rgba(255,255,255,0.80)`
- SVG annotations: minimum 10px, `rgba(255,255,255,0.60)` — opacity 0.50 or below not permitted

**Presenter topbar:**
- Subtitle: minimum 0.75rem, `rgba(255,255,255,0.75)`
- Slide counter: minimum 0.85rem, `rgba(255,255,255,0.90)`
- Keyboard hint: minimum `rgba(255,255,255,0.60)` — values 0.35 or below not permitted

**Hero subtitle:** minimum `rgba(255,255,255,0.85)`
**Hero meta items:** minimum `rgba(255,255,255,0.80)`
**Hero breadcrumb:** minimum `rgba(255,255,255,0.75)` — values 0.60 or below not permitted

**Presenter intro/closing slides:**
- Taglines + series label: minimum `rgba(255,255,255,0.70)`
- Logo dot: minimum `rgba(255,255,255,0.60)`
- Stat card label: `rgba(255,255,255,0.90)`
- Stat source: 0.75rem, `rgba(255,255,255,0.65)`

**Screen file footer:** minimum `clamp(.65rem,1vw,.80rem)`, `rgba(255,255,255,0.65)`

These thresholds were established after multiple files were delivered with text too pale to read on screen. Enforcement is Claude's responsibility during the pre-output audit.

---

## 9. VISUALS HTML STANDARDS

### CONFIRMED CANONICAL VISUALS REFERENCE — bowel-cancer-visuals.html (April 2026)

**`bowel-cancer-visuals.html` is the first visuals file that was delivered with zero changes required. It is the confirmed canonical reference for all future visuals builds.**

Dr Paul’s confirmation (April 2026): *"Good — you have applied those well and for the first time I don’t have to change anything in visuals html."*

---

### VISUALS PRE-BUILD CHECKLIST — MANDATORY BEFORE WRITING ANY VISUALS HTML

Before writing a single line of a new visuals HTML file, confirm these foundational decisions are in place.

**1. SLIDE POSITIONING — use explicit width/height, NOT inset:0**
```css
.slide {
  position:absolute;
  top:0; left:0; width:100%; height:100%;
  display:flex; flex-direction:column;
  opacity:0; visibility:hidden; pointer-events:none;
  transition:opacity .32s ease;
}
.slide.active { opacity:1; visibility:visible; pointer-events:all; }
```

**2. INTRO SLIDE — no space-between, stat grid with grid-template-rows:1fr**
```css
.intro-slide { padding:1rem 1.5rem .8rem; gap:.6rem; }
.intro-stat-grid {
  display:grid; grid-template-columns:1fr 1fr 1fr;
  grid-template-rows:1fr;
  gap:.65rem; flex:1; min-height:0;
}
.intro-stat-card { display:flex; flex-direction:column; justify-content:center; min-height:0; }
```

**3. ALL SIZES AT MAXIMUM FROM LINE ONE**
```
slide-title: 1.72rem · ic-icon: 1.55rem · ic-title: 1.12rem · ic-body: .93rem
ev-body p: .94rem · three-grid gap: .46rem · slide-header margin-bottom: .4rem
info-card padding: .82rem 1rem · ic-body line-clamp: 5 · ev-body line-clamp: 7
```

**4. ev-outcome MUST CARRY THE REASON — not just the finding**

**5. MONTHS SPELLED IN FULL — ev-stat-unit class**
```html
<div class="ev-stat-row">16.5</div>
<div class="ev-stat-unit">months</div>
```
`.ev-stat-unit { font-family:'Fraunces',serif; font-size:1.65rem; font-weight:700; color:rgba(255,255,255,0.88); line-height:1; margin-bottom:.25rem; }`

**6. RESEARCH CARD EV-BODY = 2–3 SENTENCES MAXIMUM in visuals**

**7. CTA SLIDE = HEALTH-ACTION "ONE THING" — not a membership pitch**
- Membership pitch lives on the brand close slide only
- CTA: maximum 5 action rows — `grid-template-rows: repeat(5,1fr)` — LOCKED MAY 2026
- All rows descriptive — never instructional
- Canonical reference: `lung-cancer-visuals.html` slide 10 (April 2026)

**8. NO RESEARCH OLDER THAN 12 YEARS**
Check every trial year before writing. Current year 2026 → nothing before 2014.
If a trial is borderline, search for its publication date before including it.

**9. EDUCATIONAL VOICE — pre-check before saving**
- 0 instances of: "speak to your GP", "you should", "seek help", "call 999/111"
- Canonical phrase × 2: CTA slide disclaimer + brand close disclaimer
- Both must be at `font-size:1rem`

**10. INTRO STAT CARDS — 3 cards, each with amber number + contextual label**
The label must be a full sentence explaining what the number means, not just a unit abbreviation. Example: "new cases per year in the UK — nearly 140 every day" not just "cases/year".

**11. INFO CARD BODY TEXT — TWO-TIER WORD LIMIT — LOCKED APRIL 2026**

Every `.ic-body` in a three-grid slide must observe these hard limits:

- **Cards WITHOUT `.ic-source`:** ≤34 words maximum
- **Cards WITH `.ic-source`:** ≤23 words maximum — the source line occupies one full row, reducing visible body space from 5 lines to 4

**The rule:** write the key fact (sentence 1), then one tight sentence of context (sentence 2). No long parenthetical clauses, multiple qualifying phrases, or three-sentence content.

**Verification before delivery:** run a word count on every `.ic-body`. Cards with source must be ≤23w. Cards without source must be ≤34w. Do not deliver if any card exceeds its limit.

**Canonical failure:** `lung-cancer-visuals.html` April 2026, slides 4–7 — cards ran 27–35 words with source lines present, causing visible mid-sentence clipping across four slides. Required multiple rebuilds to resolve. Root cause: source line was not accounted for in the word count target.

### VIEWPORT MAXIMISATION — MANDATORY RULE (LOCKED APRIL 2026)

**Every visuals slide must fill the available viewport. This is non-negotiable.**

**Required minimums/maximums — apply to every slide:**
- Slide padding: maximum `1rem 1.5rem 0.8rem`
- Slide header margin-bottom: `.4rem`
- Slide title: minimum `1.72rem`
- Slide subtitle margin-bottom: maximum `.4rem`
- All body text in cards and rows: minimum `.93rem`
- Card/row gaps: maximum `.48rem`
- Card padding: `.82rem 1rem`
- Info/step row body line clamp: minimum 5 lines
- Ev-body paragraph: minimum `.94rem`, line clamp minimum 7 lines
- Card icons: minimum `1.55rem`
- Card titles: minimum `1.12rem`

**CTA slide — confirmed working sizes (April 2026):**
- Central icon: `5.5rem`
- Headline: `clamp(2.8rem, 5.5vw, 4.2rem)`
- Italic subline: `1.2rem`
- Card emoji icons: `2.2rem`
- Card title text: `.96rem`

**Closing slide — confirmed working sizes (April 2026):**
- Logo: `2.8rem`
- Tagline: `1.05rem`
- Link/series label: `1rem`

**The test before delivering any visuals file:** content must fill at least 85% of the visible area.

### 3-CARD RULE — NEVER SHRINK TEXT TO FIT — LOCKED APRIL 2026

**When a slide contains 6 cards, always split into two slides of 3 cards each. Never reduce font size or line clamp to make 6 cards fit.**

**Canonical reference for 3-card layout:** `prostate-cancer-visuals.html` (slides 3–10).

### Layout
- **3-card slides: `three-grid` class** — `grid-template-rows: repeat(3, 1fr); gap: .55rem`
- **6-card slides are FORBIDDEN** — always split to 3+3
- Stats: 2.5–3.6rem font size
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

### Animation
- `animate-ready` class on all animated cards — **never** hardcoded `opacity:0` in final delivered files

### ev-stat-box — EXACT SPECIFICATION (locked April 2026)

```css
.ev-stat-box { padding: .9rem .75rem; overflow: hidden; }
.ev-kf-label { margin-bottom: .35rem; }
.ev-stat-row { margin-bottom: .3rem; }
.ev-conditions { font-size: .78rem; line-height: 1.32; }
```

- `.ev-conditions` text must be short enough to fit 220px
- Do NOT increase padding on `.ev-stat-box`
- Do NOT use `.ev-conditions` font size above `.78rem`

### CTA slide standard — LOCKED APRIL 2026 — canonical: `prostate-cancer-visuals.html` slide 13
- **`cta-wrap-v2` class with `grid-template-rows: auto 1fr auto`** — ONLY correct layout
- Full-screen with radial gold-glow background + pulsing icon halo (3.2s drop-shadow)
- **Central icon: minimum `5.5rem`**
- **Fraunces headline: minimum `clamp(2.8rem, 5.5vw, 4.2rem)`**
- **No subline mentioning "free at helf.school"** — LOCKED APRIL 2026
- **Max 5 action rows** — LOCKED MAY 2026. `grid-template-rows: repeat(5,1fr)` or fewer
- **`med-disclaimer` at bottom — `font-size:1rem` on `.med-disc-text`**
- **`cta-glow` radial gradient overlay**
- Reference: `prostate-cancer-visuals.html` slide 13

### Closing slide standard — NEW STANDARD LOCKED APRIL 2026 — canonical: `prostate-cancer-visuals.html` slide 14

**Structure:**
- `close-wrap` with `justify-content: flex-start` — **NEVER `justify-content: center`**
- **helf.school logo** — large Fraunces, with coral dot
- **"Health Education" tagline** — uppercase
- **Brand headline** — e.g. "Evidence-based. Built by a doctor."
- **Three brand pitch cards:**
  1. 📚 Article count and series breadth — **always update to current article count (33 as of May 2026)**
  2. 🩺 Dr Paul’s credentials — "retired NHS GP with over 20 years of experience"
  3. 🔓 Start for free — Explorer tier
- **`med-disclaimer`** at `font-size:1rem`
- **Series label** — e.g. "Cancer Series · Article 28 · Prostate Cancer"

**`justify-content: flex-start` is mandatory** — `center` clips the logo at the top.

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
- `.source-tag` style at `rgba(255,255,255,0.25)` not permitted

**Presenter intro and closing slides:**
- Taglines + series label: minimum `rgba(255,255,255,0.70)`
- Logo dot: minimum `rgba(255,255,255,0.60)`
- Stat card label: `rgba(255,255,255,0.90)`
- Stat source: 0.75rem, `rgba(255,255,255,0.65)`

---

### SERIES BACKGROUND COLOUR STANDARD — VISUALS — LOCKED APRIL 2026

| Series | Base colour | Slide background | Slide bg hex |
|---|---|---|---|
| Cancer | Forest green `#2A5A3A` | Deep forest green | `#0e2418` |
| Cardiovascular | Crimson `#C8423A` | Dark crimson | `#1a0808` |
| Neurological | Purple `#6B5EA8` | Dark purple | `#0f0d1a` |
| Digestive | Amber `#D47C3A` | Dark amber | `#1a0e08` |
| Fatigue | Teal `#3A8A7A` | Dark teal | `#081a14` |
| Practical Health | Olive `#7A6A2E` | Dark olive | `#120e08` |

**Cancer Series confirmed:** `#0e2418` — applied to `breast-cancer-visuals.html` and `prostate-cancer-visuals.html` April 2026.

**Retrofit instruction:** When any visuals file is opened, check the background. If it uses `#050f08`, `#060e08`, or any other near-black value, replace with the correct series dark colour from the table above.

**Gradient cards within slides** (info cards, stat cards) should use the series dark colour family at both ends of the gradient — they must NOT fade to near-black. Example for Cancer Series:
```css
.c-red  { background: linear-gradient(90deg, rgba(180,45,45,.55) 0%, rgba(110,25,25,.42) 100%); }
.c-amber{ background: linear-gradient(90deg, rgba(170,110,20,.55) 0%, rgba(110,68,12,.42) 100%); }
.c-green{ background: linear-gradient(90deg, rgba(38,105,55,.55) 0%, rgba(22,65,33,.42) 100%); }
```

---

### LAY IMPACT FIRST — VISUALS AND TELEPROMPTER STANDARD — LOCKED APRIL 2026

The visuals and teleprompter are the doorway — not the textbook. Three questions they must answer for the lay viewer: What is this condition? Does it affect me? Is there anything I can do about it?

#### VISUALS — Colour narrative (mandatory from Article 31 onwards)

- **Red cards** — risk, harm, danger, mortality figures
- **Amber cards** — mechanism, process, how something works, gene/molecular information
- **Green cards** — positive outcomes, action, survival figures, what treatment achieves

#### VISUALS — Hero stat layout

When a slide has a dominant headline figure, use the hero stat layout: one large stat card spanning the full height of one column (`grid-row: span 2`), with two smaller stat cards stacked in the adjacent column.

**Canonical example:** `melanoma-visuals.html` slide 5.

#### VISUALS — Sequential animation for formal lists

When the article contains a formally introduced set of items (ABCDE, stages, types, criteria), a sequential reveal is more engaging than showing everything at once.

**Canonical example:** `melanoma-visuals.html` slide 3 — ABCDE rule with 5-item sequential reveal.

#### VISUALS — No drug names

Drug generic names and brand names must not appear in visuals slides. Describe treatments by class only:
- ✅ "immunotherapy" · "gene-targeted treatment" · "checkpoint inhibitor" · "targeted therapy"
- ❌ pembrolizumab · nivolumab · ipilimumab · dabrafenib · Keytruda · Opdivo

#### VISUALS — Trial names: lean and stat-focused

Trial names may be used in research card titles and ev-conditions. The ev-body describes the finding in plain English.

#### TELEPROMPTER — No drug names

The same no-drug-names rule applies to teleprompter scripts. Describe treatments by what they do.

#### TELEPROMPTER — Trial names: name, stat, meaning only

Format: name of trial → headline stat → one plain sentence of what it means. Nothing else.

#### TELEPROMPTER — Three questions standard

Every teleprompter must answer:
1. **What is this?**
2. **Does it affect me?**
3. **Is there anything I can do?**

#### RETROFIT — apply when any visuals or teleprompter file is next opened

When any existing visuals file is opened for any reason, apply:
1. Colour narrative — replace uniform card colours with red/amber/green by content type
2. Check for drug names — replace with class descriptions
3. Check trial ev-body — reduce to 2–3 sentences max, remove trial design detail
4. Consider whether any formal list on a slide would benefit from sequential animation

When any existing teleprompter is opened for any reason, apply:
1. Remove drug generic and brand names — replace with class descriptions
2. Check trial references — reduce to name + stat + one plain sentence
3. Verify the three-question structure is present

**Priority articles for colour narrative retrofit (highest visual impact):**
- Cardiovascular series (01–07) — heavy treatment content benefits most from red/amber/green differentiation
- Cancer series (27–30) — already partially correct in newer builds; apply full colour narrative on next open

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
Prior teleprompter files built before this standard was confirmed may require retrofitting.

### Cue box — paired slides — CONFIRMED APRIL 2026
When two slides share a segment, the cue box label reads the slide range: e.g. `Slides 3–4 — What is prostate cancer?`.

### Video length standard
- Maximum 4–5 minutes
- Word count: approximately 600–750 words at ~150 words per minute
- Cut ruthlessly

### Teleprompter content standard
Each teleprompter must deliver:
1. Fundamental messages stated clearly
2. Key statistics with exact numbers — no rounding drift from the article figures
3. Specific practical pointers

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

---

## 12. QC CHECKLIST (run before every upload)

1. Readability — no pale text below colour minimums
2. References — full citation blocks with DOI; pill links verified in same session
3. Research flags ❖ — all claims verified
4. Graphics — standalone animation file exists; presenter has matching inline visual
5. Article ↔ presenter consistency — all facts, study names, years, citations match exactly
6. Educational voice — no forbidden phrases; canonical phrase correct and in full throughout
7. Drug names — brand names in brackets after all generics
8. **Lay-clarification — ALL medical terminology in brackets on first use per section**
9. **Research card clinical conclusions — complete clinical conclusion test (LOCKED APRIL 2026)**
10. Research card stats — outcomes only; never participant/study counts
11. CTA slide — `cta-wrap-v2` with `grid-template-rows: auto 1fr auto`; `med-disc-text` at `font-size:1rem`; **max 5 rows (LOCKED MAY 2026)**
12. Closing slide — brand close structure; `justify-content: flex-start`; three pitch cards; **article count current (33 as of May 2026)**
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
23. **EXACT FIGURE RULE — paper’s exact numerical expression everywhere**
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
38. **CTA MAX 5 ROWS — LOCKED MAY 2026**

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

**NOT approved:** Epilepsy Action · Alzheimer’s Society · WCRF · Breast Cancer Now · any charity or advocacy website.

**WCRF specifically:** Must NOT be cited as Cancer Research UK figures. Always fetch Cancer Research UK statistics page directly.

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

Never include an unverified link. Never cite NICE CG99 for adult constipation. The correct adult reference is NICE CKS at `cks.nice.org.uk/constipation`.

**NICE guideline number rule:** Always verify the exact NICE guideline number — including whether it is CG or NG — via web search before citing.

---

## 17. RETROFIT STATUS (retroactive standards across existing articles)

### Confirmed complete
- Educational voice: confirmed complete across Articles 01–26 (as built)
- Article HTML retrofits (Articles 13–18): confirmed complete
- **Cancer Series visuals + teleprompters (Articles 27–31) — ALL COMPLETE April 2026 ✅**
  - breast-cancer-visuals + teleprompter ✅
  - prostate-cancer-visuals + teleprompter ✅
  - lung-cancer-visuals + teleprompter ✅ (877-line retrofit, 33 articles, May 2026)
  - bowel-cancer-visuals + teleprompter ✅
  - melanoma-visuals + teleprompter ✅
- **Cardiovascular Series visuals + teleprompters (Articles 01–07) — ALL COMPLETE April 2026 ✅**
  - cholesterol-visuals.html: ev-cards retrofitted to canonical ev-stat-row pattern, CTA 5 rows, brand close 33 articles — May 2026 ✅
  - CTA sequential animation applied ✅
  - Brand close pitch cards applied ✅
  - `display:-webkit-box` fixed on all body elements ✅
  - 5-card and 6-card slides split to max 3 cards per slide ✅
  - ev-card padding reduced to 1.1rem, ev-body clamp:4 ✅
  - Teleprompter slide numbers updated to match ✅
- **Practical Health Series visuals + teleprompters (Articles 08–12) — ALL COMPLETE April 2026 ✅**
  - lifestyle-visuals.html: 13 slides (3 cards per slide max), CTA 5 rows, brand close 33 articles — May 2026 ✅
  - lifestyle-teleprompter.html: 235-line version correct (matches 13-slide visuals) ✅
  - ev-stage display:flex enforced (Rule 37) ✅
- **coeliac-disease-visuals.html** — brand close updated 31→33 May 2026 ✅
- **Digestive Series visuals (Articles 13–21) — structural retrofit COMPLETE May 2026 ✅**
  - ev-stage display:flex ✅ · cta-wrap-v2 ✅ · close-wrap flex-start ✅ · animate-ready ✅ · series gradient stat box ✅ · 3-card splits ✅
  - **Brand close count outstanding: still reads "31 articles / 5 series" — needs 33 / 6 series ❖**
- **Neurological Series visuals (Articles 22–26) — structural retrofit COMPLETE May 2026 ✅**
  - ev-stage display:flex ✅ · cta-wrap-v2 ✅ · close-wrap flex-start ✅ · animate-ready ✅ · colour narrative ✅
  - **Brand close count outstanding: still reads "31 articles" — needs 33 ❖**


### Retrofit checklist — when any visuals file is opened

Apply this full checklist in sequence when opening any visuals file for any reason:

**Step 1 — Slide structure check**
- Count cards per slide. Any slide with 5+ cards: split to 3+3 immediately.
- Check ev-stage: must be `display:flex`, never `display:grid`.
- Check slide backgrounds: replace near-black with correct series dark colour.

**Step 2 — Card body text check**
- Every `.ic-body` with `.ic-source`: ≤23 words. Every `.ic-body` without: ≤34 words.
- Every `.ev-body` with two stacked cards: ≤30 words.
- All body elements must have `display:-webkit-box` AND `-webkit-line-clamp:4`.

**Step 3 — Research card check**
- ev-stat-box: `padding:.9rem .75rem`, `overflow:hidden`, `.ev-conditions` at `.78rem`.
- ev-outcome must contain both the finding AND the reason/comparison.
- ev-kf-label: amber `#E8A84A`.
- ev-stat-row: 3.2rem weight 900.

**Step 4 — CTA slide check**
- `cta-wrap-v2` with `grid-template-rows: auto 1fr auto`.
- Maximum 5 action rows. No "free at helf.school" in subline.
- `med-disc-text` at `font-size:1rem`.
- Radial gold-glow background + pulsing icon halo.

**Step 5 — Brand close check**
- `justify-content: flex-start`.
- Three pitch cards: article count (33 as of May 2026), Dr Paul credentials, free tier.
- `med-disc-text` at `font-size:1rem`.
- No stat repeat — brand close is NOT a repeat of the CTA research stats.

**Step 6 — Content check**
- No drug generic or brand names in any slide. Replace with class descriptions.
- No research older than 12 years (pre-2014). Replace or remove.
- Colour narrative: red=harm, amber=mechanism, green=action. Apply to all info cards.

**Step 7 — Educational voice check**
- 0 instances of forbidden phrases.
- Canonical phrase present in CTA disclaimer AND brand close disclaimer.
- Both at `font-size:1rem`.

**Step 8 — Teleprompter consistency**
After any visuals retrofit, review the matching teleprompter slide-by-slide before upload.
Any segment whose slide content changed must be rewritten to match.
### Outstanding — to confirm and apply
- **Brand close "31 articles / 5 series" → "33 articles / 6 series": outstanding across Digestive (13–21) and Neurological (22–26) visuals — being fixed May 2026 ❖**
- **Epilepsy-visuals.html brand close: confirmed still shows "31 articles" — included in batch fix above ❖**
- Research card stat standard (outcomes only, not counts): outstanding across 01–11
- **Research card complete clinical conclusion standard: outstanding across 01–23**
- Inline citations (superscripts): outstanding across 01–11
- **Stat grid citations: outstanding across all articles built before April 2026**
- Visuals layout standard (3-card split): outstanding across 01–11
- Key terms / hero visibility standards: outstanding across 01–11
- Teleprompter cue box standard: confirm per-file which were built before standard was set
- **Subtype list formatting: outstanding across all articles**
- **Colour narrative retrofit: outstanding across Cardiovascular (01–07) visuals** — Digestive and Neurological confirmed complete May 2026

### Article byline and author card retrofit — ALL 33 articles — added May 2026
Google's E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness) standard for health content requires author credentials to be visible on every page where a visitor lands from search. The index.html About Dr Paul section covers the homepage only — individual article pages (where Google sends search traffic) currently show no credentials.

**Two additions required on every article HTML file:**

1. **Byline in article hero** — directly under the article title, alongside existing meta items:
   `Dr Paul · Retired NHS GP · 20+ years NHS experience`
   Links to `index.html#about-dr-paul`. One line of HTML.

2. **Author card** — small block before the References section, after Putting It All Together:
   > **About the author** — Dr Paul spent over twenty years as an NHS GP before retiring in 2019. helf.school exists to give every person access to clear, honest, evidence-based health education.
   Links to `index.html#about-dr-paul`.

**Apply to:** all 33 articles when next opened for any edit. Build into standard article template for all future articles from this point forward.

**Footer credential line** — every page footer should carry:
`helf.school is written by Dr Paul, a retired NHS GP with over 20 years of clinical experience. All content is health education, not medical advice.`

---

## 18. KEY LEARNING POINTS (accumulated)

### Google indexing and SEO — May 2026
Google indexes pages via crawlers that read publicly visible content. Gated content (behind login) is not indexed. The partial preview model (Option 3) ensures all 33+ articles are indexed — Google reads the free first section of every article. SEO (Search Engine Optimisation) improves ranking through: relevant plain-English content matching search queries, consistent publishing (freshness signal), and backlinks from credible sources. helf.school's consistent article structure and plain-English writing are already well-suited to organic search discovery.

### E-E-A-T standard for health content — May 2026
Google applies a higher standard to health and medical content — called E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness). Pages without visible author credentials rank lower for health queries. Dr Paul's NHS GP background is a genuine competitive advantage that must be surfaced on every article page, not just the homepage. Required on every article: byline in hero + author card before references + footer credential line. See Section 17 for full retrofit spec.

### Dr Paul's available hours — May 2026
12 hours per week. Constrains content output to: one article per week (full production ~7–8 hours) + fortnightly newsletter (~2–3 hours). Forum dropped — no hours available for moderation.
NICE CG99 covers constipation in **children and young people only**. Adult constipation: **NICE CKS** at `cks.nice.org.uk/constipation`.

### Dr Paul’s experience is 20+ years, not 30+
All references must read "20+ years" or "over twenty years as an NHS GP".

### Local link testing — expected not to work
When Dr Paul opens a downloaded HTML file locally and clicks article links, they appear broken. Expected — links are relative and work on the live GitHub site.

### Dr Paul prefers Claude to handle all file edits
Never ask Dr Paul to make manual edits. Claude fetches, applies all changes, delivers the corrected file for download.

### Conditions page — always rebuild, never patch
When helf-school-conditions.html needs significant changes, rebuild from scratch.

### Educational voice — systemic issue in older files
When fetching any older file for any purpose, audit for forbidden phrases and correct them as part of the work.

### Teleprompter cue box — advance THEN read
The cue box precedes the script for its segment. Dr Paul advances the slide first, then reads. Label: `▶ ADVANCE NOW — then read`.

### Large file writing — use create_file not bash
For HTML files over ~400 lines, `create_file` is the correct tool.

### Constipation article — April 2026 research decisions
- NICE CG99 explicitly excluded (children only)
- Rome IV criteria used as the clinical framework
- Laxative stepwise shown as 4 numbered steps with all brand names included
- Toileting position (footstool) included — evidence-based, often overlooked practical point
- Research card 1: macrogol vs lactulose (Cochrane 2010, CD007570)
- Research card 2: fibre supplementation response rate 77% vs 44% (Christodoulides 2016)

### Secondary source cited instead of primary — April 2026
In headaches article, Reference 5 was a consensus document, not the actual case-control study. Step 3 of pre-draft verification now explicitly requires confirming the specific stat is in the specific paper.

### Lay-clarification rule broadened — April 2026
Every medical or clinical term a lay reader would not immediately understand requires a plain English definition in brackets on first use in each section.

### Safety-critical terms need inline lay definitions — April 2026
Inline lay definition in same sentence, not just a Key Terms entry.

### NICE guideline number verification — CG vs NG — LOCKED APRIL 2026
Always verify via web search in the same session. In April 2026, migraine.html delivered citing NICE NG150 (incorrect) instead of NICE CG150 (correct).

### Visuals must maximise viewport space — LOCKED APRIL 2026
Content must fill at least 85%.

### ev-stat-box text overflow — confirmed fix April 2026
`.ev-stat-box` `padding:.9rem .75rem` + `overflow:hidden`; `.ev-conditions` `font-size:.78rem; line-height:1.32`.

### Research card stat boxes must state complete clinical conclusions — LOCKED APRIL 2026
**This is a health education site, not a statistics journal.** The test: read the stat box alone. Does a lay reader understand what the research found about their condition? If not, rewrite.

### PMIDs must be verified by web search every time — LOCKED APRIL 2026
Claude has repeatedly generated plausible-sounding but incorrect PMIDs. In April 2026, PMID 25088348 was included for Thurman et al Epilepsia 2014 — the correct PMID is 24903551. Mandatory process: search for the paper by author, title, journal, year; find a PubMed URL in the search results; include only that PMID.

### Charity and advocacy websites are not approved sources — LOCKED APRIL 2026
Epilepsy Action, Alzheimer’s Society, Alzheimer’s Research UK, WCRF, Breast Cancer Now, and similar organisations are not in the approved source list.

### Causal attributions require primary citations — April 2026
Causal claims require a specific primary citation. Inference from context is not sufficient.

### NEAD — use neutral language — April 2026
Non-epileptic attack disorder (NEAD) should not be described as "typically a manifestation of psychological distress." Use neutral language: "episodes that resemble seizures but are not caused by abnormal electrical activity in the brain."

### Drug-resistant epilepsy — cite the paper’s exact figure — April 2026
Kwan & Brodie NEJM 2000 reports "more than 30 percent" — not "1 in 3" or "33%".

### Exact figure rule — never convert between numerical forms — LOCKED APRIL 2026
When a paper reports a statistic, use its exact numerical expression everywhere.

### Stat grid cards require inline citations — LOCKED APRIL 2026
Every `.stat-prose` line in the Why does it matter? stat grid must carry a superscript inline citation. In the breast cancer article (Article 27, April 2026), three of four stat grid cards were presented without citations. Caught by Dr Paul.

### Approved source retrieval — fetch from the approved source page directly — LOCKED APRIL 2026
A figure found on an unapproved page that attributes its data to an approved source must NOT be used. Fetch the approved source page directly.

### Cancer Series colour changed from rose to forest green — April 2026
Initial colour `#8A3A5A` (deep rose) rejected — contrast issues. Changed to `#2A5A3A` (forest green) with dark variant `#1A3A25`.

### Research card stat boxes use series colour, not navy — LOCKED APRIL 2026
The ev-stat-box background in article research cards must use the series colour gradient (series-dark to series), not plain navy.

### Closing slide disclaimer must use .closing-disclaimer class at 1rem — LOCKED APRIL 2026
The closing slide disclaimer must use `font-size:1rem`.

### Cancer Series — three elements use series green, not navy — LOCKED APRIL 2026
Key Terms box · Putting it all together box · Research card stat boxes all use series gradient.

### CTA slide must not reference "free at helf.school" — LOCKED APRIL 2026
helf.school is a subscription service. "Start for free" is permitted as a card label. Caught by Dr Paul reviewing breast-cancer-visuals.html in April 2026.

### CTA disclaimer text size locked at 1rem — LOCKED APRIL 2026
CTA slide disclaimer text must be `font-size:1rem`, `color:rgba(255,255,255,0.90)`.

### Never rebuild a project knowledge document from scratch — LOCKED APRIL 2026
When updating the project knowledge document, always use the existing document as the base and merge new content into it. Never rebuild from memory.

### Closing slide must be brand close, not stat repeat — LOCKED APRIL 2026
The last slide of every visuals deck is the helf.school brand close.

### Closing slide must use `justify-content: flex-start` — LOCKED APRIL 2026
`justify-content: center` clips the logo at the top.

### CTA slide must use `cta-wrap-v2` with `grid-template-rows: auto 1fr auto` — LOCKED APRIL 2026
This is the only correct CTA layout.

### 6-card slides must be split to 3+3 — LOCKED APRIL 2026
Never reduce font size or line clamp to make 6 cards fit.

### Reference numbering must be visible — LOCKED APRIL 2026
References must display visible numbers via CSS counter.

### prostate-cancer-visuals.html is new canonical visuals reference — LOCKED APRIL 2026

### All stats require citations in every location — LOCKED APRIL 2026

### Subtypes and formally named sets must be listed, not written in prose — LOCKED APRIL 2026

### The reason for the stat must be in ev-outcome, not ev-conditions — LOCKED APRIL 2026

### ev-stage must use display:flex, never display:grid — LOCKED APRIL 2026
`stress-visuals.html` used `display:grid` — the middle card clipped. Caught by Dr Paul April 2026.

### CTA slide max 5 rows — LOCKED MAY 2026
At filming viewport, 6 CTA rows clip off screen. Maximum 5 rows confirmed May 2026 during lifestyle-visuals.html retrofit. CSS: `grid-template-rows: repeat(5,1fr)`.

### Article research card display standard confirmed — April 2026
The research card stat box in articles must be visually commanding. ev-stat-row: 3.2rem weight 900. The stat box is the headline — it must lead with the clinically important finding in a size that commands attention. Canonical reference: `breast-cancer.html`. See Section 8 for the full CSS specification.

### Series dark variants must be confirmed before retrofit — April 2026
The series-coloured stat box gradient requires a dark variant for each series. All dark variants are now confirmed for all series (see Section 2). Research card colour retrofit is fully unblocked.
Cancer Research UK is approved for UK cancer incidence, mortality, survival, and risk statistics. Always fetch their statistics pages directly.

### Closing slide disclaimer must use .closing-disclaimer class at 1rem — LOCKED APRIL 2026
The closing slide disclaimer must use `font-size:1rem`. The closing slide is the final thing the audience sees — it must be clearly readable on camera. Multiple files were delivered with the wrong class reused from the CTA slide. QC item 26 now checks this.

### Cancer Series established — April 2026
Series E. Articles 27–31. Colour `#2A5A3A` (forest green, confirmed April 2026). Dark variant `#1A3A25`.

### Research card stat boxes use series colour, not navy — LOCKED APRIL 2026
The ev-stat-box background in article research cards must use the series colour gradient (series-dark to series), not plain navy. Established when building breast-cancer.html for the Cancer Series. The amber kf-label contrasts effectively against any series colour.

### prostate-cancer-visuals.html is new canonical visuals reference — LOCKED APRIL 2026
`prostate-cancer-visuals.html` replaces `lifestyle-changes-visuals.html` as the primary canonical visuals reference. It demonstrates: 3-card split slides (slides 3–10), canonical `cta-wrap-v2` CTA (slide 13), brand close (slide 14), `ev-card` research cards with forest green gradient stat box, correct `#stage` padding and `#topbar` structure.

### ic-body word limit — LOCKED APRIL 2026
Cards WITHOUT `.ic-source`: ≤34 words. Cards WITH `.ic-source`: ≤23 words. The source line reduces available body space from 5 lines to 4. Canonical failure: `lung-cancer-visuals.html` April 2026, slides 4–7 — cards ran 27–35 words with source lines, causing visible mid-sentence clipping across four slides.

### ev-body word limit for two stacked ev-cards — LOCKED APRIL 2026
Two stacked ev-cards: ≤30 words in ev-body. Single ev-card: ≤44 words. At 768px filming viewport, the ev-det panel is ~441px wide — at 1.05rem × 1.5 line-height, ~30 words fills 4 lines. Exceeding this clips the text mid-sentence. Canonical failure: cholesterol-visuals.html slides 7–9, caught by Dr Paul April 2026.

### ev-stage display:flex audit is mandatory before delivery — LOCKED APRIL 2026
Every `.ev-stage` CSS rule must show `display:flex`, never `display:grid`. The grid version clips the middle ev-card at filming viewports. Always grep for `ev-stage` and verify before delivering any visuals file.

### The 3-card per slide rule is absolute — LOCKED APRIL 2026
When a slide has 6 informational cards, always split into two slides of 3 cards each. Never reduce font size or line clamp to make 6 cards fit. Text cut-off on 6-card slides confirmed as a recurring problem April 2026. 3-card slides use `-webkit-line-clamp:4` allowing body text to breathe. Canonical reference: `prostate-cancer-visuals.html` slides 3–10.

### Series background colours are mandatory, not optional — LOCKED APRIL 2026
Near-black (`#050f08`, `#060e08`) is not a series colour. All visuals slide backgrounds must use the series dark colour family (see Section 9 table). When any visuals file is opened, check the background and replace with the correct series dark colour if needed.

### The intro slide must not use justify-content:space-between — LOCKED APRIL 2026
`justify-content:space-between` conflicts with `flex:1` on the stat grid. Use no justify-content on the intro slide, and use `grid-template-rows:1fr` on the stat grid. Canonical: `bowel-cancer-visuals.html`.

### All slides must use position:absolute top/left/width/height, not inset:0 — LOCKED APRIL 2026
`inset:0` requires the parent to have a resolved height. In some browsers this fails silently and slides show through each other. Always use explicit `top:0; left:0; width:100%; height:100%`. Canonical: `bowel-cancer-visuals.html`.

### ev-stat-unit class required for months — LOCKED APRIL 2026
When a research card stat is in months, use a separate `ev-stat-unit` div with `font-family:'Fraunces',serif; font-size:1.65rem; font-weight:700; color:rgba(255,255,255,0.88)`. Never abbreviate "months" to "mo" in the ev-stat-row. The unit must be clearly readable.

### Visibility minimums — never go below these thresholds
Source attributions: min 0.75rem; rgba(255,255,255,0.55) on dark / #2C2C2C on light — .source-tag style with rgba(255,255,255,0.25) not permitted.
Key Terms: header min 1.05rem #fff; term labels min 0.88rem weight 700; definition text min 0.92rem rgba(255,255,255,0.90).
Animation/diagram text: labels min 13px rgba(255,255,255,0.80); SVG annotations min 10px rgba(255,255,255,0.60) — opacity 0.50 or below not permitted.
Presenter topbar subtitle: min 0.75rem rgba(255,255,255,0.75); slide counter min 0.85rem rgba(255,255,255,0.90); keyboard hint min rgba(255,255,255,0.60) — values 0.35 or below not permitted.
Hero subtitle: min rgba(255,255,255,0.85); meta items min rgba(255,255,255,0.80); breadcrumb min rgba(255,255,255,0.75) — values 0.60 or below not permitted.
Presenter intro/closing slides: taglines and series label min rgba(255,255,255,0.70); logo dot min rgba(255,255,255,0.60); stat card label rgba(255,255,255,0.90); stat source line 0.75rem rgba(255,255,255,0.65).
Screen file footer: min clamp(.65rem,1vw,.80rem) rgba(255,255,255,0.65).

### Brand close article count must be kept current — MAY 2026
Brand close card 1 must always state the current article count. As of May 2026: **33 articles**.

### Line count ≠ quality — confirmed May 2026
Larger file is not always the correct version. For duplicate file resolution, always read actual content.

### Duplicate file resolution — cue box slide check — MAY 2026
When two versions of a teleprompter exist, check cue box slide references against the correct visuals file slide count. The teleprompter whose cue boxes match the correct visuals is the version to keep.

### coeliac-visuals.html vs coeliac-disease-visuals.html — MAY 2026
`coeliac-disease-visuals.html` (425 lines, May 2026) is the correct file. `coeliac-visuals.html` (664 lines, old pre-rename version) should be deleted from the project.

### Project deduplication — May 2026 session
Full deduplication completed May 2026. All duplicate files resolved. Final confirmed keeps:
- helf-school-project-knowledge.md: 1,812 lines ✅
- index.html: 774 lines ✅
- lifestyle-visuals.html: 320 lines (compact, correct 13-slide version) ✅
- lifestyle-teleprompter.html: 235 lines ✅
- artery-animation.html: 442 lines ✅
- cholesterol-visuals.html: 607 lines ✅
- lung-cancer-visuals.html: 877 lines (877-line retrofit, GitHub) ✅
- epilepsy-visuals.html: 634 lines ✅
- epilepsy-teleprompter.html: 208 lines ✅
- breast-cancer-teleprompter.html: 432 lines ✅
- All 22-line stubs deleted ✅


### Coeliac disease voice audit — May 2026
Two instructional phrases identified in `coeliac-disease.html` for correction:
1. Callout box: `<strong>Do not stop eating gluten before you have been tested.</strong>` → `<strong>Testing while still eating gluten is essential.</strong> Removing gluten before testing quietens the immune reaction and can make the diagnosis much harder to confirm.`
2. Disclaimer: `Do not start a gluten-free diet before being tested — doing so can make the diagnosis much harder to confirm.` → `Starting a gluten-free diet before being tested can make the diagnosis much harder to confirm — testing while still eating gluten is the clinically recommended approach.`
These patches are outstanding and must be applied to `coeliac-disease.html` on GitHub.

### Teleprompter cue box — slide number alignment
Teleprompter cue boxes must reference the correct slide numbers in the matching visuals file. When a visuals file is retrofitted and its slide count changes (e.g. from 10 to 13 slides), all teleprompter cue boxes must be updated to match the new slide numbers. The easiest check: compare the final cue box slide number in the teleprompter against the total slide count in the visuals.

### Brand close article count — update protocol
When a new article is completed and its three files are confirmed on GitHub, update the brand close on every recently built or retrofitted visuals file to show the new count. Do not wait — update it at the same session. As of May 2026: **33 articles**.

### web_fetch token limit for project knowledge file
The `helf-school-project-knowledge.md` file (1,812+ lines, ~105KB) exceeds the default web_fetch token limit. The fetch will truncate mid-document. Always set `text_content_token_limit` to the maximum available, and combine multiple fetch attempts if needed. If the file still truncates, work from the fetched content and append the known remaining sections rather than abandoning the update.

### Duplicate file cleanup — May 2026 principle
When resolving duplicate files in the Claude project:
1. Check the actual file content — line count alone is insufficient
2. For teleprompters: compare cue box slide references against the correct visuals file slide count
3. For visuals: check slide count and card structure (max 3 per slide = correct; 6-card slides = old)
4. For project knowledge: the explicitly noted correct version takes precedence over line count
5. Always confirm before deleting — a wrong deletion cannot be undone without the recycle bin

### Article 33 — Testicular Awareness — completed May 2026
All three files built May 2026: article HTML, visuals, teleprompter. Part of Series B (Practical Health, colour `#7A6A2E`). Visuals in Claude project: `testicular-awareness-visuals.html` (885 lines). Teleprompter: `testicular-awareness-teleprompter.html` (437 lines).

### Article 32 — Breast Awareness — partial build
Visuals (`breast-awareness-visuals.html`, 450 lines) and teleprompter (`breast-awareness-teleprompter.html`, 305 lines) exist in Claude project. Article HTML status on GitHub unconfirmed — verify at next session.

### ibd-script.html and bloating-script.html — confirmed real files
These are old-format presenter/script files (not stubs). `ibd-script.html` (521 lines) and `bloating-script.html` (232 lines) contain real content. They are legacy formats predating the current three-file production workflow. Keep for reference; do not delete.

### bloating-fodmap-screen.html and bloating-gut-screen.html — screen files
These are camera-ready screen files (248 and 210 lines respectively). Used as second-screen visuals during filming of the bloating video. Keep — they are part of the bloating article’s video production files.

### ibd-gut-screen.html — screen file
Camera-ready screen file (223 lines) for the IBD article video. Keep.

### flag4-preview.html and people-grid.html — standalone development files
`flag4-preview.html` (460 lines) and `people-grid.html` (292 lines) are standalone development or preview files. They are not article files. Keep for now — check purpose at next session.
---

## 19. OUTSTANDING TASKS (May 2026)

### Completed ✅
- Cancer Series visuals + teleprompters (27–31): all retrofitted ✅
- Cardiovascular Series visuals + teleprompters (01–07): all retrofitted ✅
- Practical Health Series visuals + teleprompters (08–12): all retrofitted ✅
- Project deduplication: complete May 2026 ✅
- index.html: stat cards updated to broader health audience May 2026 ✅
- helf-school-conditions.html: updated to 33 articles May 2026 ✅

### Immediate — before next session
- Delete `coeliac-visuals.html` (664 lines) from Claude project — superseded by `coeliac-disease-visuals.html`
- Fix `epilepsy-visuals.html` brand close: "31 articles" → "33 articles" (str_replace only)
- Upload to GitHub: `cholesterol-visuals.html` · `coeliac-disease-visuals.html` · `lifestyle-visuals.html` · `index.html` · `helf-school-conditions.html`
- Apply str_replace patches to `coeliac-disease.html` on GitHub (voice audit fixes — two "Do not..." phrases identified)

### Article byline + author card retrofit — ALL 33 articles ❖
When any article HTML is next opened for any reason, add: (1) byline in hero under title; (2) author card before references. See Section 17 for full spec. Build into template for all future articles from this point forward.

### Next priority — Digestive Health Series (Articles 13–21)
Retrofit in order: acid-reflux → bloating → ibs → ibd → coeliac → gallstones → diverticular-disease → masld → constipation

Each file needs:
1. CTA sequential animation (max 5 rows) — replace static cta-rows-v2
2. Brand close pitch cards (logo / credentials / free tier / 33 articles) — replace stat-recap close
3. `display:-webkit-box` on ALL body elements (sys-body/doc-body/mech-body) — AND set `line-clamp:4`
4. Split any 5+ card slides to max 3 cards per slide
5. ev-card: reduce padding to 1.1rem, ev-body clamp:4 if two cards per slide
6. **ev-stage: confirm `display:flex` — fix if `display:grid` found**
7. Teleprompter: remove specific drug names, update CTA segment, update slide numbers
8. Series background colour: replace near-black with correct series dark colour
9. ev-body word count: ≤30 words for two stacked cards
10. ic-body word count: ≤23 words for cards with source lines

### Then: Neurological Series (Articles 22–26)
Same retrofit checklist as Digestive Series above.

### Practical Health Series extension
- Article 32: Breast Awareness — visuals + teleprompter built; article HTML status to confirm
- Article 33: Testicular Awareness — all 3 files complete ✅

### Verification outstanding
- `hypertension.html` references 5 & 6 — Cochrane PubMed IDs flagged ❖ unverified
- `helf-school-conditions.html` — hero stat updated to 33 articles ✅

### Retrofit backlog (apply when files next opened)
All dark variants confirmed April 2026 — retrofit is fully unblocked.

0. **LAY IMPACT FIRST RETROFIT — Rule 34 — LOCKED APRIL 2026** — When any visuals or teleprompter file is opened for any reason, apply: (a) colour narrative — replace uniform cards with red/amber/green by content type; (b) remove any drug generic or brand names — replace with class descriptions; (c) check teleprompter trial references — reduce to name + stat + one plain sentence; (d) consider sequential animation for any formal list (ABCDE, stages, criteria). Priority series: Cancer (27–30) and Cardiovascular (01–07). Canonical reference: `melanoma-visuals.html` and `melanoma-teleprompter.html` (April 2026).

**TELEPROMPTER CONSISTENCY RULE — LOCKED APRIL 2026:** Whenever a visuals file is updated for any reason, the matching teleprompter must be reviewed slide-by-slide before either file is uploaded. Any segment whose corresponding slide has changed content must be rewritten to match.

1. **DRUG BRAND NAMES RETROFIT — Rule 33 — HIGHEST URGENCY — LOCKED APRIL 2026** — All generic drug names across all articles, visuals, and teleprompter scripts must have a brand name added alongside them. Apply to every file when next opened.

**Cardiovascular Series (Articles 01–05):**
- `hypertension.html` / visuals / teleprompter — ACE inhibitors: ramipril (Tritace/Altace), lisinopril (Zestril), perindopril (Coversyl) · ARBs: losartan (Cozaar), candesartan (Amias), valsartan (Diovan) · calcium channel blockers: amlodipine (Norvasc) · beta-blockers: bisoprolol (Cardicor), atenolol · thiazides: indapamide (Natrilix), bendroflumethiazide (Aprinox)
- `cholesterol.html` / visuals / teleprompter — statins: atorvastatin (Lipitor), rosuvastatin (Crestor), simvastatin (Zocor) · ezetimibe (Ezetrol) · PCSK9 inhibitors: evolocumab (Repatha), alirocumab (Praluent)
- `heart-attack-risk.html` / visuals / teleprompter — clopidogrel (Plavix), ticagrelor (Brilique), warfarin (Coumadin), rivaroxaban (Xarelto), apixaban (Eliquis), edoxaban (Lixiana), dabigatran (Pradaxa) · ramipril (Tritace) · atorvastatin (Lipitor)

**Cancer Series (Articles 27–31):**
- `breast-cancer.html` / visuals / teleprompter — trastuzumab (Herceptin), pertuzumab (Perjeta), olaparib (Lynparza), tamoxifen (Nolvadex/Tamofen), palbociclib (Ibrance), ribociclib (Kisqali), abemaciclib (Verzenios), fulvestrant (Faslodex), anastrozole (Arimidex), letrozole (Femara), exemestane (Aromasin), capecitabine (Xeloda)
- `prostate-cancer.html` / visuals / teleprompter — enzalutamide (Xtandi), abiraterone (Zytiga), docetaxel (Taxotere), olaparib (Lynparza), cabazitaxel (Jevtana)
- `lung-cancer.html` / visuals / teleprompter — pembrolizumab (Keytruda) ✅, osimertinib (Tagrisso) ✅ · CHECK: erlotinib (Tarceva), gefitinib (Iressa), bevacizumab (Avastin), nivolumab (Opdivo), atezolizumab (Tecentriq)
- `bowel-cancer.html` / visuals / teleprompter — pembrolizumab (Keytruda) ✅, bevacizumab (Avastin) ✅, cetuximab (Erbitux) ✅, panitumumab (Vectibix) ✅

**Other series:** Check any article containing treatment sections for unbranded drug names. Grep pattern: `egrep -i "mab|tinib|ciclib|pril|sartan|statin|oxacin|vir|mycin" [filename]` will surface most pharmaceutical generics.

2. **Research card colour retrofit** — ev-stat-box background: navy → series-colour gradient. Spec: `linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%)`. Dark variants confirmed for all series (see Section 2). Apply across all 26 articles.
3. **Closing slide brand close retrofit** — stat-recap closing → brand close (logo / pitch cards / disclaimer). Apply across all 26 visuals files. **Article count: 33 as of May 2026.**
4. **Key Terms + Putting it all together** — navy → series-colour gradient. Cancer Series standard confirmed. Decision outstanding: extend to all series or Cancer-only? If extending, same gradient spec applies.
5. **Research card display standard** — ev-stat-row to 3.2rem weight 900 across all articles.
6. **Closing/CTA disclaimer sizes** — closing: `med-disc-text` 1rem; CTA: `med-disc-text` 1rem. Quick grep check per file.
7. **No "free at helf.school"** — grep CTA subline per visuals file.
8. **Research card clinical conclusion standard** — 01–23.
9. **Stat grid citations** — 01–11 only.
10. **Inline citations** — 01–11 only.
11. **CTA slide standard** — 01–11 only. Note: max 5 rows (May 2026).
12. **Visuals layout standard** — 01–11 only.
13. **Subtype list formatting** — apply `<ol class="subtype-list">` to any article containing formally introduced sets of items. Canonical: `lung-cancer.html`.

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

The Claude project holds **visuals, teleprompter, and screen files only**. Article HTML files live on GitHub only — intentionally absent from the Claude project. Exception: `mediterranean-diet.html` kept as canonical article template.

### Claude project — clean state as of May 2026
All duplicates removed. One version of each file. Project at ~43% capacity.

**Files confirmed deleted from project (May 2026):**
- helf-school-project-knowledge.md 2,026 lines (duplicate)
- index.html 816 lines (duplicate)
- lifestyle-visuals.html 610 lines + 597 lines (both superseded by 320-line compact)
- lifestyle-teleprompter.html 227 lines (duplicate)
- lung-cancer-visuals.html 583 lines (duplicate — 877-line version kept)
- epilepsy-visuals.html 505 lines (duplicate)
- epilepsy-teleprompter.html 204 lines (duplicate)
- breast-cancer-teleprompter.html 429 lines (duplicate)
- artery-animation.html 22 lines (stub)
- cholesterol-visuals.html 22 lines (stub)
- All other 22-line stubs: cholesterol-script, ibs-script, hypertension-script, heart-attack-risk-script, Ar sphincter-screen, Ar barretts-screen, acid-reflux-script

**Outstanding delete (project):**
- coeliac-visuals.html 664 lines — old pre-rename version; superseded by coeliac-disease-visuals.html (425 lines)

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
| `lung-cancer.html` | Canonical: myth-busting panel design; `<ol class="subtype-list">` pattern |

### Files confirmed in Claude project (May 2026)
**Teleprompters:** hypertension · cholesterol · heart-attack-risk · statins · lifestyle · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd · ibs · bloating · coeliac · masld · acid-reflux · constipation · migraine · headaches · dizziness-vertigo · memory-dementia · epilepsy · prostate-cancer · breast-cancer · lung-cancer · bowel-cancer · melanoma · breast-awareness · testicular-awareness

**Visuals:** hypertension · cholesterol · heart-attack-risk · statins · lifestyle (320 lines) · salt · supplements · mediterranean-diet · sleep · exercise · stress · alcohol · gallstones · diverticular-disease · ibd · ibs · bloating · coeliac-disease (425 lines) · masld · acid-reflux · constipation · migraine · headaches · dizziness-vertigo · memory-dementia · epilepsy (634 lines) · prostate-cancer · breast-cancer · lung-cancer (291-line compact) · bowel-cancer · melanoma · breast-awareness · testicular-awareness

**Screen files:** ibd-gut-screen · bloating-gut-screen · bloating-fodmap-screen

**Standalone animation files:** v4-smoking-timeline · v1-factor-cards · artery-animation (442 lines) · flag4-preview · people-grid

---

## 22. SESSION START RULES (content of helf-school-session-start-rules.md)

These rules must be applied at the start of every session, before any output or assessment is produced.

### Rule 1 — Read before acting
Read `helf-school-project-knowledge.md` AND `helf-school-session-start-rules.md` in full before any output. No exceptions.

### Rule 2 — Article inventory is the source of truth
The article inventory in Section 3 is authoritative. Do not infer status from file sizes or project file listings.

### Rule 3 — 5,140-byte files are NOT corrupted
Files ~5,140 bytes beginning with "data-build-id" are Edge incognito loader stubs. Never flag as corrupted.

### Rule 4 — Never produce output before confirming understanding
Before building or modifying any file, confirm: (1) which article/file, (2) current status per inventory, (3) canonical reference checked.

### Rule 5 — Educational voice check on every file
Audit every file for forbidden phrases before delivery. Always apply the full canonical phrase.

### Rule 6 — Cross-check article ↔ teleprompter before delivery
All key statistics, study names, years, and citation authors must match exactly.

### Rule 6A — Project knowledge always overrides session-start-rules on status
If session-start-rules.md conflicts with Section 3 of this document, this document is correct.

### Rule 7 — One large file per turn
Build very large HTML files one per turn. Wait for confirmation before proceeding.

### Rule 8 — Verify references before building
Run web searches to verify all planned citations. Fetch figures directly from approved source page.

### Rule 9 — Update project knowledge at session end
Update this document and session-start-rules.md together. Dr Paul uploads both to GitHub AND the Claude Project.

### Rule 10 — NICE CG99 is children only
Never cite NICE CG99 in any adult article.

### Rule 11 — Research card complete clinical conclusion
The stat box must state WHAT was studied and WHAT was found in patient-relevant terms. The test: read the stat box alone. Does a lay reader understand what the research found about their condition? If not, rewrite.

### Rule 12 — Visuals must maximise viewport space
Every visuals slide must fill the available viewport. Body text minimum `.90rem`. Content must fill at least 85% of the visible area. Slide padding maximum `1rem 1.5rem 0.8rem`. Never `1.8rem` or more top padding.

### Rule 13 — PMIDs must be verified by web search every time
Every PMID must be found in a web search result before inclusion. Process: (1) search for the paper by author, title, journal, year; (2) find a PubMed URL in the search results; (3) the PMID is the number in that URL; (4) only then include it. Never include a PMID from memory. No exceptions.

### Rule 14 — Strict source rule
Only approved sources. Derived statistics are not acceptable. Causal attributions require primary citation. If a stat cannot be traced to an approved source, omit it.

### Rule 15 — Exact figure rule — LOCKED APRIL 2026
Use paper’s exact numerical expression everywhere. Never convert between forms. Do not turn ">30%" into "1 in 3" or "33%". Before delivering any file, cross-check every instance of every figure for consistency against the source paper’s exact wording.

### Rule 16 — Stat grid citation rule — LOCKED APRIL 2026
Every `.stat-prose` line must carry a superscript citation. Run `grep -A 3 "stat-prose"` before presenting any article and confirm every instance has a `ref-` link.

### Rule 17 — Approved source retrieval rule — LOCKED APRIL 2026
Every figure must be retrieved directly from the approved source page. A figure found on an unapproved page that attributes its data to an approved source must NOT be used. Always search → find the approved source page → retrieve the figure from that page → use only that figure.

### Rule 18 — Never rebuild the project knowledge document from scratch — LOCKED APRIL 2026
Always use the existing document as the base and merge new content into it. Never rebuild from memory. The existing document is always larger and more complete than what Claude can reconstruct from memory in a session.

### Rule 19 — Cancer Series: three elements use series green, not navy — LOCKED APRIL 2026
Key Terms box · Putting it all together box · Research card stat box all use `linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%)`.

### Rule 20 — Closing slide: brand close, `justify-content: flex-start` — LOCKED APRIL 2026
Never stat repeat. Never `justify-content: center` (clips the logo at the top).

### Rule 21 — CTA slide: `cta-wrap-v2` with `grid-template-rows: auto 1fr auto` — LOCKED APRIL 2026
Only correct CTA layout. Never `justify-content: center` or `space-between`. The `auto 1fr auto` ensures: top badge/headline takes natural height, middle rows expand to fill remaining space, bottom disclaimer always fully visible.

### Rule 22 — 3-card rule: never 6 cards on one slide — LOCKED APRIL 2026
Always split to 3+3. Never reduce font size or line clamp to make 6 cards fit. Use "1 of 2" / "2 of 2" slide labels.

### Rule 23 — Dark variants confirmed: retrofit unblocked — April 2026
All series dark variants confirmed — see Section 2 table. Research card colour retrofit is now fully unblocked across all articles.

### Rule 24 — All stats require citations in every location — LOCKED APRIL 2026
Every numerical figure requires an inline superscript citation in every location. This covers body prose, Key Terms, stat grid cards, research card stat boxes, Putting it all together box, and all other locations.

### Rule 25 — Subtypes and formally named sets must be listed — LOCKED APRIL 2026
When article body prose introduces a formally counted or named set of items ("three main subtypes", "four stages"), those items must be presented in a numbered or bulleted HTML list (`<ol class="subtype-list">`) — never as inline comma-separated prose. Canonical reference: `lung-cancer.html` Section 1 NSCLC subtypes (Article 29, April 2026).

### Rule 26 — prostate-cancer-visuals.html is canonical visuals reference — LOCKED APRIL 2026
Replaces `lifestyle-changes-visuals.html` as primary canonical reference for all future builds. Demonstrates: 3-card split slides, `cta-wrap-v2` CTA, brand close, ev-card research cards with forest green gradient stat box, correct `#stage` padding and `#topbar` structure throughout.

### Rule 27 — All stats require citations in every location — LOCKED APRIL 2026
Every numerical figure, percentage, or quantitative claim in any helf.school file requires an inline superscript citation in every location it appears. Wherever a number appears — in any section, any format, any element — it needs a citation. See QC item 31.

### Rule 28 — CTA slide max 5 rows — LOCKED MAY 2026
CTA slides must use `grid-template-rows: repeat(5,1fr)` or fewer. Six rows clip at filming viewport. Confirmed May 2026 during lifestyle-visuals.html retrofit.

### Rule 29 — Brand close article count must be current — LOCKED MAY 2026
Brand close card 1 must state the current article count. As of May 2026: **33 articles**. Update whenever a new article is completed.

### Rule 30 — Duplicate file resolution: read content, not just line counts — MAY 2026
When choosing between duplicate files, always read actual content. For teleprompters: check cue box slide numbers against the correct visuals slide count. The matching version is correct. Line count alone is insufficient.

---

## 23. ARTICLE-SPECIFIC NOTES

### Article 02 — Cholesterol
- cholesterol-visuals.html: retrofitted May 2026 — ev-cards canonical ev-stat-row pattern, CTA 5 rows, brand close 33 articles ✅

### Article 05 — Lifestyle Changes
- lifestyle-visuals.html: 13 slides (3 cards per slide), 5 CTA rows, brand close 33 articles — May 2026 ✅
- lifestyle-teleprompter.html: 235-line version correct (matches 13-slide visuals) — 227-line deleted

### Article 18 — Coeliac Disease
- coeliac-disease-visuals.html (425 lines): brand close updated 31→33 May 2026 ✅
- coeliac-disease.html: two "Do not..." voice violations identified — str_replace patches outstanding
  1. Callout box: "Do not stop eating gluten before you have been tested." → educational voice version
  2. Disclaimer: "Do not start a gluten-free diet before being tested" → educational voice version
- Note: article slug on GitHub is `coeliac` — visuals file is `coeliac-disease-visuals.html`
- coeliac-visuals.html (664 lines): old pre-rename version — DELETE from project

### Article 26 — Epilepsy
- epilepsy-visuals.html (634 lines): brand close still shows "31 articles" — needs update to 33 ❖

### Article 29 — Lung Cancer
- lung-cancer-visuals.html: 877-line retrofit version on GitHub May 2026 — brand close 33 articles ✅

---

## 24. PLANNING NOTES

### Pending articles — confirmed candidates (as of May 2026)
- Article 32: Breast Awareness — visuals + teleprompter built; article HTML status to confirm
- Article 33: Testicular Awareness — all 3 files complete

### Extended Practical Health series
Articles 32 and 33 extend Series B (Practical Health) using the same colour `#7A6A2E` and production standards.

### No further articles planned beyond 33 at this time.

---

## 25. PROCESS NOTES

### Session peak hours to avoid
1pm–7pm GMT weekdays — limits burn faster during peak hours.

### Output delivery route
Claude outputs accessed via Notepad/download route: Open in Notepad → File → Save As → Downloads → "All Files" → .md or .html extension → upload via + button. Avoids browser loader stub capture.

### Project knowledge update protocol
At end of every session:
1. Fetch `helf-school-project-knowledge.md` from GitHub raw URL
2. Write fetched content to disk exactly
3. Apply str_replace for new session additions only
4. Verify `wc -l` ≥ original
5. Deliver for download and upload to GitHub AND re-upload to Claude project

### Project capacity
Project at ~43% capacity as of May 2026 after deduplication cleanup.

### File line count rule for duplicates
Line count alone is not sufficient to determine which duplicate to keep. Always read the file content. Known exceptions to "bigger = better":
- helf-school-project-knowledge.md: 1,812 correct (not 2,026)
- index.html: 774 correct (not 816)
- lifestyle-visuals.html: 320-line compact version correct (not 597 or 610)
- lifestyle-teleprompter.html: 235 correct (not 227)


### Retrofit priority order (confirmed May 2026)

When retrofitting existing visuals files, tackle in this order to maximise impact per session:

**Tier 1 — Structural fixes (do these first, they affect every slide)**
1. 6-card slides → split to 3+3
2. ev-stage display:grid → display:flex
3. Series background colour (near-black → series dark)
4. animate-ready class on all animated cards

**Tier 2 — Content fixes (do these after structure)**
5. CTA: replace old CTA with cta-wrap-v2 (max 5 rows)
6. Brand close: replace stat-recap with helf.school brand close (33 articles)
7. ev-body word count: reduce to ≤30 words for two stacked cards
8. ic-body word count: reduce to ≤23 words for cards with source lines
9. Remove drug names from slides → replace with class descriptions

**Tier 3 — Colour narrative (do after structure and content)**
10. Apply red/amber/green colour narrative to all info cards
11. Apply colour to stat boxes in research slides

**Tier 4 — Teleprompter (do last, after visuals are confirmed)**
12. Review teleprompter for slide number alignment
13. Remove drug names from script
14. Verify word count 600–750 words

### helf-school-session-start-rules.md — must be updated at same time
When the project knowledge document is updated at session end, `helf-school-session-start-rules.md` must also be updated in the same session. Both files must be uploaded to GitHub AND re-uploaded to the Claude project for changes to take effect in future sessions. Failure to do this has caused recurring audit problems where rules confirmed in one session were not applied in the next.

### Previous session file upload protocol
At the end of each production session, the following files should be uploaded to GitHub:
1. Any newly built or retrofitted HTML files (article, visuals, teleprompter)
2. `helf-school-project-knowledge.md` (updated version)
3. `helf-school-session-start-rules.md` (updated version if changed)
4. Any updated site files (`index.html`, `helf-school-conditions.html`)

Dr Paul uploads files via the GitHub drag-and-drop interface at github.com/pls4286/helfschool/upload/main. Sign in with Google if the session has expired. Upload individual HTML files, not zipped archives.

### Session handoff — what to tell Claude at the start of each new session
At the start of any new session within the helf.school project, Claude will automatically read the project knowledge files. However, to help Claude orient quickly, it is useful to state:
1. What was last worked on (which article or file)
2. Any outstanding actions from the previous session
3. Any files that were uploaded to GitHub since the last session

This saves time otherwise spent re-reading the full project knowledge to determine the current state.

### GitHub Pages URL structure
All published files are accessible at: `https://pls4286.github.io/helfschool/[filename].html`

Examples:
- Homepage: `https://pls4286.github.io/helfschool/index.html`
- Conditions: `https://pls4286.github.io/helfschool/helf-school-conditions.html`
- Hypertension article: `https://pls4286.github.io/helfschool/hypertension.html`
- Cholesterol visuals: `https://pls4286.github.io/helfschool/cholesterol-visuals.html`
- Lung cancer teleprompter: `https://pls4286.github.io/helfschool/lung-cancer-teleprompter.html`

Pages typically go live within 30–60 seconds of a GitHub push.

### When to use web_fetch vs project files
- **Article HTML files:** Always use GitHub raw URL — these do not exist in the Claude project by design
- **Visuals + teleprompter HTML files:** Use project files for the most recent version; verify via GitHub if there is any doubt
- **Project knowledge + session start rules:** Read from project files; update via fetch + str_replace at session end
- **Site files (index.html, conditions.html):** Always fetch from GitHub to get the current version before editing

### End of document marker
This document was last updated: May 2026
Total articles: 33 (Series A: 7 · Series B: 7 · Series C: 9 · Series D: 5 · Series E: 5)
Project capacity: ~43% (post-deduplication, May 2026)
Next session priority: Upload files to GitHub · Fix epilepsy-visuals brand close · Begin Digestive Series retrofit