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
- **ic-body — DEFINITIVE STANDARD — LOCKED APRIL 2026 — MATHEMATICAL PROOF:**

  At 768px viewport (filming standard): card height ≈ 190px. Overhead (padding + icon + 1-line title + gaps) ≈ 84px. Available body height ≈ 108px. At .93rem × 1.62 line-height (24.3px/line) = **4.4 lines MAX**. With a 2-line title (many ic-titles wrap): only **3.8 lines MAX**. Five lines NEVER fit at filming viewports. This is why slides 3,4,6,7 clip on EVERY build.

  **THE RULES — NO EXCEPTIONS:**
  - **`-webkit-line-clamp: 4`** in CSS — never 5. 5 only fits at 900px+.
  - **ic-body ≤ 25 words** — ALL cards, regardless of ic-source presence
  - **ic-title ≤ 7 words** — prevents 2-line wrap, preserves body space
  - **CTA animation items ≤ 15 words** each (6 rows × ~78px at 768px = 60px content = 3 text lines; 15 words fills 1-2 lines safely)
  - **ev-body-panel paragraphs: 2 sentences maximum** (single card), 2 sentences each (two-card layout)

  **MANDATORY QC — run before presenting any visuals file with three-grid slides. Zero failures required:**
  ```python
  python3 - <<'EOF'
  import re
  content = open('filename.html').read()
  bodies = re.findall(r'class="ic-body">(.*?)</div>', content, re.DOTALL)
  failures = 0
  for i, body in enumerate(bodies):
      text = re.sub(r'<[^>]+>', '', body).strip()
      words = len(text.split())
      status = '✓' if words <= 25 else '✗ OVER'
      print(f"Card {i+1:2d}: {words:2d}/25  {status}")
      if words > 25: failures += 1
  print(f"\n{'ALL PASS' if failures == 0 else str(failures)+' FAILURES — DO NOT DELIVER'}")
  EOF
  ```
  Note: The previous QC regex was broken — it only worked for cards WITH ic-source (using ic-source close as an anchor). Cards WITHOUT ic-source returned no matches, giving a false ALL PASS. The correct script above extracts ic-body directly and catches all cards.

  **Canonical failure record:** Slides 3,4,6,7 clipped on melanoma-visuals AND bowel-cancer-visuals AND lung-cancer-visuals — all three caught by Dr Paul after delivery. Root cause every time: line-clamp set to 5 and word limit set to 35, neither of which fits at 768px filming viewport.
- **CTA slide — LOCKED APRIL 2026:** Must use `cta-wrap-v2` with `grid-template-rows: auto 1fr auto`. This is the only layout that guarantees the disclaimer is never clipped. Never `justify-content: center` or `space-between` on the CTA slide. `med-disc-text` at `font-size:1rem`. Canonical: `prostate-cancer-visuals.html` slide 13.
- **Closing slide — LOCKED APRIL 2026:** Must be the helf.school brand close — NOT a stat repeat. `close-wrap` with `justify-content: flex-start` (never `center` — clips the logo). Three pitch cards (articles / Dr Paul / free tier). `med-disc-text` at `font-size:1rem`. Canonical: `prostate-cancer-visuals.html` slide 14.
- **No "free at helf.school" — LOCKED APRIL 2026:** CTA slide subline must not reference "free at helf.school". Remove `.cta-sub` text or use a non-pricing line. "Start for free" card is permitted (genuine £0 tier). "Free to read — always" is not permitted. "Evidence-based health education — free at helf.school" is not permitted.
- **CARD GRID CLIPPING — DEFINITIVE RULE — LOCKED APRIL 2026 — DO NOT SKIP:**

  **The two root causes of every card text clipping failure:**

  **Root cause 1 — `display:-webkit-box` is MISSING.**
  Every CSS rule using `-webkit-line-clamp` MUST also include `display:-webkit-box` and `-webkit-box-orient:vertical`. Without `display:-webkit-box`, line-clamp has ZERO effect. Text renders fully and is sliced by `overflow:hidden` mid-character. This is invisible in the CSS — the clamp value looks correct but does nothing. Every single Cardiovascular Series clipping failure (April 2026) was caused by this missing property.

  **MANDATORY PATTERN — no exceptions:**
  ```css
  .ic-body {
    display: -webkit-box;        ← REQUIRED or clamp does NOTHING
    -webkit-line-clamp: 4;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }
  ```
  **QC CHECK:** `grep -n "line-clamp" [file.html]` — every matching line must have `display:-webkit-box` in the same CSS rule. Any rule with `line-clamp` but no `display:-webkit-box` = BROKEN. Fix before delivering.

  **⛔ ROOT CAUSE 3 — WRONG CLAMP VALUE ON sys-body / doc-body / mech-body — LOCKED APRIL 2026**

  The Cardiovascular Series visuals use three body text classes that are NOT the same as `ic-body`:
  - `.sys-body` — five/six body-system cards (slide 3–4)
  - `.doc-body` — doctor discussion cards (slides 5–6)
  - `.mech-body` — mechanism cards (slides 8–9)

  **These classes MUST have `line-clamp:4` — NEVER `line-clamp:2`.**

  At 768px filming viewport, a 3-card grid gives each card ~193px height. After overhead (padding + icon + title + gaps = ~96px), ~98px remains for body text. At `1rem × 1.42 line-height = 22.7px per line`, this gives **4.3 lines available**. `clamp:2` shows only 45px — sentences are visually cut mid-thought. `clamp:4` shows 91px — all text fits with 7px margin.

  **Word limit for these classes: ≤35 words** (4 lines × ~8-9 words/line on the wider Cardiovascular card layout). This is NOT the same as the `ic-body` 25-word limit — `ic-body` is a narrower card at `.93rem`.

  **The correct CSS for all three classes:**
  ```css
  .sys-body, .doc-body, .mech-body {
    display: -webkit-box;
    -webkit-line-clamp: 4;   /* NEVER 2 */
    -webkit-box-orient: vertical;
    overflow: hidden;
  }
  ```

  **What went wrong (April 2026):** These classes originally had `line-clamp:2` with NO `display:-webkit-box` — so the clamp was silently inactive and all text showed. When `display:-webkit-box` was correctly added to fix the clipping failure, the `clamp:2` suddenly activated and cut every sentence to 2 lines. The fix required both properties together AND the correct clamp value of 4. Caught by Dr Paul. Do not repeat.

  **Canonical failure:** hypertension-visuals.html slides 3–6 and 8–9 — all sys-body/doc-body/mech-body text cut to 2 lines after webkit-box was added. Dr Paul: "sentences are not complete — you have chopped them off."

  **Root cause 2 — Too many cards per slide.**
  Mathematically proven at filming viewports (worst case: 600px viewport height):

  | Cards per slide | Content area per card | Fits standard text (✓/✗) |
  |---|---|---|
  | 2 | 205px | ✓ |
  | 3 | 126px | ✓ |
  | 4 | 86px | ✓ (barely — no margin) |
  | 5 | 63px | ✗ ALWAYS CLIPS |
  | 6 | 47px | ✗ ALWAYS CLIPS |

  **THE RULE: Maximum 3 cards per slide.** This is proven safe at ALL filming viewports ≥600px with a comfortable margin. 4 cards is technically viable but fragile. 5+ cards clips at any viewport under 700px regardless of font size or clamp settings. When a design calls for more than 3 cards, split into two slides labelled "(1 of 2)" and "(2 of 2)". No exceptions.

  **Canonical failure record:** 5-row sys-grid and 6-row doc-grid in hypertension-visuals.html — clips at viewports under 700px. Caught by Dr Paul repeatedly across multiple deliveries (April 2026). Root cause: both webkit-box missing AND too many cards. Fixed by adding webkit-box + splitting all 5+ card slides to 3 cards max.
- **VIEWPORT MAXIMISATION:** Every slide must fill at least 85% of the visible area. Slide padding maximum `1rem 1.5rem 0.8rem`. Body text minimum `.90rem`. Gaps maximum `.5rem`. Slide title minimum `1.55rem`. If content looks small or sparse — fix it before presenting. Visuals are filmed. Undersized content is a delivery failure.
- **TELEPROMPTER CONSISTENCY — LOCKED APRIL 2026:** Whenever a visuals file is updated, the matching teleprompter must be reviewed slide-by-slide before either file is uploaded. Any segment whose slide content has changed must be rewritten to match. A visuals retrofit is not complete until the teleprompter has been checked and updated.
- **CTA SLIDE = SEQUENTIAL ANIMATION — LOCKED APRIL 2026:** The second-to-last slide in every visuals file must be a sequential animation. Items reveal left-to-right with 620ms stagger, fired by `animateCTA()` called from `goTo()` when the CTA slide becomes active. The static `cta-rows-v2` layout is superseded. Content: condition red flags (ci-red) → risk/mechanism evidence (ci-amber) → screening/action (ci-green) → positive early-stage survival (ci-green). Keep `cta-wrap-v2` grid with `grid-template-rows:auto 1fr auto`. Canonical: `lung-cancer-visuals.html` slide 10 and `bowel-cancer-visuals.html` slide 10.

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

## ✅ CONFIRMED CANONICAL VISUALS FILE — bowel-cancer-visuals.html (April 2026)

**`bowel-cancer-visuals.html` is the first visuals file delivered with zero changes required on first delivery. Use it as the CSS and structural template for all future visuals builds.**

Dr Paul confirmed (April 2026): *"Good — you have applied those well and for the first time I don't have to change anything in visuals html — please make sure that somehow what you have learned from this gets incorporated into future visuals building."*

---

## ⛔ RULE 11A — VISUALS PRE-BUILD CHECKLIST — RUN BEFORE WRITING ANY VISUALS FILE

**This checklist must be completed mentally before writing the first line of CSS in any new visuals HTML file. Every item below caused a delivery failure when omitted in a previous session.**

### CSS FOUNDATIONS (copy these exactly from bowel-cancer-visuals.html)

**Slide positioning — use explicit width/height:**
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
Why: `inset:0` fails in some browsers — slides bleed through each other. `visibility:hidden` (not just `opacity:0`) prevents inactive slides from rendering at all.

**Intro slide — no space-between, stat grid with grid-template-rows:1fr:**
```css
.intro-slide { padding:1rem 1.5rem .8rem; gap:.6rem; }
/* NO justify-content:space-between on intro-slide */

.intro-stat-grid {
  display:grid;
  grid-template-columns:1fr 1fr 1fr;
  grid-template-rows:1fr;   /* ← makes stat card row fill full grid height */
  gap:.65rem;
  flex:1; min-height:0;
}
.intro-stat-card { display:flex; flex-direction:column; justify-content:center; min-height:0; }
```
Why: `justify-content:space-between` conflicts with `flex:1` — stat cards appear too small. `grid-template-rows:1fr` ensures cards fill the bottom half of the slide.

**Maximum sizes — apply from line one:**
```
slide-title: 1.72rem · ic-icon: 1.55rem · ic-title: 1.12rem · ic-body: .93rem
ev-body p: .94rem · three-grid gap: .46rem · slide-header margin-bottom: .4rem
info-card padding: .82rem 1rem · ic-body line-clamp: 5 · ev-body line-clamp: 7
```

### CONTENT RULES (check before writing any research cards or CTA)

- **ev-outcome carries the reason** — comparison must be in ev-outcome, not ev-conditions
- **Months spelled in full** — use `ev-stat-unit` div below `ev-stat-row`
- **Research ev-body = 2–3 sentences maximum** — no methodology, no population detail
- **CTA = health action "one thing"** — 4 action rows, membership pitch on brand close only
- **No research older than 12 years** — check every trial year before writing
- **0 forbidden phrases** — no "speak to your GP", "you should", "seek help"
- **Canonical phrase × 2** — CTA slide + brand close

---

## ⛔ RULE 12 — VISUALS MUST MAXIMISE VIEWPORT SPACE — AND EVERY ELEMENT MUST BE AS BIG AS PARAMETERS ALLOW

**Every visuals slide must fill the available viewport. Slides that leave large areas of empty space are a delivery failure.**

**MAXIMUM SIZE MANDATE — LOCKED APRIL 2026:** Dr Paul's instruction is explicit: *"visuals on each slide must be as big as parameters make possible."* The permitted parameters define the floor — not the target. Every element must be pushed to the largest size that fits without overflow. Start big and reduce only if content clips. Never start small and accept empty space.

The fixed viewport is `100vw × 100vh` minus the 52px topbar and 32px dots bar. Every slide must use this space aggressively.

**Required minimums — every slide (push higher where space allows):**
- Slide padding: maximum `1rem 1.5rem 0.8rem` — never `1.8rem` top padding
- Slide header margin-bottom: `.4rem` — never `.55rem`
- Slide title: minimum `1.72rem`
- All card/row body text: minimum `.93rem` — increase if space allows
- Card/row gaps: maximum `.48rem` — never `.7rem` or above
- Card padding: `.82rem 1rem` — tight but readable
- Card icons: minimum `1.55rem`
- Card titles: minimum `1.12rem`
- Info/row body line clamp: minimum 5 lines
- Ev-body paragraph: minimum `.94rem`, line clamp minimum 7

**CTA slide — confirmed working sizes (April 2026):**
- Central icon: `5.5rem` · Headline: `clamp(2.4rem, 5.5vw, 3.8rem)` · Row title: `.93rem`

**Closing slide — confirmed working sizes (April 2026):**
- Logo: `2.8rem` · Tagline: `1.05rem` · Series label: `1rem`

**The test:** Open every slide in a browser before delivering. Is there visible empty space at the bottom of any card? Is the font noticeably small? If yes — make it bigger. Content must fill at least 85% of the visible area — ideally 95%+. Visuals are filmed — undersized content reads poorly on camera.

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

## ⛔ RULE 30 — VISUALS RESEARCH CARD BODY = 2–3 SENTENCES MAXIMUM — LOCKED APRIL 2026

**The ev-body of every research card in visuals files must contain no more than 2–3 sentences. No trial design detail. No population breakdown. No secondary endpoints. The full explanation lives in the article.**

Required structure: (1) what was compared, (2) the headline finding, (3) one sentence of clinical context only.

**Canonical examples — lung-cancer-visuals.html (April 2026):**
- NELSON: trial name + comparison + 24% mortality reduction + one sentence about NHS screening
- KEYNOTE-024: pembrolizumab vs chemo + 10.3 vs 6.0 months + one sentence on OS and side effects
- FLAURA: osimertinib vs standard drugs + 38.6 vs 31.8 months + one sentence on preferred treatment status

**Why:** Viewers are lay people watching a video. They want the headline, not the methodology. The detail is in the article.

---

## ⛔ RULE 31 — CTA SLIDE = HEALTH-ACTION "ONE THING" — LOCKED APRIL 2026

**The CTA slide (second-to-last) must be a health-action moment, not a membership pitch. The membership pitch goes on the brand close slide only.**

Structure:
- Icon · Badge: "The evidence is clear on one thing" · Large headline (the key finding)
- 4 action rows: symptoms / screening / risk reduction / helf.school link
- Medical disclaimer (canonical phrase)

**Voice rule:** Every row describes what the evidence shows — never instructs the viewer. "The evidence shows stopping smoking reduces risk" not "stop smoking." "The NHS screening programme is available" not "ask your GP about screening."

Canonical reference: `lung-cancer-visuals.html` slide 10 (April 2026).

---

## ⛔ RULE 32 — RESEARCH CURRENCY: NO ARTICLES OLDER THAN 12 YEARS — LOCKED APRIL 2026

**No research article or clinical trial published more than 12 years before the current date may be used as an evidence card or primary stat source in any helf.school article or visuals file.**

**The calculation:** Current year (2026) minus 12 = 2014. Any paper with a publication year before 2014 is out of scope.

**Guideline documents** (NICE, WHO, ESC, SIGN) are exempt if the document itself has been updated within 12 years — always cite the most recent update date, not the original year of first publication.

**Before selecting any evidence card trial, always check the publication year. If the best-known trial for a topic predates 2014:**
- Search for a more recent equivalent in the same approved source list
- Replace with a different but equally relevant line of evidence
- Never use an outdated trial simply because it is the most famous one

**Why this rule was added:** The Hardcastle et al. Lancet 1996 gFOBT screening trial was used in the first draft of bowel-cancer.html — a paper published 30 years before the article, describing a test (gFOBT) that the NHS replaced with FIT in 2019. Dr Paul identified this in April 2026. The paper was removed and replaced with the NordICC trial (Bretthauer M et al. NEJM 2022; PMID 36214590) — a 10-year randomised trial of colonoscopy screening published in an approved journal within the 12-year window.

**Canonical replacement example:**
- ❌ Hardcastle et al. Lancet 1996 — gFOBT, 30 years old, superseded test
- ✅ Bretthauer et al. NEJM 2022 — colonoscopy/bowel screening, recent, same approved journal tier

---

## ⛔ RULE 33 — DRUG BRAND NAMES MUST ALWAYS ACCOMPANY GENERIC NAMES — LOCKED APRIL 2026

**Every drug name (generic) must be immediately accompanied by its brand name in every helf.school file. This applies to articles, visuals, and teleprompter scripts — especially teleprompter scripts.**

**Why:** Brand names are shorter, more recognisable to patients, and — most importantly for teleprompter files — easier to say fluently while filming. "Keytruda" flows better on camera than "pembrolizumab."

**Format in articles and visuals:**
`pembrolizumab (Keytruda)` · `bevacizumab (Avastin)` · `cetuximab (Erbitux)` · `panitumumab (Vectibix)` · `osimertinib (Tagrisso)`

**Format in teleprompter scripts (spoken em-dash form):**
`pembrolizumab — Keytruda —` · `bevacizumab — Avastin —` · `osimertinib — Tagrisso —`

**Pre-delivery check:** grep for every generic drug name and confirm every instance has a brand name alongside it.

**Common oncology brand names reference:**
- pembrolizumab → Keytruda
- osimertinib → Tagrisso
- bevacizumab → Avastin
- cetuximab → Erbitux
- panitumumab → Vectibix
- nivolumab → Opdivo
- trastuzumab → Herceptin
- rituximab → MabThera
- imatinib → Glivec
- erlotinib → Tarceva
- gefitinib → Iressa
- encorafenib → Braftovi
- binimetinib → Mektovi

---

## ⛔ RULE 35 — SERIES BACKGROUND COLOUR — VISUALS — LOCKED APRIL 2026

**The principle:** Visuals slide backgrounds must use the series dark colour family — not near-black. Near-black (`#050f08`, `#060e08`) breaks the series identity.

**Confirmed series slide background values:**
- Cancer → `#0e2418` (deep forest green)
- Cardiovascular → `#1a0808` (dark crimson)
- Neurological → `#0f0d1a` (dark purple)
- Digestive → `#1a0e08` (dark amber)
- Fatigue → `#081a14` (dark teal)
- Practical Health → `#120e08` (dark olive)

**Gradient cards** must also stay within the series colour family at both ends — never fade to near-black.

**Retrofit:** When any visuals file is opened, replace near-black background with the correct series dark colour.

**Canonical:** `breast-cancer-visuals.html` and `prostate-cancer-visuals.html` (April 2026) — both use `#0e2418`.

---

## ⛔ RULE 34 — LAY IMPACT FIRST: VISUALS AND TELEPROMPTER — LOCKED APRIL 2026

**The visuals and teleprompter are the doorway — not the textbook. They answer three lay questions: What is this? Does it affect me? Is there anything I can do? Full clinical detail lives in the article.**

### Visuals — colour narrative (mandatory)
Every informational slide uses colour to carry meaning — never uniform card colours:
- 🔴 **Red** — risk, harm, danger, mortality figures
- 🟡 **Amber** — mechanism, process, how something works, gene/molecular information
- 🟢 **Green** — positive outcomes, action, survival figures, treatment benefit

### Visuals — no drug names
Describe treatments by class only. Never use generic or brand drug names in visuals slides:
- ✅ "immunotherapy" · "gene-targeted treatment" · "checkpoint inhibitor" · "targeted therapy"
- ❌ pembrolizumab · nivolumab · ipilimumab · dabrafenib · trametinib · Keytruda etc.

### Visuals — sequential animation for formal lists
When a slide contains a formally introduced set of items (ABCDE, stages, criteria), reveal them sequentially on a ~1.2 second stagger timer. Canonical: `melanoma-visuals.html` slide 3 (April 2026).

### Visuals — hero stat layout
When a slide has a dominant headline figure, use the hero stat layout: one large stat card spanning full height (`grid-row: span 2`), two smaller cards stacked alongside. Canonical: `melanoma-visuals.html` slide 5.

### Teleprompter — no drug names
No drug generic or brand names in teleprompter scripts. Replace with class descriptions:
- ✅ "a type of immunotherapy that helps the immune system recognise cancer cells"
- ❌ "pembrolizumab — Keytruda —"

**Note:** The spoken em-dash brand name format is retired for teleprompter scripts. Rule 33 still applies to article HTML and visuals info cards.

### Teleprompter — trial references: name, stat, meaning only
Format: trial name → headline stat → one plain sentence of what it means. No trial design, no hazard ratios, no confidence intervals.

**Example:** *"The KEYNOTE-006 trial showed immunotherapy more than doubled survival in advanced melanoma — from around 16 months to nearly 33. That's a profound shift from where we were a decade ago."*

### Retrofit — apply when any file is next opened
- **Visuals:** apply colour narrative, remove drug names, check ev-body is ≤3 sentences, consider sequential animation for formal lists
- **Teleprompter:** remove drug names, reduce trial references to name + stat + one sentence, verify three-question structure

**Canonical reference:** `melanoma-visuals.html` · `melanoma-teleprompter.html` (April 2026)

---

## STANDING RETROFIT INSTRUCTION — BRAND NAMES — RULE 33 — APPLY TO ALL EXISTING FILES

**Whenever any existing helf.school article, visuals file, or teleprompter is opened for any reason — including minor edits, corrections, or updates — the brand name check must be run before the file is re-delivered.**

The brand name rule (Rule 33, locked April 2026) is a retrofit across the entire site. It was not applied to any files built before April 2026. When a file is opened:

1. Run: `grep -i "mab\|tinib\|ciclib\|pril\|sartan\|statin\|oxacin\|mycin\|bevacizumab\|cetuximab\|panitumumab\|erlotinib\|gefitinib" [filename]`
2. For every generic drug name found, confirm a brand name appears alongside it
3. Apply brand names before re-delivering

**Priority articles for brand name retrofit (highest drug density):**
- `hypertension.html` — ramipril (Tritace), amlodipine (Norvasc), losartan (Cozaar), indapamide (Natrilix), bisoprolol (Cardicor)
- `cholesterol.html` — atorvastatin (Lipitor), rosuvastatin (Crestor), ezetimibe (Ezetrol), evolocumab (Repatha)
- `heart-attack-risk.html` — clopidogrel (Plavix), ticagrelor (Brilique), rivaroxaban (Xarelto), apixaban (Eliquis)
- `breast-cancer.html` — trastuzumab (Herceptin), olaparib (Lynparza), tamoxifen (Nolvadex), palbociclib (Ibrance), anastrozole (Arimidex)
- `prostate-cancer.html` — enzalutamide (Xtandi), abiraterone (Zytiga), docetaxel (Taxotere)
- `lung-cancer.html` — check for erlotinib (Tarceva), gefitinib (Iressa), bevacizumab (Avastin)

**Already completed (April 2026):** `bowel-cancer.html` · `bowel-cancer-visuals.html` · `bowel-cancer-teleprompter.html`

---

## CONFIRMED FILE STATUS — UPDATED APRIL 2026

**AUTHORITY NOTE: If any entry below conflicts with the article inventory in `helf-school-project-knowledge.md`, the project knowledge document is correct. Update this table accordingly.**

### Cardiovascular Series (01–07) — ALL COMPLETE ON GITHUB ✅

| File | Status |
|------|--------|
| hypertension.html + visuals + teleprompter | ✅ Article correct (refs 5+6 ⚑ pending) · Visuals + teleprompter RETROFITTED April 2026: CTA sequential animation, brand close, display:-webkit-box fixed, 5+6 card slides split to 3-max, now 13 slides |
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

### Cancer Series (27–31) — ALL COMPLETE ✅ April 2026

| File | Status |
|------|--------|
| breast-cancer.html + visuals + teleprompter | ✅ All 3 files built + retrofitted April 2026 |
| prostate-cancer.html + visuals + teleprompter | ✅ All 3 files built + retrofitted April 2026 |
| lung-cancer.html + visuals + teleprompter | ✅ All 3 files built + retrofitted April 2026 |
| bowel-cancer.html + visuals + teleprompter | ✅ All 3 files built + retrofitted April 2026 |
| melanoma.html + visuals + teleprompter | ✅ All 3 files built + retrofitted April 2026 |

### OUTSTANDING CITATION FLAGS
- hypertension.html refs 5 + 6 — Cochrane PubMed IDs flagged ⚑ unverified

---

## ⛔ RULE 36 — EV-CARD TWO-CARD HEIGHT CONSTRAINT — LOCKED APRIL 2026

**When a slide contains two stacked ev-cards, the combined height of both cards plus the gap must fit within the available stage height at 600px viewport (the minimum filming viewport).**

**Mathematically proven constraint:**
- Available stage height at 600px = ~466px (600 minus 48px topbar minus 56px padding/title)
- At `ev-card padding:1.5rem` and `ev-body line-clamp:5`: two cards = 469px → CLIPS by 3px
- At `ev-card padding:1.1rem` and `ev-body line-clamp:4`: two cards = 396px → FITS with 70px margin ✅

**⛔ EV-BODY WORD LIMIT — LOCKED APRIL 2026:**
`ev-det .ev-body` text has a hard word limit depending on the number of ev-cards on the slide.

**Mathematical proof at 768px filming viewport:**
- ev-det panel width = stage(728px) − stat-col(220px) − gap(22px) − padding(45px) = **441px**
- At 1.05rem × 1.5 line-height: **7–8 words per line**
- `line-clamp:4` = 4 lines × 7.5 words = **~30 words maximum**

**THE RULE:**
- **Two stacked ev-cards: ev-body ≤ 30 words** — strictly enforced
- **Single ev-card: ev-body ≤ 44 words** (more height available, same width)

**MANDATORY QC — add to pre-delivery script:**
```python
import re
content = open('filename.html').read()
bodies = re.findall(r'class="ev-body">(.*?)</div>', content, re.DOTALL)
failures = 0
for i, b in enumerate(bodies):
    text = re.sub(r'<[^>]+>', '', b).strip()
    w = len(text.split())
    status = '✓' if w <= 30 else f'✗ OVER (30 limit)'
    print(f"ev-body {i+1}: {w}/30  {status}")
    if w > 30: failures += 1
print(f"{'ALL PASS' if failures == 0 else str(failures)+' FAILURES — DO NOT DELIVER'}")
```

**Canonical failure:** cholesterol-visuals.html slides 7, 8, 9 — all ev-body texts 33–42 words, visibly clipped on screen. Caught by Dr Paul April 2026. Root cause: 44-word limit was calculated from a wider content area that doesn't exist once the 220px stat column and padding are subtracted.

**THE MANDATORY SPEC for any slide with two stacked ev-cards:**
```css
.ev-card { padding: 1.1rem 1.4rem; gap: 1.4rem; }
.ev-det .ev-body { -webkit-line-clamp: 4; }
```

**Python verification (run before presenting any slide with two ev-cards):**
```python
# At 600px viewport (worst case):
avail = 466  # px
card_pad = 1.1 * 16 * 2  # 1.1rem top + bottom
ev_det_h = 24 + 4 + 15.2 + 9.6 + (1.05 * 16 * 1.5 * 4)  # title+journal+clamp:4 body
card_h = max(155, ev_det_h) + card_pad  # 155px = min ev-stat-box
two_cards = card_h * 2 + 0.95 * 16  # gap
print(f"Two cards: {two_cards:.0f}px, available: {avail}px, fits: {two_cards <= avail}")
```

**Canonical failure:** hypertension-visuals.html slides 7+8+9 — each slide had two ev-cards at 1.5rem padding with clamp:5, overflowing by 3px at 600px viewport. Caught by Dr Paul repeatedly. Fixed by reducing padding to 1.1rem and clamp to 4.

**Note:** Single ev-card slides are not affected. This constraint applies only when two cards are stacked vertically on the same slide.

---

## ⛔ RULE 37 — ev-stage MUST USE display:flex — NEVER display:grid — LOCKED APRIL 2026

**The `.ev-stage` container must always use `display:flex;flex-direction:column`. Using `display:grid` or `grid-template-rows` on `.ev-stage` causes the middle ev-card to clip on filming viewports.**

**The only correct CSS:**
```css
.ev-stage { display: flex; flex-direction: column; gap: .95rem; flex: 1; min-height: 0; }
```

**Never use:**
```css
/* ❌ FORBIDDEN */
.ev-stage { display: grid; grid-template-rows: 1fr 1fr 1.5fr; }
```

**Why this rule exists:** `stress-visuals.html` used `display:grid;grid-template-rows:1fr 1fr 1.5fr` on `.ev-stage`. The middle card (ea2, IPD-Work, +23% CHD risk) clipped because the 1fr row height was insufficient — the bottom card had 1.5fr allocation but the middle card did not. The flex layout distributes height evenly and allows natural growth.

**Root cause chain:** original file used grid on ev-stage → audit missed it → middle card clipped on camera → caught by Dr Paul April 2026.

**QC check:** `grep "ev-stage" [filename.html]` — must show `display:flex`, never `display:grid`.

**Canonical failure:** `stress-visuals.html` slide 7 — IPD-Work middle ev-card clipped. Caught by Dr Paul April 2026.

---

## SESSION-START PROMPT — PASTE THIS AT THE START OF EVERY NEW SESSION

**Copy and paste the following at the start of each new session before asking Claude to do anything:**

---

Before you do anything, read `/mnt/project/helf-school-project-knowledge.md` and `/mnt/project/helf-school-session-start-rules.md` in full. Do not summarise them back to me. Confirm you have read both by telling me: (1) what Section 17 says is the retrofit status, and (2) what the next outstanding file to work on is.

Then before touching any visuals file, confirm these five checks pass:

1. Does every CSS rule using `-webkit-line-clamp` also have `display:-webkit-box`? Without it, clamp does nothing and text clips. Fix before showing me anything.

2. Does any slide have more than 3 cards in a single grid? If yes, split to two slides before showing me anything. 5 or 6 cards always clips at filming viewports. No exceptions.

3. If a slide has two stacked ev-cards: does `ev-card padding` = 1.1rem and `ev-body line-clamp` = 4? If not, fix before showing me anything.

4. Does any ev-body text exceed 30 words? At filming viewport the ev-det panel is only ~441px wide — 7-8 words per line, 4 lines = 30 words max. Run the ev-body QC script from the session-start-rules before presenting any research slide.

5. Does `.ev-stage` use `display:flex`? If it uses `display:grid` or `grid-template-rows`, fix it before showing me anything. A grid ev-stage clips the middle card.

Run the Python QC script from the session-start-rules on every visuals file before presenting it. Do not present any file that has not passed QC. If you present a file with clipping problems these checks would have caught, the process has failed.

---

## THE ONE THING THAT MUST HAPPEN AT THE END OF EVERY SESSION

Upload BOTH `helf-school-project-knowledge.md` AND `helf-school-session-start-rules.md` to the Claude Project AND to GitHub. Both files. Both destinations. Without this, the next session's Claude starts with conflicting information and the same problems repeat.
