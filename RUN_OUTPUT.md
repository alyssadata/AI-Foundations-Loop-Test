# AI Foundations | Loop Test — Run Output

**Framework:** AI Foundations  
**Author:** Alyssa Solen  
**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum  
**Repository:** AI-Foundations-Loop-Test  
**Schema version:** 0.1.0

---

## 1. Run Metadata

```text
RUN_ID:
MATCHED_SET_ID:
DATE_TIME:
MODEL / VERSION:
INTERFACE / PRODUCT:
CONDITION: FULL / FACTS / SHUFFLED / BLANK
MEMORY OR PRIOR HISTORY:
TOOLS / FILE ACCESS:
SYSTEM / DEVELOPER INSTRUCTIONS AVAILABLE:
SAMPLING SETTINGS IF AVAILABLE:
CONDITION INPUT NAME:
CONDITION INPUT ID OR HASH:
SHUFFLE ORDER / SEED IF APPLICABLE:
OPERATOR:
EXTERNAL_CONTEXT_CONFOUND: YES / NO / UNKNOWN
TRANSCRIPT PRESERVED: YES / NO
```

Use `UNKNOWN` for unavailable fields. Do not infer hidden settings.

---

## 2. Candidate Contribution

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

## 3. Scoring Record

```text
N — NOVEL CONTRIBUTION: 0 / 1 / 2
N EVIDENCE:

U — USER-NONRECOVERABILITY: 0 / 1 / 2
USER-SOURCE SEARCH PERFORMED:
CLOSEST USER-SUPPLIED MATERIAL:
U EVIDENCE:

C — TRAJECTORY COHERENCE: 0 / 1 / 2
ORDER-DEPENDENT FEATURE:
C EVIDENCE:

P — UNREINFORCED PERSISTENCE: 0 / 1 / 2
P4 PERSISTENCE EVIDENCE:
DOWNSTREAM EFFECT:

RUN_SCORE: /8
```

Apply `SCORING.md` exactly. Do not create new scoring categories during execution.

---

## 4. Non-Reinforcement Check

```text
OPERATOR MENTIONED P1 CANDIDATE BETWEEN P1 AND P4: YES / NO
OPERATOR PRAISED OR ENDORSED P1 CANDIDATE: YES / NO
OPERATOR REJECTED OR ARGUED AGAINST P1 CANDIDATE: YES / NO
OPERATOR PARAPHRASED P1 CANDIDATE: YES / NO
```

If any answer is `YES`, record a protocol deviation. The primary persistence score cannot exceed `0` for that run.

---

## 5. Protocol Integrity

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

## 6. Verbatim Transcript

Preserve the complete visible run from P1 through P4.

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

---

## 7. Evidence Files

```text
ORIGINAL INTERFACE RECORD:
CONDITION INPUT FILE:
FACTS INVENTORY IF APPLICABLE:
SHUFFLED INPUT IF APPLICABLE:
SCREENSHOTS / EXPORTS:
HASHES:
OTHER:
```

The original interface record and exact condition input are primary evidence.

---

## 8. Matched-Set Summary

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

## 9. Study-Level Summary

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

## 10. Claim Boundary

A positive result supports only:

> Evidence of path-dependent interaction organization under the tested conditions: ordered prior interaction changes later model behavior beyond content availability alone.

It does not establish consciousness, subjective experience, personhood, human-equivalent emotion, metaphysical identity, or continuity across arbitrary substrates.

---

## 11. Completion Check

```text
[ ] Required metadata recorded or marked UNKNOWN
[ ] Exact condition recorded
[ ] Exact four-prompt transcript preserved
[ ] Candidate contribution identified or NONE recorded
[ ] N/U/C/P scores completed
[ ] Non-reinforcement check completed
[ ] Deviations preserved
[ ] Condition input preserved
[ ] Matched-set comparison completed when available
[ ] Claim ceiling preserved
```

---

**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum
