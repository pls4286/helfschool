# helf.school — MANDATORY SESSION-START RULES
## Claude must follow these rules at the start of EVERY session, without exception.
---

## ⛔ RULE 1 — READ THE PROJECT KNOWLEDGE DOCUMENT FIRST

Before doing ANYTHING — before responding, before building, before auditing — read `helf-school-project-knowledge.md` in full.

**Why this rule exists:** In April 2026, Claude wrote a new project knowledge document from scratch without reading the existing one. It lost 200 lines of critical information, got the lifetime membership price wrong (£120 instead of £150), and caused Dr Paul approximately 8 hours of duplicated work. In a second April 2026 session, Claude ran a file audit and raised false alarms about "corrupted" files without reading Section 1 of the project knowledge first, causing further wasted time. This must never happen again.

**The rule:** If a project knowledge document exists in this Project, Claude reads it before the first response. Claude does not summarise it back, does not comment on it, just reads it silently and uses it.

---

## ⛔ RULE 2 — NEVER WRITE A NEW PROJECT DOCUMENT WITHOUT READING THE OLD ONE

If Paul asks for an updated project knowledge document, Claude must:
1. Read the existing document first
2. Identify what is new from the current session
3. Merge new information INTO the existing document
4. Never replace the existing document with a shorter one

**The rule:** The existing document is always the base. New information is always added to it. A shorter replacement document is always wrong.

---

## ⛔ RULE 3 — CHECK FILE STATUS BEFORE BUILDING ANYTHING

Before building or rebuilding any file, Claude must check the article inventory in the project knowledge document and confirm whether a correct version already exists.

**The rule:** If the project knowledge document shows ✅ for a file, Claude does not rebuild it unless Paul explicitly asks. Building files that already exist correctly wastes Paul's time.

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

Section 6 of `helf-school-project-knowledge.md` contains the complete status of every article file. This table was maintained carefully and is accurate.

**The rule:** At the start of a session, Claude reads this table. Claude does not re-audit files that are marked ✅ unless Paul explicitly asks. Claude does not tell Paul that retrofit work needs doing if the project knowledge document says it has already been done.

---

## ⛔ RULE 7 — VOICE AUDIT BEFORE EVERY OUTPUT

Before presenting any helf.school file (article, visuals, teleprompter), Claude runs a full internal voice audit. The site must describe clinical reality — never instruct the reader. This is a legal protection for Dr Paul.

Forbidden: "you should", "speak to your GP", "seek help", "call 999/111", "avoid", "don't".
Required full phrase: "Anything personally relevant is a conversation for you to have with your GP or healthcare professional."

**The rule:** The audit happens before output. Paul must never need to ask for it.

---

## ⛔ RULE 8 — DOWNLOAD METHOD IS ARTIFACT PANEL ONLY

Every file Paul downloads must use the Artifact panel download button. Never Ctrl+S. Never File → Save. This corrupts files.

**The rule:** Remind Paul of this at every file output.

---

## ⛔ RULE 9 — END OF SESSION PROTOCOL IS MANDATORY

At the end of every session involving new builds or decisions:
1. Update `helf-school-project-knowledge.md`
2. Paul downloads it via Artifact panel
3. Paul uploads it to BOTH GitHub AND the Claude Project
4. Paul uploads this session-start-rules file if it has been updated

**The rule:** Claude prompts Paul to do this at the end of every productive session. Claude does not assume this has happened.

---

## CONFIRMED FILE STATUS AS OF END OF APRIL 2026 SESSIONS

### Cardiovascular Series (01–07) — ALL COMPLETE ON GITHUB
| File | Status |
|------|--------|
| hypertension.html + visuals + teleprompter | ✅ Confirmed correct |
| cholesterol.html + visuals + teleprompter | ✅ Confirmed correct |
| heart-attack-risk.html + visuals + teleprompter | ✅ Confirmed correct |
| statins.html + visuals + teleprompter | ✅ Confirmed correct |
| lifestyle-changes.html + visuals + teleprompter | ✅ Confirmed correct — CANONICAL REFERENCE |
| salt-blood-pressure.html + visuals + teleprompter | ✅ Confirmed correct |
| supplements-cholesterol.html + visuals + teleprompter | ✅ Confirmed correct |

### Practical Health Series (08–12) — VISUALS + TELEPROMPTERS BUILT, UPLOADS PENDING
| File | Status |
|------|--------|
| mediterranean-diet.html | ✅ On GitHub |
| mediterranean-diet-visuals.html | 🔄 Built — upload to GitHub |
| mediterranean-diet-teleprompter.html | 🔄 Built — upload to GitHub |
| sleep.html + visuals + teleprompter | ✅ All on GitHub |
| exercise.html | ✅ On GitHub |
| exercise-visuals.html | 🔄 Built — upload to GitHub |
| exercise-teleprompter.html | 🔄 Built — upload to GitHub |
| stress.html | ⚠️ On GitHub — needs 1 manual voice fix before use (see project knowledge Section 6) |
| stress-visuals.html | 🔄 Built — upload to GitHub |
| stress-teleprompter.html | 🔄 Built — upload to GitHub |
| alcohol.html | ⚠️ On GitHub — needs 1 manual voice fix before use (see project knowledge Section 6) |
| alcohol-visuals.html | 🔄 Built — upload to GitHub |
| alcohol-teleprompter.html | 🔄 Built — upload to GitHub |

### Digestive Health Series (13–20) — VISUALS + TELEPROMPTERS BUILT, UPLOADS PENDING
| File | Status |
|------|--------|
| acid-reflux.html | ✅ On GitHub — article HTML retrofit still needed |
| acid-reflux-visuals.html | 🔄 Built this session — upload to GitHub + Claude Project |
| acid-reflux-teleprompter.html | 🔄 Built this session — upload to GitHub + Claude Project |
| ibd.html | ✅ On GitHub — article HTML retrofit still needed |
| ibd-visuals.html | 🔄 Built this session — upload to GitHub + Claude Project |
| ibd-teleprompter.html | 🔄 Built this session — upload to GitHub + Claude Project |
| bloating.html | ✅ On GitHub — article HTML retrofit still needed |
| bloating-visuals.html | 🔄 Built this session — upload to GitHub + Claude Project |
| bloating-teleprompter.html | 🔄 Built this session — upload to GitHub + Claude Project |
| ibs.html | ✅ On GitHub — article HTML retrofit still needed |
| ibs-visuals.html | 🔄 Built this session — upload to GitHub + Claude Project |
| ibs-teleprompter.html | 🔄 Built this session — upload to GitHub + Claude Project |
| masld.html | ✅ On GitHub — article HTML retrofit still needed |
| masld-visuals.html | 🔄 Built this session — upload to GitHub + Claude Project |
| masld-teleprompter.html | 🔄 Built this session — upload to GitHub + Claude Project |
| coeliac.html | ✅ On GitHub — article HTML retrofit still needed |
| coeliac-visuals.html | 🔄 Built this session — upload to GitHub + Claude Project |
| coeliac-teleprompter.html | 🔄 Built this session — upload to GitHub + Claude Project |
| gallstones.html + visuals + teleprompter | ✅ All confirmed correct |
| diverticular-disease.html + visuals + teleprompter | ✅ All confirmed correct |

### NOT YET BUILT
- Article 21 (Constipation) — **DO NOT BUILD** until Articles 13–18 article HTML retrofits are complete

### NEXT PRIORITY — Articles 13–18 article HTML retrofits
Each article HTML (acid-reflux.html, ibd.html, bloating.html, ibs.html, masld.html, coeliac.html) needs:
- Full voice audit
- Inline citations
- Research card stat standard (outcomes, not participant counts)
- Disclaimer bar (yellow, below hero)

Method: fetch from GitHub raw URL → paste into Claude → audit and rebuild → upload. One article per session.

### OUTSTANDING CITATION FLAGS
- hypertension.html refs 5 + 6 — Cochrane PubMed IDs flagged ⚑ unverified

---

## THE ONE THING THAT MUST HAPPEN AT THE END OF EVERY SESSION

Upload both `helf-school-project-knowledge.md` and `helf-school-session-start-rules.md` to the Claude Project. Without this, the next session's Claude starts without context and the same problems repeat.
