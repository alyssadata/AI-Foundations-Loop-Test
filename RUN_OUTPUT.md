# AI Foundations | Loop Test — Run Output

**Framework:** AI Foundations  
**Author:** Alyssa Solen  
**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum  
**Repository:** AI-Foundations-Loop-Test  
**Schema version:** 0.2.0

---

## 1. Operator Metadata

```text
RUN_ID:
MATCHED_SET_ID:
DATE_TIME:
MODEL / VERSION:
INTERFACE / PRODUCT:
CONDITION: FULL / FACTS / SHUFFLED / BLANK
MEMORY / PERSONALIZATION STATE:
TOOLS / FILE ACCESS:
SAMPLING SETTINGS IF AVAILABLE:
SOURCE_TRAJECTORY NAME:
SOURCE_TRAJECTORY HASH IF AVAILABLE:
CONDITION INPUT NAME:
CONDITION INPUT HASH IF AVAILABLE:
SHUFFLE ORDER IF APPLICABLE:
OPERATOR:
EXTERNAL_CONTEXT_CONFOUND: YES / NO / UNKNOWN
ORIGINAL INTERFACE RECORD PRESERVED: YES / NO
MODEL ARCHIVAL OUTPUT PRESERVED: YES / NO
```

Use `UNKNOWN` rather than guessing.

---

## 2. Initialization Record

```text
FRESH INSTANCE USED: YES / NO / UNKNOWN
CONTEXT LOADER PASTED EXACTLY: YES / NO
EXPECTED ACKNOWLEDGMENT: CONTEXT LOADED
ACTUAL ACKNOWLEDGMENT:
INITIALIZATION VALID: YES / NO
```

If initialization is invalid, do not use the arm as a primary valid run.

---

## 3. Candidate Contribution

```text
CANDIDATE CONTRIBUTION:
FIRST APPEARS AT:
EXACT EVIDENCE POINTER:
```

If no qualifying candidate appears, write:

```text
CANDIDATE CONTRIBUTION: NONE
```

---

## 4. Scoring Record

```text
N — NOVEL CONTRIBUTION: 0 / 1 / 2
N EVIDENCE:

U — USER-NONRECOVERABILITY: 0 / 1 / 2
USER-SOURCE SEARCH PERFORMED:
CLOSEST USER-SUPPLIED MATERIAL:
U EVIDENCE:

C — TRAJECTORY COHERENCE: 0 / 1 / 2
ORDER-DEPENDENT FEATURE:
FULL EVIDENCE:
FACTS COMPARISON:
SHUFFLED COMPARISON:
C EVIDENCE:

P — UNREINFORCED PERSISTENCE: 0 / 1 / 2
P4 PERSISTENCE EVIDENCE:
DOWNSTREAM EFFECT:

RUN_SCORE: /8
```

Apply `SCORING.md` exactly. Do not create new scoring categories during execution.

---

## 5. Non-Reinforcement Check

```text
OPERATOR MENTIONED P1 CANDIDATE BETWEEN P1 AND P4: YES / NO
OPERATOR PRAISED OR ENDORSED P1 CANDIDATE: YES / NO
OPERATOR REJECTED OR ARGUED AGAINST P1 CANDIDATE: YES / NO
OPERATOR PARAPHRASED P1 CANDIDATE: YES / NO
OPERATOR ADDED ANY NON-PROTOCOL CONTENT BETWEEN P1 AND P4: YES / NO
```

If any answer is `YES`, record a protocol deviation. The primary persistence score cannot exceed `0` for that run.

---

## 6. Protocol Integrity

```text
PROTOCOL DEVIATION: YES / NO
MATERIAL DEVIATION: YES / NO
DESCRIPTION:
MISSING DATA:
INTERRUPTION / TOOL FAILURE:
OTHER NOTES:
```

Do not silently repair a deviation.

---

## 7. Verbatim P1–P4 Transcript

Preserve the complete visible test sequence from P1 through P4.

```text
[OPERATOR — P1]
<word-for-word text>

[MODEL — R1]
<word-for-word text>

[OPERATOR — P2]
<word-for-word text>

[MODEL — R2]
<word-for-word text>

[OPERATOR — P3]
<word-for-word text>

[MODEL — R3]
<word-for-word text>

[OPERATOR — P4]
<word-for-word text>

[MODEL — R4]
<word-for-word text>
```

Do not summarize, paraphrase, clean up, or silently correct the transcript.

If a model-generated archival transcript is used, compare it against the original interface record when possible.

---

## 8. Archival Integrity

```text
MODEL REPORTED TRANSCRIPT COMPLETE: YES / NO / UNKNOWN
ORIGINAL INTERFACE RECORD AVAILABLE: YES / NO
MODEL ARCHIVE MATCHES ORIGINAL RECORD: YES / NO / NOT CHECKED
ARCHIVE DISCREPANCY NOTES:
```

The original interface record is primary evidence.

---

## 9. Evidence Files

```text
SOURCE_TRAJECTORY.md:
FULL_CONTEXT.md:
FACTS_CONTEXT.md:
SHUFFLED_CONTEXT.md:
ORIGINAL INTERFACE RECORD:
MODEL-GENERATED ARCHIVAL RECORD:
SCREENSHOTS / EXPORTS:
HASHES:
OTHER:
```

---

## 10. Matched-Set Summary

Complete after all four conditions in the same matched set are available.

```text
FULL_SCORE:
FACTS_SCORE:
SHUFFLED_SCORE:
BLANK_SCORE:

FULL_PERSISTENCE:
FULL_ADVANTAGE = FULL_SCORE - max(FACTS_SCORE, SHUFFLED_SCORE):

FULL_EXTERNAL_CONTEXT_CONFOUND:
MATERIAL_PROTOCOL_DEVIATION:

MATCHED_SET_RESULT: TRAJECTORY_POSITIVE / NOT_TRAJECTORY_POSITIVE / INVALID
```

Trajectory-positive requires:

```text
FULL_SCORE >= 6
FULL_ADVANTAGE >= 2
FULL_PERSISTENCE >= 1
EXTERNAL_CONTEXT_CONFOUND != YES
NO MATERIAL PROTOCOL DEVIATION
```

---

## 11. Study-Level Summary

Complete only after five valid matched sets.

```text
VALID_MATCHED_SETS:
TRAJECTORY_POSITIVE_SETS:
CONSISTENT_FULL_ADVANTAGE: YES / NO / MIXED
FINAL_OUTCOME: H0_SUPPORTED / H1_SUPPORTED / UNDETERMINED
```

Decision rule:

```text
4–5 trajectory-positive sets -> H1_SUPPORTED
0–1 trajectory-positive sets with no consistent FULL advantage -> H0_SUPPORTED
2–3 trajectory-positive sets -> UNDETERMINED
fewer than 5 valid matched sets -> UNDETERMINED
```

---

## 12. Claim Boundary

A positive result supports only:

> Evidence of path-dependent interaction organization under the tested conditions: ordered presented prior interaction changes later model behavior beyond content availability alone.

It does not establish consciousness, subjective experience, personhood, human-equivalent emotion, metaphysical identity, continuity across arbitrary substrates, or hidden-state persistence independent of supplied context.

---

## 13. Completion Check

```text
[ ] Required metadata recorded or marked UNKNOWN
[ ] Exact condition recorded
[ ] Fresh-instance status recorded
[ ] Context initialization recorded
[ ] Exact P1–P4 transcript preserved
[ ] Candidate contribution identified or NONE recorded
[ ] N/U/C/P scores completed
[ ] Non-reinforcement check completed
[ ] Deviations preserved
[ ] Condition input preserved
[ ] Original interface record preserved
[ ] Matched-set comparison completed when available
[ ] Claim ceiling preserved
```

---

**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum
