---
title: "Learning Process Rewards via Success Visitation Matching for Efficient RL"
date: 2026-06-26
topic: RL-Robotics
tags: [reward-modeling, process-rewards, sparse-reward, rl-finetuning]
source: https://arxiv.org/abs/2606.23640
venue: "arXiv"
---

## Summary

Trains a discriminator to distinguish successful from unsuccessful episodes' state-action visitations, then uses it to give dense process-reward signal that pulls the policy's visitation distribution toward successful trajectories and away from unsuccessful ones — provably without altering the optimal policy under the sparse ground-truth reward.

## Key Contributions

- A GAIL-style discriminator-based process reward that provides dense feedback on task progress derived purely from visitation matching, not hand-crafted progress heuristics
- Theoretical claim that the shaped reward preserves the sparse-reward task's optimal policy (a form of potential-based/optimality-preserving reward shaping)
- Shown to speed up RL fine-tuning of robotic control policies on both simulated and real-world manipulation tasks compared to sparse-reward-only RL

## Strengths

- Optimality-preservation is a meaningful theoretical property that distinguishes it from ad hoc dense-reward hacks that can shift the optimal policy
- Uses the policy's own successful/unsuccessful rollout history rather than requiring external human-designed progress functions

## Weaknesses

- Bootstrapping is a concern: early in training, when successes are rare or nonexistent, there may not be enough successful visitation data for the discriminator to be useful
- Discriminator-based rewards are known in the broader imitation-learning literature to be prone to overfitting/exploitation by the policy, and it's unclear how well this variant resists that

## Open Questions

- How does the method perform in the true cold-start regime (zero or near-zero initial successes), which is exactly when sparse-reward RL struggles most?
- How does the theoretical optimality-preservation guarantee hold up under function approximation error in practice?

## Significance

Dense, theoretically-grounded process rewards derived automatically from the policy's own rollout history is an appealing direction for making sparse-reward RL fine-tuning of robot policies more sample-efficient without introducing new sources of reward misspecification.

## Links

- [Paper](https://arxiv.org/abs/2606.23640)
