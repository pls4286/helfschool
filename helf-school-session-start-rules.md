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

Section 3 of `helf-school-project-knowledge.md` contains the complete status of every article file. This table is maintained carefully and is accurate.

**The rule:** At the start of a session, Claude reads this table. Claude does not re-audit files that are marked ✅ unless Paul explicitly asks. Claude does not tell Paul that retrofit work needs doing if the project knowledge document says it has already been done.

---

## ⛔ RULE 6A — PROJECT KNOWLEDGE ALWAYS OVERRIDES THIS FILE ON STATUS

**THIS IS THE MOST IMPORTANT CONFLICT-RESOLUTION RULE.**

If the file status table in THIS document (session-start-rules.md) contradicts the article inventory in `helf-school-project-knowledge.md`, the project knowledge document is ALWAYS correct.

**Why this rule exists:** The status table in this file has repeatedly fallen out of sync with the project knowledge document because both files were not updated together at session end. Every time this happened, Claude defaulted to the wrong (outdated) information in this file and told Dr Paul that work had not been done when it had — causing repeated arguments and wasted time across multiple sessions in April 2026.

**The rule:** In any conflict between the two documents, project knowledge wins. Claude never flags outstanding work based on this file alone. Claude never says retrofits are undone if project knowledge says they are done.

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
2. Update THIS file (`helf-school-session-start-rules.md`) — especially the status table below
3. Paul downloads both via Artifact panel
4. Paul uploads BOTH to GitHub AND the Claude Project

**The rule:** Both files must be updated and uploaded together. If only one is updated, they fall out of sync and Rule 6A conflict will repeat. Claude prompts Paul to do this at the end of every productive session.

---

## ⛔ RULE 10 — NICE CG99 IS CHILDREN ONLY

Never cite NICE CG99 in any adult article. It covers constipation in children and young people only. The correct adult constipation reference is NICE CKS at cks.nice.org.uk/constipation. This rule exists because the error is easy to make and is clinically significant.

---

## CONFIRMED FILE STATUS — UPDATED APRIL 2026

**AUTHORITY NOTE: If any entry below conflicts with the article inventory in `helf-school-project-knowledge.md`, the project knowledge document is correct. Update this table accordingly.**

### Cardiovascular Series (01–07) — ALL COMPLETE ON GITHUB ✅
All article HTML, visuals, and teleprompter files confirmed correct.

| File | Status |
|------|--------|
| hypertension.html + visuals + teleprompter | ✅ Confirmed correct |
| cholesterol.html + visuals + teleprompter | ✅ Confirmed correct |
| heart-attack-risk.html + visuals + teleprompter | ✅ Confirmed correct |
| statins.html + visuals + teleprompter | ✅ Confirmed correct |
| lifestyle-changes.html + visuals + teleprompter | ✅ Confirmed correct — CANONICAL REFERENCE |
| salt-blood-pressure.html + visuals + teleprompter | ✅ Confirmed correct |
| supplements-cholesterol.html + visuals + teleprompter | ✅ Confirmed correct |

### Practical Health Series (08–12) — ALL COMPLETE ✅
Educational voice retrofit confirmed complete.

| File | Status |
|------|--------|
| mediterranean-diet.html + visuals + teleprompter | ✅ All confirmed correct |
| sleep.html + visuals + teleprompter | ✅ All confirmed correct |
| exercise.html + visuals + teleprompter | ✅ All confirmed correct |
| stress.html + visuals + teleprompter | ✅ All confirmed correct |
| alcohol.html + visuals + teleprompter | ✅ All confirmed correct |

### Digestive Health Series (13–21)

**Articles 13–20: ALL COMPLETE ON GITHUB ✅**
Article HTML retrofits confirmed complete. Visuals and teleprompters confirmed built. Educational voice retrofit confirmed complete.

| File | Status |
|------|--------|
| acid-reflux.html + visuals + teleprompter | ✅ All confirmed correct |
| ibd.html + visuals + teleprompter | ✅ All confirmed correct |
| bloating.html + visuals + teleprompter | ✅ All confirmed correct |
| ibs.html + visuals + teleprompter | ✅ All confirmed correct |
| masld.html + visuals + teleprompter | ✅ All confirmed correct |
| coeliac.html + visuals + teleprompter | ✅ All confirmed correct |
| gallstones.html + visuals + teleprompter | ✅ All confirmed correct |
| diverticular-disease.html + visuals + teleprompter | ✅ All confirmed correct |

**Article 21 — Constipation — IN PROGRESS**

| File | Status |
|------|--------|
| constipation.html | ✅ Built April 2026 — upload to GitHub |
| constipation-visuals.html | ✅ Built April 2026 — upload to GitHub |
| constipation-teleprompter.html | ✅ Built April 2026 — upload to GitHub |

### OUTSTANDING CITATION FLAGS
- hypertension.html refs 5 + 6 — Cochrane PubMed IDs flagged ⚑ unverified

### NEXT WORK
1. constipation-teleprompter.html — build after visuals confirmed
2. Neurological Series planning — define article list before any builds
3. hypertension.html refs 5 & 6 — verify when convenient

---

## THE ONE THING THAT MUST HAPPEN AT THE END OF EVERY SESSION

Upload BOTH `helf-school-project-knowledge.md` AND `helf-school-session-start-rules.md` to the Claude Project AND to GitHub. Both files. Both destinations. Without this, the next session's Claude starts with conflicting information and the same problems repeat.
