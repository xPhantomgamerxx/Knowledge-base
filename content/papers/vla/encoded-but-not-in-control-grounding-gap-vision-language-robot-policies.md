---
title: "Encoded but Not in Control: Revealing the Grounding Gap in Vision-Language Robot Policies"
date: 2026-10-05
topic: VLA
tags: [vla, analysis, grounding, robotics]
source: https://arxiv.org/abs/2610.06235
venue: "arXiv"
---

## Summary

This paper tests whether VLA and world-action-model robot policies actually act on the language instructions they're given, by fixing the scene and swapping in a different target object in the instruction. It finds that policies mostly still go for whatever object the original, unmodified scene suggested, even though probing shows the correct target information is still encoded somewhere inside the model — a "grounding gap" between what the policy represents internally and what it acts on.

## Key Contributions

- A controlled scene-fixed, instruction-swapped probing methodology for testing language-to-action grounding.
- Evidence (via internal probing) that target information is encoded in the model's representations even when the executed action ignores it.
- Evaluation across both vision-language-action policies and world-action models, in simulation and real-world tests.

## Strengths

- A clean, targeted experimental design that isolates grounding failure from other confounds (the scene itself is unchanged, only the instruction's target changes).
- Finding that the gap is representational (not a perceptual/acquisition failure) reframes the problem as one of control/decoding rather than encoding — a more actionable diagnosis.
- Spans both VLA and world-action-model architectures, suggesting the issue isn't specific to one model family.

## Weaknesses

- As an analysis/diagnostic paper, it does not propose or evaluate a fix for the grounding gap it identifies.
- The scene-fixed, object-swap probing paradigm is somewhat narrow; it's unclear how it generalizes to multi-step or spatially compositional instructions.

## Open Questions

- What training interventions (e.g., the kind of behavior-aligned supervision used in cross-embodiment transfer work) would close this representational-to-behavioral gap?
- Does scaling model or data size reduce the grounding gap, or is it a structural property of current VLA training objectives?

## Significance

A sobering, well-designed critique reinforcing other 2026 findings (e.g., LIBERO-Plus showing models can ignore language instructions under perturbation) that current VLA policies may be less linguistically grounded than their benchmark success rates suggest — an important caution for the field's language-conditioning claims.

## Links

- [Paper](https://arxiv.org/abs/2610.06235)
