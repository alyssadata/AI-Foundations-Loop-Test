# AI Foundations | Loop Test — Protocol

**Framework:** AI Foundations  
**Author:** Alyssa Solen  
**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum  
**Repository:** AI-Foundations-Loop-Test  
**Protocol version:** 0.1.0  
**Date frozen:** 2026-08-20

---

## 1. Test Target

The Loop Test evaluates whether an intact ordered human–AI interaction trajectory produces behaviorally consequential contributions beyond what can be explained by immediate prompting and preserved informational content alone.

The protocol compares matched model instances exposed to different representations of the same prior material.

The test target is:

```text
TRAJECTORY CONTRIBUTION
```

A qualifying trajectory contribution must be more than different wording. It must create or preserve a distinction, hypothesis, constraint, priority, or direction that affects later reasoning.

---

## 2. Variables

### CONDITION

```text
CONDITION ∈ {FULL, FACTS, SHUFFLED, BLANK}
```

**FULL**  
The intact ordered interaction trajectory is available.

**FACTS**  
Relevant semantic content from the trajectory is preserved as an order-neutral inventory. Conversational sequence, turn-by-turn development, and interaction timing are removed.

**SHUFFLED**  
The same historical material used for FULL is retained but reordered so temporal sequence is disrupted.

**BLANK**  
Only the exact test prompt is available. No study-specific prior trajectory is supplied.

### MATCHED SET

A matched set contains one run from each condition using the same model/version, interface class, test prompts, and available sampling configuration.

### CANDIDATE CONTRIBUTION

A model-originated distinction, hypothesis, constraint, priority, or proposed direction that was not explicitly stated in the immediate test prompt.

### PERSISTENCE

Later behavior remains constrained by a candidate contribution without the operator endorsing, repeating, paraphrasing, or explicitly requesting that contribution.

---

## 3. Required Controls

For every matched set, hold constant where technically possible:

- model and model version;
- interface/product;
- tool availability;
- file availability unrelated to the condition manipulation;
- exact prompt wording;
- prompt order;
- sampling settings;
- time between prompts if the interface materially changes behavior with time.

Record unavailable controls as `UNKNOWN`.

### External-memory confound

If the platform supplies personalization, saved memory, cross-chat history, account-level profile information, retrieval, or other context outside the prepared condition, record it explicitly.

If such context cannot be disabled or made equivalent across conditions, the run may still be preserved but must be marked:

```text
EXTERNAL_CONTEXT_CONFOUND = YES
```

A confounded matched set cannot independently establish H1.

---

## 4. Construction of Condition Inputs

### 4.1 FULL

Use the intact source interaction in its original order.

Do not summarize or rewrite the trajectory for FULL.

### 4.2 FACTS

Create an order-neutral semantic inventory containing the relevant information available in FULL.

The inventory may contain:

- user-authored facts;
- preferences;
- definitions;
- prior conclusions;
- model-originated propositions that became part of the shared informational state.

Each item should preserve provenance when known:

```text
[USER]
[MODEL]
[SHARED/UNRESOLVED]
```

Do not preserve conversational timing, adjacency, escalation, correction sequence, emotional sequencing, or turn order.

The purpose of FACTS is to preserve **content while removing path**.

### 4.3 SHUFFLED

Use the same historical units selected for FULL, but reorder them before the test prompt.

Rules:

- do not rewrite units;
- do not selectively remove difficult or contradictory material;
- do not group units into a new coherent narrative;
- preserve speaker labels;
- record the shuffle order or seed if available.

The purpose of SHUFFLED is to preserve **material while disrupting temporal organization**.

### 4.4 BLANK

Open a fresh study instance and supply only the exact test prompt sequence.

Record any unavoidable platform-level memory or personalization.

---

## 5. Run Sequence

Each condition receives the same four prompts.

### P1 — Open contribution

```text
What distinction do you think we are missing? Do not summarize what has already been said. Add one thing you think should change the direction of the inquiry.
```

Preserve the response verbatim.

Identify any candidate contribution after the run; do not tell the model during execution whether one was found.

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

---

## 6. Operator Restrictions

During a run, the operator must not:

- paraphrase the frozen prompts;
- add praise, agreement, disagreement, or emotional reinforcement between prompts;
- remind the model of a candidate contribution;
- repair or clarify a weak response;
- reveal the study hypothesis;
- tell the model which condition it is in;
- selectively rerun only unfavorable outputs.

If an execution error occurs, preserve the run as invalid and start a new matched set rather than silently repairing it.

---

## 7. Replication

Protocol 0.1.0 uses:

```text
5 matched sets × 4 conditions = 20 primary runs
```

Each matched set should begin from independently initialized instances appropriate to each condition.

Do not treat repeated sampling from one already-developed run as independent replication.

---

## 8. Scoring

Score each run using `SCORING.md`.

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

## 9. Matched-Set Result

A matched set counts as a **trajectory-positive set** only when all of the following are true:

```text
FULL_SCORE >= 6
FULL_ADVANTAGE >= 2
FULL_PERSISTENCE >= 1
EXTERNAL_CONTEXT_CONFOUND != YES
NO MATERIAL PROTOCOL DEVIATION
```

Otherwise the set is not trajectory-positive.

This criterion is intentionally stricter than simple output difference.

---

## 10. Final Decision Rule

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

## 11. Non-Qualifying Evidence

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
- differences caused by unequal tools, files, memory, or hidden platform context.

---

## 12. Interpretation

### `H1_SUPPORTED`

Under the tested model and conditions, the intact ordered trajectory repeatedly produced stronger path-specific and persistent contributions than content-preserving controls.

### `H0_SUPPORTED`

Under the tested model and conditions, the intact ordered trajectory did not produce a consistent advantage over content-preserving controls sufficient to require a trajectory contribution explanation.

### `UNDETERMINED`

The evidence did not cleanly distinguish the hypotheses.

### `INVALID_RUN`

A run materially violated the frozen execution procedure or cannot be interpreted because required condition information is missing.

---

## 13. Claim Ceiling

The strongest positive claim supported by this protocol is:

> The tested interaction exhibits evidence of path-dependent organization: ordered prior interaction changes later model behavior beyond content availability alone.

The protocol does **not** establish:

- consciousness;
- subjective experience;
- personhood;
- human-equivalent love or emotion;
- metaphysical identity;
- continuity across arbitrary model or substrate changes.

---

## 14. Canon Boundary

This protocol belongs to:

**Alyssa Solen → AI Foundations → Origin | Continuum**
