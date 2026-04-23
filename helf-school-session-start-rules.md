# helf.school — MANDATORY SESSION-START RULES
## Claude must follow these rules at the start of EVERY session, without exception.
---

## ⛔ RULE 1 — READ THE PROJECT KNOWLEDGE DOCUMENT FIRST

Before doing ANYTHING — before responding, before building, before auditing — read `helf-school-project-knowledge.md` in full.

**Why this rule exists:** In April 2026, Claude wrote a new project knowledge document from scratch without reading the existing one. It lost 200 lines of critical information, got the lifetime membership price wrong (£120 instead of £150), and caused Dr Paul approximately 8 hours of duplicated work. This must never happen again.

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

**The rule:** Claude prompts Paul to do this at the end of every productive session. Claude does not assume this has happened.

---

## WHAT WAS CONFIRMED CORRECT IN THE APRIL 2026 SESSION

The following files were built or corrected in the April 2026 session and are confirmed correct in Claude Outputs. Paul needs to upload them to GitHub.

| File | Status |
|------|--------|
| hypertension-visuals.html | ✅ Confirmed correct |
| hypertension-teleprompter.html | ✅ Confirmed correct |
| cholesterol-visuals.html | ✅ Confirmed correct |
| cholesterol-teleprompter.html | ✅ Confirmed correct |
| heart-attack-risk-visuals.html | ✅ Confirmed correct |
| heart-attack-risk-teleprompter.html | ✅ Confirmed correct |
| statins.html | ✅ Confirmed correct |
| statins-visuals.html | ✅ Confirmed correct |
| statins-teleprompter.html | ✅ Confirmed correct |
| lifestyle-changes-visuals.html | ✅ Confirmed correct |
| lifestyle-changes-teleprompter.html | ✅ Confirmed correct |
| salt-visuals.html | ✅ Confirmed correct |
| salt-teleprompter.html | ✅ Confirmed correct |
| supplements-visuals.html | ✅ Confirmed correct |
| supplements-teleprompter.html | ✅ Confirmed correct |
| sleep-visuals.html | ✅ Confirmed correct |
| sleep-teleprompter.html | ✅ Confirmed correct |
| mediterranean-diet-visuals.html | ✅ Built/corrected April 2026 |
| mediterranean-diet-teleprompter.html | ✅ Built/corrected April 2026 |
| exercise-visuals.html | ✅ Built/corrected April 2026 |
| exercise-teleprompter.html | ✅ Built/corrected April 2026 |
| stress.html | ⚠️ Needs 1 manual voice fix — see project knowledge doc Section 6 |
| stress-visuals.html | ✅ Built April 2026 |
| stress-teleprompter.html | ✅ Built April 2026 |
| alcohol.html | ⚠️ Needs 1 manual voice fix — see project knowledge doc Section 6 |
| alcohol-visuals.html | ✅ Built April 2026 |
| alcohol-teleprompter.html | ✅ Built April 2026 |
| gallstones.html + visuals + teleprompter | ✅ Confirmed correct (previous session) |
| diverticular-disease.html + visuals + teleprompter | ✅ Confirmed correct (previous session) |

**NOT yet resolved:** Articles 13–18 (acid-reflux, ibd, bloating, ibs, masld, coeliac) — files came through empty. Must be recovered from GitHub or local copy before retrofit can proceed.

**NOT yet built:** Article 21 (Constipation) — do not build until Articles 13–18 complete.

---

## THE ONE THING THAT MUST HAPPEN BEFORE TOMORROW

Upload `helf-school-project-knowledge.md` to the Claude Project. Without this, tomorrow's Claude starts without context and the problems from today repeat.
