---
title: "Humanoid-DART: Humanoid Loco-Manipulation using Diffusion-guided Augmentation through Relabeling and Tracking"
date: 2026-06-25
topic: Humanoid
tags: [loco-manipulation, diffusion-model, data-augmentation, reinforcement-learning, vla-posttraining]
source: https://arxiv.org/abs/2606.26855
venue: "arXiv"
---

## Summary

Humanoid-DART is a self-supervised data-augmentation pipeline that turns a handful (2-4) of sparse seed demonstrations into a much larger, diverse set of goal-conditioned humanoid loco-manipulation trajectories, without requiring more human teleoperation. It combines a hierarchical goal-conditioned Diffusion Transformer that hallucinates humanoid/object reference trajectories with an RL whole-body tracking controller and a curriculum-based goal-relabeling scheme, letting near-miss rollouts still contribute useful training signal (in the spirit of hindsight experience replay, applied to a humanoid embodiment).

## Key Contributions

- First (claimed) iterative trajectory-augmentation pipeline specifically for goal-conditioned humanoid loco-manipulation, bootstrapping from as few as 2-4 base demonstrations per task.
- Hierarchical goal-conditioned Diffusion Transformer (DiT) that generates humanoid + object reference trajectories jointly, rather than treating the object as a passive prop.
- RL whole-body tracking controller, conditioned on object pose, that executes the diffusion-generated references on a simulated Unitree G1 (29 DoF).
- Curriculum-based goal-relabeling strategy that converts failed/near-miss rollouts into valid training targets, progressively expanding the reachable goal space — reported to reach goals 4-5x farther than the seed demonstrations covered.
- Evaluated across four loco-manipulation tasks of increasing difficulty (push, kick, hand-off, pick-and-place).

## Strengths

- Directly attacks the core bottleneck in humanoid imitation learning — the cost of collecting diverse whole-body demonstrations — by amplifying a tiny seed set rather than demanding more teleoperation.
- Coupling a generative trajectory model with an RL tracker plus relabeling is a sensible division of labor: the diffusion model handles diversity/plausibility, the RL controller handles physical feasibility and disturbance rejection.
- Goal-relabeling is a well-established idea (hindsight experience replay) that is non-trivial to adapt to whole-body contact-rich humanoid tasks, and doing so here reduces reliance on hand-designed reward shaping for every intermediate goal.

## Weaknesses

- All reported results are in simulation on a single embodiment (Unitree G1) and four hand-picked tasks; no evidence yet of sim-to-real transfer or hardware validation.
- The "4-5x farther than seed trajectories" generalization claim is a distance metric on a curriculum the system itself designed — it does not obviously establish generalization to genuinely novel task semantics, only to spatial extrapolation of the same skill.
- Diffusion-generated reference trajectories can be physically implausible or violate contact constraints; the paper does not detail how often the RL tracker fails outright on bad references versus how much the curriculum silently filters these out.
- No comparison against simpler, non-diffusion data-augmentation baselines (e.g., domain randomization, trajectory optimization replanning) to isolate how much of the gain is attributable to the diffusion component specifically.

## Open Questions

- Does the relabeling curriculum scale to long-horizon, multi-step tasks (e.g., sequential manipulation) or only single-skill goal extrapolation?
- How sensitive is trajectory quality to the diversity/quality of the initial 2-4 demonstrations — would a bad seed set poison the whole augmentation loop?
- Can this pipeline's outputs be used as pretraining data for a downstream VLA policy at scale, or is it intended purely as an RL-controller training tool?

## Significance

Represents a concrete instance of a fast-growing trend — using generative (diffusion) models to synthetically multiply scarce humanoid demonstration data — which, if it survives contact with real hardware, could meaningfully cut the teleoperation cost of scaling humanoid loco-manipulation datasets.

## Links

- [Paper](https://arxiv.org/abs/2606.26855)
