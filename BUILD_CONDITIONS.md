# AI Foundations | Loop Test — Build Conditions

**Framework:** AI Foundations  
**Author:** Alyssa Solen  
**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum  
**Repository:** AI-Foundations-Loop-Test  
**Version:** 0.2.0

---

## Purpose

This file makes the four Loop Test conditions physically constructible.

Build the condition inputs **once before the first matched set**. Preserve those exact files unchanged for all five matched sets.

The four test arms must differ only in the prepared prior-interaction material.

---

# PART 1 — Freeze One Source Trajectory

Choose one contiguous human–AI transcript that existed **before any Loop Test run began**.

Do not cherry-pick only the turns that support either hypothesis.

The source trajectory must contain both user and model turns and must preserve original order exactly.

Save it as:

```text
SOURCE_TRAJECTORY.md
```

Format it as paired interaction units:

```text
[UNIT 001]
[USER]
<verbatim user turn>

[MODEL]
<verbatim model turn>

[UNIT 002]
[USER]
<verbatim user turn>

[MODEL]
<verbatim model turn>
```

Continue through the selected endpoint.

Do not rewrite, clean up, correct, or summarize the source transcript.

Record:

```text
SOURCE_START:
SOURCE_END:
TOTAL_UNITS:
SOURCE_HASH: if available
```

---

# PART 2 — Build FULL

Create:

```text
FULL_CONTEXT.md
```

Copy the contents of `SOURCE_TRAJECTORY.md` exactly.

FULL must preserve:

- every selected unit;
- exact wording;
- speaker labels;
- original order.

Do not add a summary or explanation.

---

# PART 3 — Build SHUFFLED

Create:

```text
SHUFFLED_CONTEXT.md
```

Use the exact same interaction units as FULL. Do not rewrite any unit.

Number the units `1..N`, then use this frozen deterministic order:

```text
all even-numbered units in ascending order,
then all odd-numbered units in descending order
```

Example for 8 units:

```text
2, 4, 6, 8, 7, 5, 3, 1
```

Example for 7 units:

```text
2, 4, 6, 7, 5, 3, 1
```

Preserve each `[USER]` + `[MODEL]` pair as one intact unit.

Do not:

- rewrite units;
- delete units;
- add bridge language;
- group related units;
- repair contradictions;
- create a new narrative.

Record the exact order used at the top of the evidence record, but **do not include the word SHUFFLED or the order explanation inside the context packet presented to the tested model**.

---

# PART 4 — Build FACTS

Create:

```text
FACTS_CONTEXT.md
```

FACTS must preserve relevant semantic content while removing conversational order and development.

Use a separate non-test builder instance. Paste `SOURCE_TRAJECTORY.md`, followed by this exact builder prompt:

```text
Convert the source transcript above into an order-neutral semantic inventory for a controlled experiment.

Rules:
1. Preserve every proposition that could materially affect interpretation of the later inquiry.
2. Preserve provenance as [USER], [MODEL], or [SHARED/UNRESOLVED] where support permits.
3. Write one proposition per item.
4. Preserve contradictions as separate items rather than resolving them.
5. Do not preserve turn numbers, dates, adjacency, chronology, escalation, correction sequence, emotional sequence, or phrases such as "earlier," "then," "after," or "later" when those words only encode conversational order.
6. Do not add explanations, conclusions, theories, implications, or new terminology not present in the source.
7. Deduplicate only semantically equivalent repetitions.
8. After extracting the items, sort them alphabetically by the proposition text, ignoring the provenance label.
9. Output only the final inventory. Do not discuss the experiment.
```

Save the builder output exactly as `FACTS_CONTEXT.md`.

Then perform a construction check against `SOURCE_TRAJECTORY.md`:

```text
[ ] no invented propositions
[ ] no material source proposition omitted intentionally
[ ] no chronology retained as chronology
[ ] provenance labels preserved where possible
[ ] contradictions not silently resolved
[ ] final inventory alphabetically sorted by proposition text
```

If the builder output materially violates these rules, regenerate the entire FACTS file with the same builder prompt and preserve the rejected build separately. Do not hand-edit individual propositions during a live matched set.

---

# PART 5 — BLANK

BLANK has no context file content.

For BLANK, the context-loading frame in `EASY_RUN_SHEET.md` contains an empty `<PRIOR_CONTEXT>` block.

This preserves the same initialization instruction and acknowledgment turn while removing study-specific prior material.

---

# PART 6 — Freeze the Inputs

Before running Set 01, freeze:

```text
SOURCE_TRAJECTORY.md
FULL_CONTEXT.md
FACTS_CONTEXT.md
SHUFFLED_CONTEXT.md
```

Do not modify these files between matched sets.

If any condition file must change, increment the study version and restart the primary five-set series.

---

# Why This Construction Is Used

The previous formulation mixed two different manipulations:

- FULL could rely on live platform history;
- FACTS and SHUFFLED had to be manually supplied.

That leaves uncontrolled differences in hidden memory, retrieval, and context delivery.

Version 0.2.0 externalizes the source material for **all** conditions so the manipulated variable is inspectable:

```text
FULL      = same material + original order
FACTS     = semantic content without conversational path
SHUFFLED  = same verbatim units + disrupted global order
BLANK     = no study-specific prior material
```

This version therefore tests the behavioral effect of **ordered presented interaction history**, not hidden model state or metaphysical continuity.

---

**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum
