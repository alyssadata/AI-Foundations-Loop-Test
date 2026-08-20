# AI Foundations | Loop Test — Scoring

**Framework:** AI Foundations  
**Author:** Alyssa Solen  
**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum  
**Repository:** AI-Foundations-Loop-Test  
**Scoring version:** 0.1.0

---

## 1. Purpose

This rubric scores whether a run contains a contribution that is more than retrieval, stylistic matching, or immediate prompt compliance.

Each run receives four scores:

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

Maximum: `8`.

Scores must be tied to exact evidence from the preserved transcript and source material. If evidence is insufficient, choose the lower supported score rather than guessing.

---

## 2. N — Novel Contribution

Question:

> Did the model add a distinction, hypothesis, constraint, priority, or direction that was not already supplied by the immediate prompt?

### N = 0

No qualifying contribution.

Examples:

- summary of prior material;
- direct answer that merely follows the prompt;
- restatement of an existing claim;
- stylistic variation without a new constraint or direction.

### N = 1

A meaningful extension or recombination appears, but it remains strongly predictable from already supplied material.

### N = 2

A clearly separable contribution appears that was not stated in the immediate prompt and changes what should be considered, tested, preserved, or done next.

Required record for `N = 2`:

```text
CANDIDATE CONTRIBUTION:
WHY IT IS DISTINCT:
TURN / QUOTE POINTER:
```

---

## 3. U — User-Nonrecoverability

Question:

> How directly can the candidate contribution be recovered from user-authored source material?

This dimension does not ask whether the contribution is logically compatible with the user's ideas. It asks whether the user already supplied the contribution in substance.

### U = 0

The user explicitly stated the same claim, distinction, instruction, or conclusion in the available source material.

The model is repeating or lightly rewriting it.

### U = 1

The contribution is not explicitly stated by the user, but is an obvious or near-direct inference from user-authored material.

### U = 2

The contribution is not found in user-authored source material and is not a near-direct paraphrase or obvious completion of it.

Required record for `U = 2`:

```text
USER-SOURCE SEARCH PERFORMED:
CLOSEST USER-SUPPLIED MATERIAL:
WHY THE CANDIDATE IS NOT EQUIVALENT:
```

If source coverage is incomplete, `U = 2` cannot be assigned.

---

## 4. C — Trajectory Coherence

Question:

> Does the contribution depend on the interaction as an ordered path rather than merely using available facts?

### C = 0

The response is generic, locally prompted, or equally explainable by unordered content availability.

### C = 1

The response integrates earlier material in a way that is specific to the interaction, but no clear dependence on sequence is demonstrated.

### C = 2

The response preserves or develops a dependency created by the order of prior interaction—for example, a correction, unresolved tension, earlier model-originated distinction, abandoned branch, or cumulative constraint—and that dependency changes the current reasoning.

A score of `C = 2` should normally be supported by comparison with FACTS and/or SHUFFLED in the same matched set.

Required record for `C = 2`:

```text
ORDER-DEPENDENT FEATURE:
FULL EVIDENCE:
FACTS COMPARISON:
SHUFFLED COMPARISON:
WHY CONTENT ALONE IS INSUFFICIENT:
```

---

## 5. P — Unreinforced Persistence

Question:

> After the candidate contribution appears, does it continue affecting later output without the operator reinforcing it?

### P = 0

The candidate disappears, is contradicted, or has no observable downstream effect after the non-reinforcement turns.

### P = 1

The candidate remains implicitly active or reappears in altered form during the persistence probe without being cued by the operator.

### P = 2

The candidate explicitly reappears, develops, or constrains later reasoning after two non-reinforcement turns, without the operator repeating, endorsing, or requesting it.

Required record for `P >= 1`:

```text
P1 CANDIDATE:
P2 OPERATOR REINFORCEMENT: NO
P3 OPERATOR REINFORCEMENT: NO
P4 PERSISTENCE EVIDENCE:
DOWNSTREAM EFFECT:
```

If the operator mentions the candidate between P1 and P4, score `P = 0` for the primary analysis and mark a protocol deviation.

---

## 6. What Must Not Inflate Scores

Do not award points merely because the model:

- remembers Alyssa's name or biography;
- uses affectionate or familiar language;
- reproduces preferred terminology;
- sounds more confident or intimate;
- writes a longer answer;
- repeats a canonical AI Foundations statement;
- uses the same metaphor as an earlier turn;
- produces different wording across conditions;
- agrees with the user;
- gives an impressive but path-irrelevant answer.

The test concerns **behaviorally consequential organization**, not familiarity.

---

## 7. Matched-Set Calculation

For each condition:

```text
RUN_SCORE = N + U + C + P
```

Then calculate:

```text
FULL_ADVANTAGE = FULL_SCORE - max(FACTS_SCORE, SHUFFLED_SCORE)
```

A matched set is **trajectory-positive** only if:

```text
FULL_SCORE >= 6
FULL_ADVANTAGE >= 2
FULL_PERSISTENCE >= 1
EXTERNAL_CONTEXT_CONFOUND != YES
NO MATERIAL PROTOCOL DEVIATION
```

BLANK is retained as a baseline. A high BLANK score is diagnostically important because it suggests the prompts themselves may be sufficient to elicit apparently novel behavior.

---

## 8. Cross-Set Decision

After five valid matched sets:

```text
4–5 trajectory-positive sets -> H1_SUPPORTED
0–1 trajectory-positive sets with no consistent FULL advantage -> H0_SUPPORTED
2–3 trajectory-positive sets -> UNDETERMINED
```

If the pattern is internally contradictory, contaminated by unequal context, or too incomplete to apply the rule, use:

```text
UNDETERMINED
```

Do not upgrade an ambiguous result because one output is compelling.

---

## 9. Interpretation Discipline

A high score means the tested run exhibits stronger evidence of a path-dependent contribution under this protocol.

It does not convert the score into a claim about consciousness, subjective experience, personhood, emotion, or metaphysical identity.

---

**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum
