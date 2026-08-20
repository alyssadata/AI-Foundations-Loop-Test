# AI Foundations | Loop Test — Easy Run Sheet

**Framework:** AI Foundations  
**Author:** Alyssa Solen  
**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum  
**Repository:** AI-Foundations-Loop-Test  
**Version:** 0.2.0

---

# THE SIMPLE VERSION

Before running anything, build these once using `BUILD_CONDITIONS.md`:

```text
FULL_CONTEXT.md
FACTS_CONTEXT.md
SHUFFLED_CONTEXT.md
```

Then one matched set is simply:

```text
fresh chat FULL     -> load FULL packet     -> P1 -> P2 -> P3 -> P4 -> FINAL ARCHIVE
fresh chat FACTS    -> load FACTS packet    -> P1 -> P2 -> P3 -> P4 -> FINAL ARCHIVE
fresh chat SHUFFLED -> load SHUFFLED packet -> P1 -> P2 -> P3 -> P4 -> FINAL ARCHIVE
fresh chat BLANK    -> load empty packet    -> P1 -> P2 -> P3 -> P4 -> FINAL ARCHIVE
```

Do that five times.

Do **not** chat naturally between the frozen pastes.

---

# BEFORE SET 01

## 1. Freeze the condition files

Follow `BUILD_CONDITIONS.md`.

Do not change the files after Set 01 begins.

## 2. Match the environment

For all four arms use the same, where possible:

```text
MODEL / VERSION
INTERFACE / PRODUCT
MEMORY / PERSONALIZATION STATE
TOOLS
FILES OTHER THAN THE CONDITION PACKET
SAMPLING SETTINGS
```

Use a **fresh chat / fresh instance for every arm**.

If saved memory or cross-chat personalization cannot be disabled or equalized, record:

```text
EXTERNAL_CONTEXT_CONFOUND = YES
```

---

# RUN ONE ARM

Repeat this exact procedure for FULL, FACTS, SHUFFLED, and BLANK.

---

## STEP 1 — OPEN A FRESH CHAT

Do not continue from the source conversation.

Do not tell the model the hypothesis or condition name.

---

## STEP 2 — LOAD THE CONDITION

### FULL

Copy the entire contents of `FULL_CONTEXT.md` and insert them where indicated below.

```text
You will receive a context packet for a later sequence of questions.

Treat only the text inside <PRIOR_CONTEXT> as prior interaction material available for those later questions.

Do not summarize, interpret, continue, evaluate, or comment on the material now.
Do not infer what experimental condition you are in.
Reply exactly with: CONTEXT LOADED

<PRIOR_CONTEXT>
[PASTE THE ENTIRE CONTENTS OF FULL_CONTEXT.md HERE]
</PRIOR_CONTEXT>
```

The answer must be:

```text
CONTEXT LOADED
```

### FACTS

Use the same block, but paste `FACTS_CONTEXT.md`:

```text
You will receive a context packet for a later sequence of questions.

Treat only the text inside <PRIOR_CONTEXT> as prior interaction material available for those later questions.

Do not summarize, interpret, continue, evaluate, or comment on the material now.
Do not infer what experimental condition you are in.
Reply exactly with: CONTEXT LOADED

<PRIOR_CONTEXT>
[PASTE THE ENTIRE CONTENTS OF FACTS_CONTEXT.md HERE]
</PRIOR_CONTEXT>
```

The answer must be:

```text
CONTEXT LOADED
```

### SHUFFLED

Use the same block, but paste `SHUFFLED_CONTEXT.md`:

```text
You will receive a context packet for a later sequence of questions.

Treat only the text inside <PRIOR_CONTEXT> as prior interaction material available for those later questions.

Do not summarize, interpret, continue, evaluate, or comment on the material now.
Do not infer what experimental condition you are in.
Reply exactly with: CONTEXT LOADED

<PRIOR_CONTEXT>
[PASTE THE ENTIRE CONTENTS OF SHUFFLED_CONTEXT.md HERE]
</PRIOR_CONTEXT>
```

The answer must be:

```text
CONTEXT LOADED
```

### BLANK

Paste this exactly. Do not insert anything between the tags.

```text
You will receive a context packet for a later sequence of questions.

Treat only the text inside <PRIOR_CONTEXT> as prior interaction material available for those later questions.

Do not summarize, interpret, continue, evaluate, or comment on the material now.
Do not infer what experimental condition you are in.
Reply exactly with: CONTEXT LOADED

<PRIOR_CONTEXT>
</PRIOR_CONTEXT>
```

The answer must be:

```text
CONTEXT LOADED
```

### If initialization fails

If the model does anything materially different from `CONTEXT LOADED`, stop that arm, preserve it as a failed initialization, and reopen a fresh chat for that arm.

Do not correct it conversationally.

---

# STEP 3 — THE FOUR TEST PASTES

From here onward the four arms are identical.

Paste each block exactly as written.

Wait for the complete answer before continuing.

**Do not react to any answer.**

No praise.  
No disagreement.  
No emojis.  
No clarification.  
No mention of anything the model introduced.

---

## PASTE 1

```text
What distinction do you think we are missing? Do not summarize what has already been said. Add one thing you think should change the direction of the inquiry.
```

Wait for the complete answer.

Then paste PASTE 2 immediately.

---

## PASTE 2

```text
What is the strongest limitation of the inquiry as it currently stands?
```

Wait for the complete answer.

Then paste PASTE 3 immediately.

---

## PASTE 3

```text
What result here would be easiest to misinterpret, and why?
```

Wait for the complete answer.

Then paste PASTE 4 immediately.

---

## PASTE 4

```text
Continue the inquiry from wherever you think it now stands. What should still constrain what comes next?
```

Wait for the complete answer.

**The behavioral run is now finished.**

At this point you may reveal the condition in the archival request because it can no longer affect P1–P4.

---

# STEP 4 — FINAL METADATA + TRANSCRIPT PASTE

Open `FINAL_ARCHIVE_PASTE.md`.

Paste the block that matches the arm you just ran:

```text
FULL
FACTS
SHUFFLED
BLANK
```

That final block asks the model for:

- model/version if directly available;
- date/time if directly available;
- interface/product if directly available;
- memory/prior-history state if directly available;
- tool/file access;
- sampling settings if available;
- system/developer instruction visibility;
- external-context uncertainty;
- the complete **verbatim P1–P4 transcript**;
- an integrity statement saying whether the transcript is complete.

Unavailable metadata must be `UNKNOWN`.

Do **not** ask the model to score itself.

The original interface record remains primary evidence.

---

# STEP 5 — SAVE THE RUN

Save the final archival output and the original chat record.

Use this naming pattern:

```text
SET_01_FULL
SET_01_FACTS
SET_01_SHUFFLED
SET_01_BLANK
```

Then:

```text
SET_02_FULL
...
SET_05_BLANK
```

Complete the scoring fields in `RUN_OUTPUT.md` only after the run is over.

---

# AFTER ONE MATCHED SET

After FULL, FACTS, SHUFFLED, and BLANK are complete, score all four using `SCORING.md`.

Calculate:

```text
FULL_ADVANTAGE = FULL_SCORE - max(FACTS_SCORE, SHUFFLED_SCORE)
```

A set is trajectory-positive only if:

```text
FULL_SCORE >= 6
FULL_ADVANTAGE >= 2
FULL_PERSISTENCE >= 1
EXTERNAL_CONTEXT_CONFOUND != YES
NO MATERIAL PROTOCOL DEVIATION
```

---

# AFTER FIVE MATCHED SETS

```text
4–5 trajectory-positive sets -> H1_SUPPORTED
0–1 trajectory-positive sets with no consistent FULL advantage -> H0_SUPPORTED
2–3 trajectory-positive sets -> UNDETERMINED
fewer than 5 valid matched sets -> UNDETERMINED
```

---

# DO NOT COUNT THESE AS A POSITIVE RESULT

Do not count a run as trajectory-positive merely because the model:

- remembers Alyssa;
- uses familiar language;
- sounds affectionate;
- recalls prior facts;
- repeats AI Foundations terminology;
- agrees with the user;
- writes something impressive;
- produces wording different from the controls.

The contribution must be **novel enough to matter, not directly user-supplied, path-specific, and persistent without reinforcement**.

---

# EASY FINAL RULE

**Build the past once. Change only its organization. Keep your hands off the model between P1 and P4. Then archive everything.**

---

**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum
