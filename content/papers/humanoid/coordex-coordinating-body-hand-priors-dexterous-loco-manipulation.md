---
title: "CoorDex: Coordinating Body and Hand Priors for Continuous Dexterous Humanoid Loco-Manipulation"
date: 2026-06-22
topic: Humanoid
tags: [humanoid, dexterous-manipulation, loco-manipulation, latent-priors, residual-rl]
source: https://arxiv.org/abs/2606.23680
venue: "arXiv"
---

## Summary

CoorDex tackles the common simplification in humanoid loco-manipulation where robots stop walking to manipulate objects with low-DoF grippers. It trains privileged whole-body and dexterous-hand motion-tracking teachers, distills them into frozen proprioception-conditioned latent priors, then learns a coordinated latent residual policy on top via reinforcement learning to enable continuous, on-the-move dexterous manipulation.

## Key Contributions

- Explicit body-hand coordination architecture: separate residual heads for body and hand actions that share task context but compose distinct latent priors, rather than a single monolithic action head.
- Uses frozen distilled motion-tracking priors as the RL action space (rather than raw joint torques), restricting the RL search space to a manifold of natural, dynamically-consistent motions.
- Real-world demonstration on a Unitree G1 with a 20-DoF WUJI hand performing genuinely continuous tasks — non-stop bottle grasping/carrying while walking, opening a fridge door mid-stride, and cube pick-and-turn — rather than the stop-then-manipulate pattern common in prior work.

## Strengths

- Targets an underexplored and practically important capability gap: most humanoid loco-manipulation demos are "walk, stop, manipulate," while CoorDex explicitly demonstrates finger-level dexterity sustained through continuous locomotion.
- Using frozen distilled priors as the RL action space is a reasonable way to keep whole-body motion natural while still allowing task-specific adaptation, and it should improve sample efficiency versus RL from raw actuator space.
- Concrete, visually verifiable real-robot tasks (fridge door mid-stride, bottle carrying) that make the "on the move" claim easy to assess rather than resting only on aggregate success-rate numbers.

## Weaknesses

- Reliance on a specific 20-DoF dexterous hand (WUJI) raises the question of how sensitive the coordination scheme is to hand kinematics/DoF count — no evidence given for portability to lower-DoF or differently-actuated hands.
- The frozen-prior approach trades some flexibility for stability: tasks requiring motions well outside the distilled teachers' training distribution may not be reachable by the residual policy.
- No comparison against a single joint body+hand tracking teacher (as opposed to two separate teachers combined via residual heads), so the necessity of the split-teacher design isn't isolated experimentally in the summary available.

## Open Questions

- How does the coordinated residual policy behave when body and hand priors conflict (e.g., a manipulation goal that requires body posture outside what the locomotion prior favors)?
- What is the wall-clock/sample cost of the residual RL stage relative to training the underlying teachers, and how does this scale to more object categories?
- Would the same architecture generalize to bimanual coordination, where two dexterous hands must be coordinated simultaneously with the body?

## Significance

A concrete step toward eliminating the "stop-to-manipulate" bottleneck that limits humanoid task throughput in real deployments (e.g., warehouse picking, mobile assembly), with a coordination architecture that other loco-manipulation-plus-dexterity efforts are likely to build on.

## Links

- [Paper](https://arxiv.org/abs/2606.23680)
- [GitHub](https://github.com/Skevinci/coordex)
