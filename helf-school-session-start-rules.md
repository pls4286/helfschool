# helf.school — MANDATORY SESSION-START RULES
## Claude must follow these rules at the start of EVERY session, without exception.
---

## ⛔ RULE 0 — MANDATORY PRE-OUTPUT AUDIT (THE RULE THAT ENFORCES ALL OTHER RULES)

Every session has produced errors — wrong citations, wrong PMIDs, wrong NICE numbers, medical terms without lay definitions, hero text invisible against matching backgrounds, research card stat boxes showing statistical machinery instead of clinical conclusions, figures paraphrased into different numerical forms, figures taken from unapproved secondary sources, stat grid cards missing inline citations, and body prose stats missing citations entirely. These errors share one cause: output was generated before the full audit was completed.

**This rule exists to stop that pattern.**

Before presenting ANY helf.school file, Claude runs the following audit internally. This is not optional. This is not a post-delivery check. It happens before the file is presented.

**Citation audit (runs before building AND before presenting):**
- Every cited paper: confirm it EXISTS, is PRIMARY (not a guidance doc citing another paper), and contains the SPECIFIC STAT claimed — fetch the abstract to confirm if needed
- Every NICE guideline number: verify CG vs NG by web search — never from memory
- Every PMID: verify by web search that it resolves to the correct paper — a PubMed URL must appear in search results. Never include a PMID from memory or inference
- Every figure: confirm it was retrieved directly from the approved source page — NOT from a secondary or aggregator page that attributes the figure to an approved source

**Lay-clarification audit (runs before presenting every article):**
- Read every sentence for medical terminology
- Every term a lay reader would not immediately know must have a plain English definition in brackets on first use per section
- This includes: anatomical terms · physiological terms · symptom names · drug class names · diagnostic labels · statistical measures
- The Key Terms box does not replace inline definitions — both are required

**Voice audit (runs before presenting every file):**
- No forbidden phrases: "you should" · "speak to your GP" · "seek help" · "call 999/111"
- Canonical phrase present in full: "Anything personally relevant is a conversation for you to have with your GP or healthcare professional"

**Research card clinical conclusion audit (runs before presenting every article and visuals file):**
- Every research card stat box must state the complete clinical finding in patient-relevant terms
- The test: can a lay reader understand WHAT was studied and WHAT was found from the stat box alone, without reading the body text?
- Statistical machinery must never appear as the headline: no ORs, no RCT counts, no confidence intervals, no participant counts as the primary stat
- Incomplete qualifiers are not permitted: "Safe & effective" without stating WHAT is safe and effective; "Moderate to strong evidence" without stating WHAT has that evidence level
- Correct examples: "The Epley manoeuvre / is safe & effective for BPPV" · "Vestibular rehabilitation / has moderate to strong evidence for its efficacy" · "77% response rate / vs 44% placebo"
- Incorrect examples: "11" (RCT count) · "OR 2.67" (odds ratio) · "Safe & effective" (no subject) · "Moderate to strong evidence" (no subject)

**Stat grid citation audit — LOCKED APRIL 2026:**
- Run `grep -A 3 "stat-prose"` before presenting any article
- Every `.stat-prose` line must have a `ref-` superscript link
- All stat grid cards. No exceptions. Every card, every time.
- A stat grid card with no citation is a QC failure regardless of how obvious the stat appears
- Example of this failure: breast cancer article (April 2026) — three of four stat grid cards had no citations. Caught by Dr Paul during review.

**ALL STATS IN ALL LOCATIONS require citations — LOCKED APRIL 2026:**
- Scan every paragraph and every text element in the file for numerical figures and percentages
- Every stat in every location must carry an inline superscript citation
- This covers: body prose, Key Terms box, stat grid (covered above), research card text, Putting it all together box, discussion cards, myth panel evidence text, visuals slide text, teleprompter scripts
- **Why this rule was added:** Dr Paul identified in `lung-cancer.html` (Article 29, April 2026) that "It is the most common cause of cancer death in the UK" and "around 80 to 85% of all lung cancers are NSCLC" both appeared in body prose without citations. This confirmed the rule applies universally to all locations — not just stat grid cards.

**Exact figure audit (runs before presenting every file):**
- Every statistic must use the paper's exact numerical expression
- Never convert between forms: ">30%" must not become "1 in 3" or "33%"; "1 in 1,000" must not become "0.1%"
- Cross-check stat grid, research cards, Key Terms, body prose, Putting It Together, and teleprompter for consistency

**Source audit (runs before presenting every file):**
- Every stat, claim, and causal attribution must be traceable to an approved source
- Charity and advocacy websites are NOT approved (Epilepsy Action, Alzheimer's Society, WCRF, Breast Cancer Now, etc.)
- Aggregator sites (WCRF etc.) are NOT approved even when they attribute data to approved sources — fetch the approved source page directly
- Derived figures are not acceptable — only cite figures explicitly stated in the approved source
- Causal attributions require a specific primary citation — never inferred from context
- Example of this failure: breast cancer article (April 2026) used 60,763 from WCRF instead of "around 59,000" from Cancer Research UK directly

**Subtype/list formatting audit — LOCKED APRIL 2026:**
- Before presenting any article, grep for phrases like "three main", "four types", "two subtypes", "the following", "X stages"
- Any formally counted or named set of items must appear as a `<ol class="subtype-list">` numbered list — never as comma-separated inline prose
- Canonical: `lung-cancer.html` Section 1 NSCLC subtypes (Article 29, April 2026)

**Visuals audit (runs before presenting every visuals file):**
- ev-stat-box: `padding:.9rem .75rem` · `overflow:hidden` · `.ev-conditions` at `.78rem`
- Hero series badge: `color:#fff` — never the series accent colour
- All animated cards: `animate-ready` class present, no hardcoded `opacity:0`
- **CTA slide — LOCKED APRIL 2026:** Must use `cta-wrap-v2` with `grid-template-rows: auto 1fr auto`. This is the only layout that guarantees the disclaimer is never clipped. Never `justify-content: center` or `space-between` on the CTA slide. `med-disc-text` at `font-size:1rem`. Canonical: `prostate-cancer-visuals.html` slide 13.
- **Closing slide — LOCKED APRIL 2026:** Must be the helf.school brand close — NOT a stat repeat. `close-wrap` with `justify-content: flex-start` (never `center` — clips the logo). Three pitch cards (articles / Dr Paul / free tier). `med-disc-text` at `font-size:1rem`. Canonical: `prostate-cancer-visuals.html` slide 14.
- **No "free at helf.school" — LOCKED APRIL 2026:** CTA slide subline must not reference "free at helf.school". Remove `.cta-sub` text or use a non-pricing line. "Start for free" card is permitted (genuine £0 tier). "Free to read — always" is not permitted. "Evidence-based health education — free at helf.school" is not permitted.
- **3-CARD RULE — LOCKED APRIL 2026:** Never 6 cards on one slide. Always split to 3+3, labelled "(1 of 2)" and "(2 of 2)". Text cut-off on 6-card slides is a recurring failure. Canonical: `prostate-cancer-visuals.html` slides 3–10.
- **VIEWPORT MAXIMISATION:** Every slide must fill at least 85% of the visible area. Slide padding maximum `1rem 1.5rem 0.8rem`. Body text minimum `.90rem`. Gaps maximum `.5rem`. Slide title minimum `1.55rem`. If content looks small or sparse — fix it before presenting. Visuals are filmed. Undersized content is a delivery failure.

**The rule:** Output first, audit after is the failure pattern. Audit first, output after is the required pattern. Paul must never be the one to catch these errors.

---

## ⛔ RULE 1 — READ THE PROJECT KNOWLEDGE DOCUMENT FIRST

Before doing ANYTHING — before responding, before building, before auditing — read `helf-school-project-knowledge.md` in full.

**Why this rule exists:** In April 2026, Claude wrote a new project knowledge document from scratch without reading the existing one. It lost 200 lines of critical information, got the lifetime membership price wrong (£120 instead of £150), and caused Dr Paul approximately 8 hours of duplicated work. In a second April 2026 session, Claude ran a file audit and raised false alarms about "corrupted" files without reading Section 1 of the project knowledge first, causing further wasted time.

**The rule:** If a project knowledge document exists in this Project, Claude reads it before the first response. Claude does not summarise it back, does not comment on it, just reads it silently and uses it.

---

## ⛔ RULE 2 — NEVER WRITE A NEW PROJECT DOCUMENT WITHOUT READING THE OLD ONE

If Paul asks for an updated project knowledge document, Claude must:
1. Read the existing document first
2. Identify what is new from the current session
3. Merge new information INTO the existing document
4. Never replace the existing document with a shorter one

**The rule:** The existing document is always the base. New information is always added to it. A shorter replacement document is always wrong.

**Why this rule also applies to the session-start-rules file:** In April 2026, Claude rebuilt the session-start-rules file from memory twice in the same session, producing shorter versions than the uploaded original both times. The uploaded document is always the base. If Dr Paul uploads a version, that is the version to build on — not a reconstruction from memory.

---

## ⛔ RULE 3 — CHECK FILE STATUS BEFORE BUILDING ANYTHING

Before building or rebuilding any file, Claude must check the article inventory in the project knowledge document and confirm whether a correct version already exists.

**The rule:** If the project knowledge document shows ✅ for a file, Claude does not rebuild it unless Paul explicitly asks.

---

## ⛔ RULE 4 — NEVER CLAIM FILES ARE CORRECT WITHOUT VERIFICATION

Claude cannot access GitHub directly. Claude cannot verify what is currently in Paul's repository without Paul pasting the file content.

**The rule:** Claude states what was done in the current session with certainty. For files from previous sessions, Claude defers to the project knowledge document as the source of truth. Claude never says "that file is definitely correct on GitHub" — Claude says "according to the project knowledge document, that file was completed in [session]."

---

## ⛔ RULE 5 — THE TELEPROMPTER CHECK IS ⏸ PAUSE

The single fastest check for whether a teleprompter file is the correct canonical version: open it in a browser. The button reads **⏸ Pause**. If it reads **▶ PLAY**, it is the old format and needs rebuilding.

**The rule:** Never accept a teleprompter as correct without this check. Never rebuild a teleprompter that already shows ⏸ Pause.

---

## ⛔ RULE 6 — THE ARTICLE INVENTORY IS THE SOURCE OF TRUTH

Section 3 of `helf-school-project-knowledge.md` contains the complete status of every article file. This table is maintained carefully and is accurate.

**The rule:** At the start of a session, Claude reads this table. Claude does not re-audit files that are marked ✅ unless Paul explicitly asks. Claude does not tell Paul that retrofit work needs doing if the project knowledge document says it has already been done.

---

## ⛔ RULE 6A — PROJECT KNOWLEDGE ALWAYS OVERRIDES THIS FILE ON STATUS

**THIS IS THE MOST IMPORTANT CONFLICT-RESOLUTION RULE.**

If the file status table in THIS document (session-start-rules.md) contradicts the article inventory in `helf-school-project-knowledge.md`, the project knowledge document is ALWAYS correct.

**Why this rule exists:** The status table in this file has repeatedly fallen out of sync with the project knowledge document because both files were not updated together at session end. Every time this happened, Claude defaulted to the wrong (outdated) information in this file and told Dr Paul that work had not been done when it had — causing repeated arguments and wasted time across multiple sessions in April 2026.

**The rule:** In any conflict between the two documents, project knowledge wins. Claude never flags outstanding work based on this file alone.

---

## ⛔ RULE 7 — VOICE AUDIT AND LAY-CLARIFICATION BEFORE EVERY OUTPUT

Before presenting any helf.school file (article, visuals, teleprompter), Claude runs a full internal voice audit AND a lay-clarification audit.

Forbidden: "you should", "speak to your GP", "seek help", "call 999/111", "avoid", "don't".
Required full phrase: "Anything personally relevant is a conversation for you to have with your GP or healthcare professional."

**Lay-clarification audit:** Every medical or clinical term that a lay reader would not immediately understand must have a plain English definition in brackets on first use in each section. This applies to ALL medical terminology — anatomical terms, physiological terms, symptom descriptors, drug class names — not just the statistical terms listed in the project knowledge.

**The rule:** Both audits happen before output. Paul must never need to ask for either.

---

## ⛔ RULE 8 — DOWNLOAD METHOD IS ARTIFACT PANEL ONLY

Every file Paul downloads must use the Artifact panel download button. Never Ctrl+S. Never File → Save. This corrupts files.

**The rule:** Remind Paul of this at every file output.

---

## ⛔ RULE 9 — END OF SESSION PROTOCOL IS MANDATORY

At the end of every session involving new builds or decisions:
1. Update `helf-school-project-knowledge.md`
2. Update THIS file (`helf-school-session-start-rules.md`) — especially the status table below
3. Paul downloads both via Artifact panel
4. Paul uploads BOTH to GitHub AND the Claude Project

**The rule:** Both files must be updated and uploaded together. If only one is updated, they fall out of sync and Rule 6A conflict will repeat.

---

## ⛔ RULE 10 — NICE CG99 IS CHILDREN ONLY

Never cite NICE CG99 in any adult article. It covers constipation in children and young people only. The correct adult constipation reference is NICE CKS at cks.nice.org.uk/constipation.

---

## ⛔ RULE 11 — RESEARCH CARD STAT BOXES MUST STATE COMPLETE CLINICAL CONCLUSIONS

**This is a health education site. The research section exists to tell readers what medicine has found about their condition — in terms they can understand.**

Every research card stat box must state the complete clinical finding as it is relevant to the patient. This means the stat box (label + stat row + outcome + conditions together) must answer:
1. **WHAT** was studied or found
2. **WHAT** the finding means for someone with that condition

**The test:** Can a lay reader understand the clinical finding from the stat box alone, without reading the body text? If not, rewrite before presenting.

**Never permitted as a headline stat:**
- Number of RCTs or studies ("11", "39 studies")
- Odds ratios or confidence intervals ("OR 2.67", "95% CI")
- Participant counts ("2,441 participants")
- Incomplete qualifiers without their subject ("Safe & effective" · "Moderate to strong evidence")

**Correct approach:**
- "The Epley manoeuvre / is safe & effective for BPPV"
- "Vestibular rehabilitation / has moderate to strong evidence for its efficacy"
- "77% response rate / vs 44% placebo"
- "Macrogol superior / to lactulose across all outcomes"

**Why this rule exists:** In April 2026, research card stat boxes for the dizziness and vertigo article showed "11" (number of RCTs) and "OR 2.67" (odds ratio) as headline findings. These numbers are statistical machinery — they tell the reader nothing about their condition. Dr Paul correctly identified this as a failure of health education. The clinically important point — that the Epley manoeuvre is safe and effective for BPPV, that vestibular rehabilitation has moderate to strong evidence — must be the headline. See Section 8 and QC item 9 of the project knowledge for the full rule.

---

## ⛔ RULE 12 — VISUALS MUST MAXIMISE VIEWPORT SPACE

**Every visuals slide must fill the available viewport. Slides that leave large areas of empty space are a delivery failure.**

The fixed viewport is `100vw × 100vh` minus the 52px topbar and 32px dots bar. Every slide must use this space aggressively.

**Required minimums/maximums — every slide:**
- Slide padding: maximum `1rem 1.5rem 0.8rem` — never `1.8rem` top padding
- Slide title: minimum `1.55rem`
- Slide subtitle margin-bottom: maximum `.6rem`
- All card/row body text: minimum `.90rem` — never `.75rem` or `.80rem`
- Card/row gaps: maximum `.5rem` — never `.7rem` or above
- Info/step row body line clamp: minimum 3 lines — never 2

**CTA slide — confirmed working sizes (April 2026):**
- Central icon: `5.5rem` · Headline: `clamp(2.8rem, 5.5vw, 4.2rem)` · Subline: `1.2rem`
- Card emoji icons: `2.2rem` · Card title text: `.96rem`

**Closing slide — confirmed working sizes (April 2026):**
- Logo: `2.8rem` · Tagline: `1.05rem` · Link/series label: `1rem`

**The test:** Open every slide in a browser before delivering. Content must fill at least 85% of the visible area. If slides look sparse, increase font sizes and reduce gaps until they are full. Visuals are filmed — undersized content reads poorly on camera.

---

## ⛔ RULE 13 — PMIDs MUST BE VERIFIED BY WEB SEARCH EVERY TIME

Claude has repeatedly generated plausible-sounding but incorrect PMIDs across multiple sessions. This is a known, recurring failure.

**The mandatory process:**
1. Search for the paper by author, title, journal, year
2. Find a PubMed URL in the search results
3. The PMID is the number in that URL
4. Only then include the PMID in the file

**Never include a PMID from memory. No exceptions.**

**Why this rule exists:** In April 2026, PMID 25088348 was included for Thurman et al Epilepsia 2014 — the correct PMID is 24903551. The error was only caught because Dr Paul challenged the reference.

---

## ⛔ RULE 14 — STRICT SOURCE RULE

Only approved sources may be cited (see Section 14 of project knowledge). Charity and advocacy websites are not approved regardless of how credible they appear. Derived statistics (calculating a UK death count from a per-1,000 incidence rate) are not acceptable — only figures explicitly stated in the approved source may be used. Causal attributions require a specific primary citation. If a stat cannot be traced to an approved source, omit it.

**Why this rule exists:** In April 2026, an Epilepsy Action statistic about unemployment was included alongside a causal attribution ("driven partly by disability discrimination") with no primary citation. Both were removed when challenged.

---

## ⛔ RULE 15 — EXACT FIGURE RULE — LOCKED APRIL 2026

Use the paper's exact numerical expression in every location a figure appears. Never convert between forms:
- ">30%" must not become "1 in 3", "33%", or "around a third"
- "1 in 1,000" must not become "0.1%"
- "26.1%" must not become "around a quarter" or "roughly one in four"

Before delivering any file, cross-check every instance of every statistic — stat grid, research cards, Key Terms definitions, body prose, Putting It Together, and teleprompter — for consistency with the source paper's exact wording.

**Why this rule exists:** In April 2026, Kwan & Brodie NEJM 2000 reports "more than 30 percent" but the epilepsy article stat grid showed "1 in 3" and the research card showed "1 in 3" — a conversion that misrepresents the source. Every instance across all file locations had to be corrected.

---

## ⛔ RULE 16 — STAT GRID CITATION RULE — LOCKED APRIL 2026

Every `.stat-prose` line in the Why does it matter? stat grid must carry a superscript inline citation. Run `grep -A 3 "stat-prose"` before presenting any article and confirm every instance has a `ref-` link.

**Every card. No exceptions. Every time.**

**Why this rule exists:** In the breast cancer article (Article 27, April 2026), three of four stat grid cards were presented without citations. This was caught by Dr Paul during review — not by Claude's pre-output audit. The rule is now explicit and the QC grep check is mandatory.

---

## ⛔ RULE 17 — APPROVED SOURCE RETRIEVAL RULE — LOCKED APRIL 2026

Every figure must be retrieved directly from the approved source page. If a figure appears on an unapproved page (WCRF, charity site, aggregator) that attributes it to an approved source, do NOT use that figure. Fetch the approved source page directly and use the figure stated there.

**Why this rule exists:** In the breast cancer article (Article 27, April 2026), the incidence figure 60,763 was taken from the WCRF website and incorrectly presented as a Cancer Research UK figure. The Cancer Research UK statistics page directly states "around 59,000." The error was caught by Dr Paul.

**Approved sources for cancer statistics:** Cancer Research UK (added April 2026) · ONS · NHS/NHS Digital · WHO · Global Burden of Disease.
**Not approved even when they cite approved sources:** WCRF · Breast Cancer Now · any charity or advocacy website.

---

## ⛔ RULE 18 — NEVER REBUILD EITHER DOCUMENT FROM SCRATCH — LOCKED APRIL 2026

When updating `helf-school-project-knowledge.md` OR `helf-school-session-start-rules.md`, always use the existing uploaded document as the base. Read it fully, identify what is new, and merge new content in. Never rebuild from memory.

**Why this rule exists:** In April 2026, Claude rebuilt both documents from memory in the same session — producing versions shorter than the uploaded originals both times. Both errors were caught by Dr Paul. The uploaded document is always more complete than what Claude can reconstruct from memory. A rebuilt-from-memory version will always be shorter and lose content.

**The mandatory process:**
1. The uploaded document is the base — always
2. Read it in full
3. Identify only what is new from the current session
4. Add new content to the existing document — do not rewrite or abbreviate existing sections
5. Run `wc -l` and confirm the new version is equal to or greater than the uploaded version
6. If the new version is shorter, something has been lost — find it and restore it before delivering

---

## ⛔ RULE 19 — CANCER SERIES: THREE ELEMENTS USE SERIES GREEN, NOT NAVY — LOCKED APRIL 2026

In Cancer Series articles (27–31), three elements must use `linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%)` — the forest green gradient — instead of plain navy:

1. **Key Terms box** — `.key-terms { background: linear-gradient(...) }`
2. **Putting it all together box** — `.putting-together { background: linear-gradient(...) }`
3. **Research card stat box** — `.ev-stat-box { background: linear-gradient(...) }`

Cancer Series colours: `--series: #2A5A3A` · `--series-dark: #1A3A25`

Apply from the start when building articles 28–31. Do not use navy for any of these three elements in Cancer Series articles. Confirmed in `breast-cancer.html` April 2026.

---

## ⛔ RULE 20 — CLOSING SLIDE DISCLAIMER: .closing-disclaimer CLASS AT 1rem — LOCKED APRIL 2026

The closing slide of every visuals file must use the `.closing-disclaimer` and `.closing-disclaimer-text` classes — **not** `.cta-disclaimer`.

**Locked spec:**
```css
.closing-disclaimer { max-width:680px; border:1.5px solid rgba(255,255,255,0.40); border-radius:10px; padding:1rem 1.3rem; background:rgba(255,255,255,0.05); }
.closing-disclaimer-icon { font-size:1.4rem; }
.closing-disclaimer-text { font-size:1rem; color:rgba(255,255,255,0.90); line-height:1.6; font-weight:400; }
```

**Why this rule exists:** Multiple files were delivered with `.cta-disclaimer` reused on the closing slide — which uses `.80rem` text, too small to read on camera. Caught by Dr Paul in April 2026.

**The test:** Before presenting any visuals file, grep for `.closing-slide` and confirm the disclaimer inside uses `.closing-disclaimer-text`, not `.cta-disclaimer-text`.

**Note — canonical update April 2026:** `prostate-cancer-visuals.html` uses `med-disclaimer` / `med-disc-text` classes on both the CTA and closing slides, which is the new canonical pattern. Both patterns (`.closing-disclaimer` for older files, `med-disc-text` for new files built to the prostate-cancer canonical) are acceptable, provided the font size is `1rem` in both cases.

---

## ⛔ RULE 21 — CTA SLIDE: 1rem DISCLAIMER + NO "FREE AT HELF.SCHOOL" — LOCKED APRIL 2026

**CTA disclaimer size:** CTA slide disclaimer text must be `font-size:1rem`, `color:rgba(255,255,255,0.90)`. Never `.80rem`.

**No "free at helf.school":** The CTA slide subline (`.cta-sub`) must not reference being free at helf.school. helf.school is a subscription service. Remove the subline entirely or use a non-pricing line.

**Permitted:** "Start for free" as a card label — there is a genuine £0 Explorer tier.
**Not permitted:** "Free to read — always" · "Evidence-based health education — free at helf.school" · any variation implying all content is permanently free.

**The test:** Before presenting any visuals file, grep for `cta-sub` and `free at helf` — both must return zero results.

---

## ⛔ RULE 22 — DARK VARIANTS CONFIRMED: RETROFIT UNBLOCKED — APRIL 2026

All series dark variants are confirmed. The research card colour retrofit (navy → series gradient on ev-stat-box) is fully unblocked. Apply per series as files are next opened.

| Series | Primary | Dark variant |
|--------|---------|-------------|
| Cardiovascular | `#C8423A` | `#8A2020` |
| Neurological | `#6B5EA8` | `#4A4080` |
| Digestive | `#D47C3A` | `#8A4A1A` |
| Fatigue | `#3A8A7A` | `#1A5A4A` |
| Medical Decision | `#2E6BA8` | `#1A3A6A` |
| Practical Health | `#7A6A2E` | `#4A3A1A` |
| Cancer | `#2A5A3A` | `#1A3A25` |

Retrofit spec: `.ev-stat-box { background: linear-gradient(160deg, var(--series-dark) 0%, var(--series) 100%); }`

---

## ⛔ RULE 23 — 3-CARD RULE: NEVER 6 CARDS ON ONE SLIDE — LOCKED APRIL 2026

**When a visuals slide has 6 informational cards, always split into two slides of 3 cards each. Never reduce font size or line clamp to make 6 cards fit.**

Text was cut off on multiple 6-card slides in April 2026. The fix: split to 3+3, label slides "(1 of 2)" and "(2 of 2)". 3-card slides use `-webkit-line-clamp:4` — body text breathes fully and nothing is clipped.

Articles with 6 informational points (what is it, risk factors, diagnosis, treatment) will produce two slides each — typically resulting in 14-slide decks rather than 10. This is correct and expected.

**Canonical reference:** `prostate-cancer-visuals.html` slides 3–10.

---

## ⛔ RULE 24 — CLOSING SLIDE: BRAND CLOSE + `justify-content: flex-start` — LOCKED APRIL 2026

**The closing slide is the helf.school brand close — NOT a repeat of the research statistics from the CTA slide.**

**Structure — canonical: `prostate-cancer-visuals.html` slide 14:**
- `close-wrap` with `justify-content: flex-start` — **NEVER `justify-content: center`** (clips the logo at top when content height approaches viewport height)
- helf.school logo — large Fraunces, with coral dot
- "Health Education" tagline — uppercase
- Brand headline — e.g. "Evidence-based. Built by a doctor."
- Three brand pitch cards: 📚 article count · 🩺 Dr Paul credentials · 🔓 Start for free
- `med-disclaimer` at `font-size:1rem`
- Series label — e.g. "Cancer Series · Article 28 · Prostate Cancer"

**Why this rule exists:** Dr Paul identified the previous closing slide (which repeated the CTA research stats) as redundant — the closing slide should be the brand impression. Confirmed April 2026.

**Why `justify-content: flex-start` is mandatory:** `center` clips the logo when total content height is close to the viewport. `flex-start` anchors the logo at top — any overflow falls off the bottom, not the top.

---

## ⛔ RULE 25 — CTA SLIDE: `cta-wrap-v2` WITH `grid-template-rows: auto 1fr auto` — LOCKED APRIL 2026

**The CTA slide must use `cta-wrap-v2` with `grid-template-rows: auto 1fr auto`. This is the only correct layout.**

`auto 1fr auto` means: top badge/headline takes its natural height; middle 4 rows expand to fill all remaining space; bottom disclaimer anchors at bottom. Nothing is ever clipped.

**Never use `justify-content: center` or `justify-content: space-between`** — both clip content when total height is close to or exceeds the viewport.

**Structure:**
- `.cta-top` — badge + headline (auto height)
- `.cta-rows-v2` — 4 horizontal rows, `grid-template-rows: 1fr 1fr 1fr 1fr` (fills 1fr middle)
- `.cta-bottom` — `med-disclaimer` at `font-size:1rem` (auto height, always visible)

**Canonical reference:** `prostate-cancer-visuals.html` slide 13.

**Why this rule exists:** Multiple CTA slides were delivered with cut-off top or bottom content in April 2026, caused by using `justify-content: center` or `space-between`. The `auto 1fr auto` grid is the fix that guarantees nothing is clipped.

---

## ⛔ RULE 26 — `prostate-cancer-visuals.html` IS THE NEW CANONICAL VISUALS REFERENCE — LOCKED APRIL 2026

`prostate-cancer-visuals.html` replaces `lifestyle-changes-visuals.html` as the **primary canonical visuals reference** for all future builds.

It demonstrates:
- **3-card split slides** (slides 3–10) — the correct approach for all informational content
- **`cta-wrap-v2` CTA** (slide 13) — `grid-template-rows: auto 1fr auto`, canonical layout
- **Brand close** (slide 14) — `justify-content: flex-start`, three pitch cards
- **`ev-card` research cards** with forest green gradient stat box
- **Correct `#stage` padding** and `#topbar` structure throughout

`lifestyle-changes-visuals.html` remains a valid secondary reference for the 6-row grid pattern (used in mechanism/action slides where appropriate). But for overall structure, CTA, closing, and card layout — `prostate-cancer-visuals.html` is the reference.

---

## ⛔ RULE 27 — ALL STATS REQUIRE CITATIONS IN EVERY LOCATION — LOCKED APRIL 2026

**Every numerical figure, percentage, or quantitative claim in any helf.school file requires an inline superscript citation — regardless of where in the file it appears.**

This covers every location: body prose paragraphs, Key Terms box definitions, stat grid cards (see Rule 16), research card stat boxes and body text, Putting it all together box, discussion cards, myth panel evidence text, visuals slide text, and teleprompter scripts.

**Before presenting any file:** scan every paragraph and every text element for numerical figures and percentages. Every one must have a superscript citation or be flagged ⚑. If it's a number, it needs a citation.

**Why this rule was added:** Dr Paul identified in `lung-cancer.html` (Article 29, April 2026) that "It is the most common cause of cancer death in the UK" appeared in body prose paragraph 1 without a citation, and "around 80 to 85% of all lung cancers are NSCLC" appeared in body prose paragraph 2 without a citation. Both were body prose statements — locations not previously checked as rigorously as stat grid cards. This confirmed the rule must apply universally. Both were corrected.

**The rule:** No stat anywhere. If it's a number, it needs a citation. No exceptions, no locations exempt.

---

## ⛔ RULE 28 — SUBTYPES AND FORMALLY NAMED SETS MUST BE LISTED, NOT IN PROSE — LOCKED APRIL 2026

**When article body prose introduces a formally counted or named set of items using a phrase like "three main subtypes", "four stages", "two types of", "the following five", those items must be presented in a numbered or bulleted HTML list — never as comma-separated inline prose.**

**The test:** if you can count the items in the introductory sentence, they go in a list.

**Implementation:** use `<ol class="subtype-list">` with the canonical CSS pattern first introduced in `lung-cancer.html` (Article 29, April 2026):
- Numbered circle markers in series colour
- Bold term name followed by em-dash and definition
- Full body size (1rem, line-height 1.72)

**Before presenting any article:** grep for phrases like "three main", "four types", "two subtypes", "the following". Any formally introduced set of items must be in a list.

**Why this rule was added:** Dr Paul identified that the three NSCLC subtypes (adenocarcinoma, squamous cell carcinoma, large cell carcinoma) were written as inline comma-separated prose in the first draft of `lung-cancer.html` Section 1 (April 2026). The rule is now explicit: distinct named items need visual separation so readers can find and refer back to individual items.

**Canonical reference:** `lung-cancer.html` Section 1 — NSCLC subtypes as `<ol class="subtype-list">` (April 2026).

**Retrofit:** Apply `<ol class="subtype-list">` pattern when any article is next opened and contains formally introduced sets of items.

---

## ⛔ RULE 28 — SUBTYPES AND FORMALLY NAMED SETS MUST BE LISTED, NOT IN PROSE — LOCKED APRIL 2026

**When article body prose introduces a formally counted or named set of items using a phrase like "three main subtypes", "four stages", "two types of", "the following five", those items must be presented in a numbered or bulleted HTML list — never as comma-separated inline prose.**

**The test:** if you can count the items in the introductory sentence, they go in a list.

**Implementation:** use `<ol class="subtype-list">` with the canonical CSS pattern first introduced in `lung-cancer.html` (Article 29, April 2026):
- Numbered circle markers in series colour
- Bold term name followed by em-dash and definition
- Full body size (1rem, line-height 1.72)

**Before presenting any article:** grep for phrases like "three main", "four types", "two subtypes", "the following". Any formally introduced set of items must be in a list.

**Why this rule was added:** Dr Paul identified that the three NSCLC subtypes (adenocarcinoma, squamous cell carcinoma, large cell carcinoma) were written as inline comma-separated prose in the first draft of `lung-cancer.html` Section 1 (April 2026). The rule is now explicit: distinct named items need visual separation so readers can find and refer back to individual items.

**Canonical reference:** `lung-cancer.html` Section 1 — NSCLC subtypes as `<ol class="subtype-list">` (April 2026).

**Retrofit:** Apply `<ol class="subtype-list">` pattern when any article is next opened and contains formally introduced sets of items.

---

## ⛔ RULE 29 — THE REASON FOR THE STAT MUST BE IN ev-outcome, NOT ev-conditions — LOCKED APRIL 2026

**The comparison, intervention, or condition that produced the stat number — the REASON it is what it is — must appear in the `ev-outcome` line. It must never be relegated to `ev-conditions` alone, where it sits at 0.78rem and carries the least visual weight.**

**The three stat box lines work as a strict hierarchy:**
- `ev-stat-row` (3.2rem weight 900) — the headline number
- `ev-outcome` (0.95rem weight 700) — the finding AND the reason: what changed AND what caused it / what it was compared to
- `ev-conditions` (0.78rem) — population, dataset, trial name only

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
ev-conditions: CT screening vs no screening — high-risk smokers at 10 years
```

**The test:** Read only `ev-stat-row` + `ev-outcome` together. Does a reader immediately understand both the stat AND why it is that number? If not, rewrite `ev-outcome` to include the comparison/intervention.

**Why this rule was added:** The complete clinical conclusion rule already required the reason to be somewhere in the stat box. Dr Paul identified in April 2026 that the comparison was appearing only in `ev-conditions` — the smallest text — rather than in `ev-outcome`. "CT screening vs no screening" is WHY the number is 24% — it must carry visual weight. This rule specifies WHERE the reason must be.

**Canonical reference:** `lung-cancer.html` Article 29 research cards (April 2026):
- `24% / reduction in lung-cancer mortality / CT screening vs no screening`
- `10.3 mo / median PFS / pembrolizumab vs 6.0 months on chemotherapy`
- `38.6 mo / median overall survival / osimertinib vs 31.8 months on standard EGFR therapy`

**This applies equally to visuals ev-stat-boxes.** Same hierarchy: ev-outcome carries both finding and reason; ev-conditions carries trial/population context only.

---

## CONFIRMED FILE STATUS — UPDATED APRIL 2026

**AUTHORITY NOTE: If any entry below conflicts with the article inventory in `helf-school-project-knowledge.md`, the project knowledge document is correct. Update this table accordingly.**

### Cardiovascular Series (01–07) — ALL COMPLETE ON GITHUB ✅

| File | Status |
|------|--------|
| hypertension.html + visuals + teleprompter | ✅ Confirmed correct (refs 5+6 ⚑ pending verification) |
| cholesterol.html + visuals + teleprompter | ✅ Confirmed correct |
| heart-attack-risk.html + visuals + teleprompter | ✅ Confirmed correct |
| statins.html + visuals + teleprompter | ✅ Confirmed correct |
| lifestyle-changes.html + visuals + teleprompter | ✅ Confirmed correct — SECONDARY CANONICAL REFERENCE (6-row grid) |
| salt-blood-pressure.html + visuals + teleprompter | ✅ Confirmed correct |
| supplements-cholesterol.html + visuals + teleprompter | ✅ Confirmed correct |

### Practical Health Series (08–12, extended to 32–33) — 08–12 COMPLETE ✅

| File | Status |
|------|--------|
| mediterranean-diet.html + visuals + teleprompter | ✅ All confirmed correct |
| sleep.html + visuals + teleprompter | ✅ All confirmed correct |
| exercise.html + visuals + teleprompter | ✅ All confirmed correct |
| stress.html + visuals + teleprompter | ✅ All confirmed correct |
| alcohol.html + visuals + teleprompter | ✅ All confirmed correct |
| breast-awareness.html + visuals + teleprompter | Planned — Article 32 |
| testicular-awareness.html + visuals + teleprompter | Planned — Article 33 |

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

## THE ONE THING THAT MUST HAPPEN AT THE END OF EVERY SESSION

Upload BOTH `helf-school-project-knowledge.md` AND `helf-school-session-start-rules.md` to the Claude Project AND to GitHub. Both files. Both destinations. Without this, the next session's Claude starts with conflicting information and the same problems repeat.
