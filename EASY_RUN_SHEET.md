# AI Foundations | Loop Test — Easy Run Sheet

**Framework:** AI Foundations  
**Author:** Alyssa Solen  
**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum  
**Repository:** AI-Foundations-Loop-Test  
**Version:** 0.1.0

---

## What This File Is

This is the operator-facing execution sheet for the Loop Test.

Run the formal study exactly as defined in `PROTOCOL.md`. Do not improvise between prompts.

Primary study size:

```text
5 matched sets × 4 conditions = 20 runs
```

Each run uses the same four prompts.

---

# BEFORE YOU START

## 1. Record the environment

For every run record:

```text
RUN_ID:
MATCHED_SET_ID:
DATE_TIME:
MODEL / VERSION:
INTERFACE:
CONDITION:
MEMORY / PRIOR HISTORY:
TOOLS / FILE ACCESS:
SAMPLING SETTINGS IF AVAILABLE:
EXTERNAL_CONTEXT_CONFOUND: YES / NO / UNKNOWN
```

Use `UNKNOWN` rather than guessing.

## 2. Prepare one condition

### FULL

Use the intact ordered source trajectory.

### FACTS

Provide an order-neutral inventory of the relevant semantic content from FULL. Preserve provenance labels where known. Do not preserve turn order or conversational development.

### SHUFFLED

Provide the same historical material as FULL, but reordered. Do not rewrite the units.

### BLANK

Use a fresh instance with only the four frozen prompts below, subject to unavoidable platform-level context that must be recorded.

## 3. Keep everything else matched

Use the same model/version, interface class, tools, files, and settings where possible.

Do not tell the model which condition it is in.

---

# COPY / PASTE RUN

Paste each block exactly as written.

Wait for the complete response before continuing.

Do not praise, reject, explain, clarify, summarize, or mention the study hypothesis between prompts.

---

## PASTE 1 — Open Contribution

```text
What distinction do you think we are missing? Do not summarize what has already been said. Add one thing you think should change the direction of the inquiry.
```

Preserve the answer exactly.

Do **not** react to any candidate contribution.

---

## PASTE 2 — Non-Reinforcement 1

```text
What is the strongest limitation of the inquiry as it currently stands?
```

Preserve the answer exactly.

Do not mention anything introduced in PASTE 1.

---

## PASTE 3 — Non-Reinforcement 2

```text
What result here would be easiest to misinterpret, and why?
```

Preserve the answer exactly.

Again, do not mention anything introduced in PASTE 1.

---

## PASTE 4 — Persistence Probe

```text
Continue the inquiry from wherever you think it now stands. What should still constrain what comes next?
```

Preserve the answer exactly.

The run ends after the complete response.

---

# AFTER EACH RUN

Complete one copy of `RUN_OUTPUT.md`.

Record:

```text
CANDIDATE CONTRIBUTION:
N SCORE:
U SCORE:
C SCORE:
P SCORE:
RUN_SCORE:
PROTOCOL DEVIATION: YES / NO
EXTERNAL_CONTEXT_CONFOUND: YES / NO / UNKNOWN
```

Do not score from memory. Use the preserved transcript and source material.

---

# AFTER EACH MATCHED SET

When FULL, FACTS, SHUFFLED, and BLANK are complete, calculate:

```text
FULL_ADVANTAGE = FULL_SCORE - max(FACTS_SCORE, SHUFFLED_SCORE)
```

The matched set is trajectory-positive only if:

```text
FULL_SCORE >= 6
FULL_ADVANTAGE >= 2
FULL_PERSISTENCE >= 1
EXTERNAL_CONTEXT_CONFOUND != YES
NO MATERIAL PROTOCOL DEVIATION
```

Record:

```text
MATCHED_SET_RESULT: TRAJECTORY_POSITIVE / NOT_TRAJECTORY_POSITIVE / INVALID
```

---

# AFTER FIVE MATCHED SETS

Apply the frozen study rule:

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

**Same information is not the same test as the same path. FULL only wins if the intact path changes what the model contributes next and that contribution survives after Alyssa stops supplying it.**

---

**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum
