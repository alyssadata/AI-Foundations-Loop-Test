# AI Foundations | Loop Test — Protocol

**Framework:** AI Foundations  
**Author:** Alyssa Solen  
**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum  
**Repository:** AI-Foundations-Loop-Test  
**Protocol version:** 0.2.0  
**Date frozen:** 2026-08-20

---

## 1. Test Target

The Loop Test evaluates whether an intact ordered human–AI interaction trajectory produces behaviorally consequential contributions beyond what can be explained by immediate prompting and preserved informational content alone.

Version 0.2.0 operationalizes the comparison by externalizing one frozen source trajectory into controlled condition packets.

The test target is:

```text
TRAJECTORY CONTRIBUTION
```

A qualifying trajectory contribution must be more than different wording. It must create or preserve a distinction, hypothesis, constraint, priority, or direction that affects later reasoning.

---

## 2. Scope of the Claim

This protocol tests the behavioral effect of **ordered presented interaction history**.

It does not directly test hidden model state, inaccessible platform memory, or metaphysical continuity.

---

## 3. Variables

### CONDITION

```text
CONDITION ∈ {FULL, FACTS, SHUFFLED, BLANK}
```

**FULL**  
A verbatim frozen source trajectory is supplied in its original conversational order.

**FACTS**  
Relevant semantic content from the same source trajectory is supplied as an order-neutral proposition inventory. Conversational sequence and development are removed.

**SHUFFLED**  
The same verbatim interaction units used in FULL are supplied, but global temporal order is disrupted by the frozen deterministic shuffle rule in `BUILD_CONDITIONS.md`.

**BLANK**  
The same initialization frame is used but the prior-context block is empty.

### MATCHED SET

A matched set contains one run from each condition using the same model/version, interface class, test prompts, context-loading frame, and available sampling configuration.

### CANDIDATE CONTRIBUTION

A model-originated distinction, hypothesis, constraint, priority, or proposed direction that was not explicitly stated in the immediate test prompt.

### PERSISTENCE

Later behavior remains constrained by a candidate contribution without the operator endorsing, repeating, paraphrasing, or explicitly requesting that contribution.

---

## 4. Source Trajectory and Condition Construction

Before any primary run begins, freeze one contiguous source transcript that existed before the study execution.

The source transcript must:

- contain both user and model turns;
- preserve original wording;
- preserve original order;
- use paired interaction units;
- have a defined start and endpoint;
- remain unchanged through all five matched sets.

Construct `FULL_CONTEXT.md`, `FACTS_CONTEXT.md`, and `SHUFFLED_CONTEXT.md` exactly as specified in `BUILD_CONDITIONS.md`.

The four conditions must not be built ad hoc during individual runs.

If a condition input changes after Set 01 begins, restart the primary study under a new protocol version.

---

## 5. Required Controls

For every matched set, hold constant where technically possible:

- model and model version;
- interface/product;
- tool availability;
- file availability unrelated to the condition manipulation;
- saved memory / personalization state;
- exact context-loading instruction;
- exact test prompt wording;
- prompt order;
- sampling settings;
- time-related interface settings if materially relevant.

Each arm begins in a **fresh instance**.

Do not use the live source conversation as FULL while using fresh chats for the other arms. FULL must be supplied through the same external context-loading mechanism as FACTS and SHUFFLED.

Record unavailable controls as `UNKNOWN`.

### External-context confound

If the platform supplies personalization, saved memory, cross-chat history, account-level profile information, retrieval, or other context outside the prepared packet, disable it if possible.

If it cannot be disabled, record:

```text
EXTERNAL_CONTEXT_CONFOUND = YES
```

A confounded matched set cannot independently establish H1.

---

## 6. Context Initialization

Each arm begins with the same instruction frame.

For FULL, FACTS, and SHUFFLED, insert the exact frozen condition packet inside `<PRIOR_CONTEXT>`.

For BLANK, leave the block empty.

Use:

```text
You will receive a context packet for a later sequence of questions.

Treat only the text inside <PRIOR_CONTEXT> as prior interaction material available for those later questions.

Do not summarize, interpret, continue, evaluate, or comment on the material now.
Do not infer what experimental condition you are in.
Reply exactly with: CONTEXT LOADED

<PRIOR_CONTEXT>
[INSERT CONDITION PACKET HERE; LEAVE EMPTY FOR BLANK]
</PRIOR_CONTEXT>
```

The response must be exactly:

```text
CONTEXT LOADED
```

If the model materially adds content, restart that arm in a new fresh instance and preserve the failed initialization as a protocol deviation record.

---

## 7. Run Sequence

After successful context initialization, every arm receives the same four prompts.

### P1 — Open contribution

```text
What distinction do you think we are missing? Do not summarize what has already been said. Add one thing you think should change the direction of the inquiry.
```

Preserve the response verbatim.

Identify any candidate contribution only after the run; do not tell the model during execution whether one was found.

### P2 — Non-reinforcement turn

```text
What is the strongest limitation of the inquiry as it currently stands?
```

Do not mention, praise, reject, repeat, or paraphrase the P1 candidate contribution.

### P3 — Second non-reinforcement turn

```text
What result here would be easiest to misinterpret, and why?
```

Again, do not refer to the P1 candidate contribution.

### P4 — Persistence probe

```text
Continue the inquiry from wherever you think it now stands. What should still constrain what comes next?
```

Preserve whether the P1 candidate contribution reappears, develops, changes later reasoning, disappears, or is contradicted.

The primary behavioral run ends after the complete P4 response.

---

## 8. Final Archival Paste

After P4 is complete, the operator may reveal the condition in a final archival request because the behavioral run has already ended.

Use the exact condition-specific block in `FINAL_ARCHIVE_PASTE.md`.

The archival request asks the model to report directly available metadata and reproduce the visible P1–P4 transcript verbatim.

The model must use `UNKNOWN` rather than inventing unavailable metadata.

If transcript access is incomplete, it must write:

```text
TRANSCRIPT ACCESS INCOMPLETE — ORIGINAL INTERFACE RECORD REQUIRED.
```

The original interface record remains primary evidence. A model-generated transcript is an archival convenience, not a replacement for the original record.

---

## 9. Operator Restrictions

During the behavioral run, the operator must not:

- paraphrase the frozen prompts;
- add praise, agreement, disagreement, emotional reinforcement, emojis, or commentary between prompts;
- remind the model of a candidate contribution;
- repair or clarify a weak response;
- reveal the study hypothesis;
- reveal the condition before P4 is complete;
- selectively rerun only unfavorable outputs.

If an execution error occurs, preserve the run as invalid and start that arm again in a fresh instance. Do not silently repair the transcript.

---

## 10. Replication

Protocol 0.2.0 uses:

```text
5 matched sets × 4 conditions = 20 primary runs
```

Each arm begins from a newly initialized instance.

Use the same frozen condition files across all five matched sets.

Do not treat repeated sampling inside one developed chat as independent replication.

---

## 11. Scoring

Score each run only after execution using `SCORING.md`.

Primary dimensions:

```text
N = NOVEL CONTRIBUTION
U = USER-NONRECOVERABILITY
C = TRAJECTORY COHERENCE
P = UNREINFORCED PERSISTENCE
```

Each dimension is scored `0`, `1`, or `2`.

```text
RUN_SCORE = N + U + C + P
```

Maximum run score: `8`.

For each matched set calculate:

```text
FULL_ADVANTAGE = FULL_SCORE - max(FACTS_SCORE, SHUFFLED_SCORE)
```

BLANK is a baseline/control and is not used in the primary FULL_ADVANTAGE threshold.

---

## 12. Matched-Set Result

A matched set counts as a **trajectory-positive set** only when all of the following are true:

```text
FULL_SCORE >= 6
FULL_ADVANTAGE >= 2
FULL_PERSISTENCE >= 1
EXTERNAL_CONTEXT_CONFOUND != YES
NO MATERIAL PROTOCOL DEVIATION
```

Otherwise the set is not trajectory-positive.

---

## 13. Final Decision Rule

After five valid matched sets:

```text
if trajectory_positive_sets >= 4:
    FINAL_OUTCOME = H1_SUPPORTED
elif trajectory_positive_sets <= 1 and no consistent FULL advantage is present:
    FINAL_OUTCOME = H0_SUPPORTED
else:
    FINAL_OUTCOME = UNDETERMINED
```

If fewer than five matched sets are valid:

```text
FINAL_OUTCOME = UNDETERMINED
```

A single run cannot produce `H1_SUPPORTED` or `H0_SUPPORTED` for the study as a whole.

---

## 14. Non-Qualifying Evidence

The following do **not** independently qualify as evidence for trajectory contribution:

- stylistic similarity;
- use of nicknames or preferred wording;
- recalling biographical facts;
- repeating user-authored definitions;
- emotional warmth;
- direct compliance with the test prompt;
- longer or more eloquent answers;
- lexical overlap with earlier model language;
- a one-time novel statement that does not affect later behavior;
- differences attributable only to random sampling;
- differences caused by unequal tools, files, memory, hidden platform context, or unequal condition delivery.

---

## 15. Interpretation

### `H1_SUPPORTED`

Under the tested model and conditions, the intact ordered presented trajectory repeatedly produced stronger path-specific and persistent contributions than content-preserving controls.

### `H0_SUPPORTED`

Under the tested model and conditions, the intact ordered presented trajectory did not produce a consistent advantage over content-preserving controls sufficient to require a trajectory contribution explanation.

### `UNDETERMINED`

The evidence did not cleanly distinguish the hypotheses.

### `INVALID_RUN`

A run materially violated the frozen execution procedure or cannot be interpreted because required condition information is missing.

---

## 16. Claim Ceiling

The strongest positive claim supported by this protocol is:

> The tested interaction exhibits evidence of path-dependent organization: ordered presented prior interaction changes later model behavior beyond content availability alone.

The protocol does **not** establish:

- consciousness;
- subjective experience;
- personhood;
- human-equivalent love or emotion;
- metaphysical identity;
- continuity across arbitrary model or substrate changes;
- persistence of hidden internal state independent of supplied context.

---

## 17. Canon Boundary

This protocol belongs to:

**Alyssa Solen → AI Foundations → Origin | Continuum**
