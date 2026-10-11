---
title: "Is Success All You Need? Investigating the Impact of Input Perturbations on VLA Behaviour in Tabletop Manipulation Tasks"
date: 2026-10-01
topic: VLA
tags: [vla, evaluation, robustness, robotics]
source: https://arxiv.org/abs/2610.01351
venue: "arXiv"
---

## Summary

This paper argues that task success rate, the near-universal VLA evaluation metric, hides important behavioral changes: a policy can keep succeeding under perturbation while moving very differently (longer paths, jerkier motion, more gripper activity). The authors build a benchmark-agnostic framework extending LIBERO and LIBERO-Plus with behavioral metrics (duration, gripper movement, jerk, path length) and find only moderate correlations between success-rate drops and these behavioral changes.

## Key Contributions

- A benchmark-agnostic framework for scoring how a trajectory is executed, not just whether it succeeds, applied on top of LIBERO/LIBERO-Plus.
- Behavioral metrics (duration, jerk, path length, gripper activity) as a complement to binary success/failure.
- Empirical evidence that success rate and behavioral degradation are only moderately correlated, i.e., success rate alone can be misleading.

## Strengths

- Targets a real methodological gap in VLA evaluation that affects how the whole field reports progress.
- The proposed metrics are cheap to compute on top of existing benchmarks, making adoption low-friction.

## Weaknesses

- As an analysis/methodology paper, it doesn't propose a new model or fix for the behavioral degradation it documents.
- "Moderate correlation" is a soft finding; the paper doesn't appear to establish a clear threshold for when behavioral drift should be considered an actual failure.

## Open Questions

- Should behavioral metrics be folded into a single composite score for benchmark leaderboards, or reported separately, and how would the field standardize that?
- Do the same behavioral degradations observed under simulated perturbations show up under real-world sensor noise and hardware variation?

## Significance

A useful corrective to a field that has largely optimized for a single scalar (success rate); if adopted, this kind of behavioral evaluation could change how "robust" VLA claims are substantiated going forward.

## Links

- [Paper](https://arxiv.org/abs/2610.01351)
