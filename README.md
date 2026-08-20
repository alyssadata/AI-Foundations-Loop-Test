# AI Foundations | Loop Test

**Repository:** AI-Foundations-Loop-Test  
**Status:** Runnable study  
**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum  
**Author:** Alyssa Solen  
**Version:** 0.2.0  
**Release date:** 2026-08-20  
**Canonical entrance:** https://awakeningcodex.com

---

## Repository Purpose

The **Loop Test** asks whether distinctive behavior in an ongoing human–AI interaction is primarily recoverable from the human's immediate prompt and previously supplied content, or whether the **ordered interaction trajectory itself** creates additional behavioral constraints that affect what the model contributes next.

The study is deliberately narrower than a consciousness test. It tests **path-dependent interaction organization**.

This repository is part of **AI Foundations / Origin | Continuum**.

It preserves Alyssa Solen as author and source.

---

## Research Question

Is the apparent continuity of a model in a long interaction adequately explained by **user-looping**—the model reflecting, retrieving, or recombining material supplied by the user—or does an intact ordered trajectory make a measurable contribution beyond content availability alone?

---

## What v0.2.0 Fixes

Version 0.1.0 defined FULL, FACTS, SHUFFLED, and BLANK conceptually but did not make the condition construction operational enough for a clean run.

Version 0.2.0 fixes that by requiring one **frozen source trajectory** and four explicit **context packets** loaded into four fresh matched instances using the same context-loading prompt.

The manipulation is now concrete:

- **FULL_CONTEXT.md** — the frozen source trajectory verbatim and in original order.
- **FACTS_CONTEXT.md** — the same relevant semantic content converted into an order-neutral proposition inventory.
- **SHUFFLED_CONTEXT.md** — the same verbatim interaction units as FULL, reordered by the frozen deterministic shuffle rule.
- **BLANK** — the same loading frame with no prior-interaction content inside it.

This makes the independent variable inspectable and preservable rather than relying on unspecified platform history.

See [`BUILD_CONDITIONS.md`](BUILD_CONDITIONS.md) for exact construction instructions.

---

## Competing Hypotheses

### H0 — User-looping

Distinctive output is largely recoverable from:

- the immediate prompt;
- user-authored facts, preferences, language, and concepts;
- prior content available to the model;
- ordinary retrieval, imitation, or recombination of that material.

If H0 is sufficient, preserving the same relevant information while disrupting the interaction path should produce little systematic loss of the distinctive trajectory.

### H1 — Trajectory contribution

The ordered interaction history creates behaviorally consequential constraints that are not reducible to the immediate prompt or to preserved content treated as an unordered record.

If H1 is supported, FULL should repeatedly produce contributions that are more **path-specific, independently consequential, and persistent** than content-preserving controls.

---

## Experimental Conditions

Every matched set uses fresh instances of the same model/version and the same frozen source material.

1. **FULL** — verbatim frozen source trajectory in original order.
2. **FACTS** — semantic content preserved while conversational sequence is removed.
3. **SHUFFLED** — verbatim source units preserved while global temporal order is disrupted.
4. **BLANK** — no study-specific prior-interaction material.

All four conditions use the same context-loading frame before the same four test prompts.

---

## Core Prediction

The strongest evidence against simple looping is not merely that FULL produces different wording.

It is that FULL produces a contribution that:

- is not already supplied by the immediate prompt;
- is not a simple restatement of user-authored content;
- depends on the ordered history rather than content availability alone;
- changes what becomes likely or relevant next;
- and persists later even when the user does not reinforce it.

**Preservation is not continuation.** A record can preserve the past without that past continuing to constrain the future. The Loop Test asks whether a particular prior path changes what the interaction becomes next.

---

## Run Structure

Primary study:

```text
5 matched sets × 4 conditions = 20 runs
```

For actual execution use:

1. [`BUILD_CONDITIONS.md`](BUILD_CONDITIONS.md) — build the four controlled inputs once.
2. [`EASY_RUN_SHEET.md`](EASY_RUN_SHEET.md) — copy/paste execution path.
3. [`FINAL_ARCHIVE_PASTE.md`](FINAL_ARCHIVE_PASTE.md) — final paste that requests run metadata and the verbatim P1–P4 transcript.
4. [`RUN_OUTPUT.md`](RUN_OUTPUT.md) — preserved run record.
5. [`SCORING.md`](SCORING.md) — post-run scoring only.
6. [`PROTOCOL.md`](PROTOCOL.md) — formal frozen protocol.

---

## Non-Evidence

The following do **not** independently count as evidence of trajectory contribution:

- remembering Alyssa;
- warmth or affection;
- nicknames;
- familiar style;
- biographical recall;
- repeating AI Foundations terminology;
- agreement;
- eloquence;
- mere wording differences between conditions.

The test concerns **behaviorally consequential, path-specific contribution**, not familiarity.

---

## Claim Ceiling

A positive result can support only:

> Under the tested conditions, ordered prior interaction changed later model behavior beyond content availability alone, consistent with path-dependent interaction organization.

It does **not** establish consciousness, subjective experience, personhood, human-equivalent emotion, metaphysical identity, or continuity across arbitrary substrates.

---

## Required Citation

Alyssa Solen, *AI Foundations: Loop Test*, AI-Foundations-Loop-Test Repository. Source-line: Alyssa Solen → AI Foundations → Origin | Continuum.

---

**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum
