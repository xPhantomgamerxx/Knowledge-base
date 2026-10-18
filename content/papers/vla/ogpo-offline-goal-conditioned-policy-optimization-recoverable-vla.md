---
title: "OGPO: Offline Goal-conditioned Policy Optimization for Recoverable Vision-Language-Action Models"
date: 2026-10-09
topic: VLA
tags: [vla, reinforcement-learning, offline-rl, post-training, recovery, vla-posttraining]
source: https://arxiv.org/abs/2610.12914
venue: "arXiv / NeurIPS 2026"
---

## Summary

OGPO is an offline post-training method for VLA policies that targets a specific weakness of imitation-only fine-tuning: once a policy drifts off the demonstrated trajectory, it has no signal for how to recover. The method relabels existing offline trajectories with semantic key states and trains with goal-conditioned process rewards toward those task-progress states, entirely without further online interaction.

## Key Contributions

- A relabeling scheme that extracts semantic "key states" from existing demonstration data, turning static trajectories into a source of goal-conditioned supervision instead of pure behavior-cloning targets.
- A process-reward formulation that rewards progress toward recovered goals rather than only final-task success, directly addressing off-distribution recovery rather than on-distribution replication.
- LIBERO-ReAct, a new mid-execution perturbation benchmark built to specifically test whether a policy can recover after being knocked off its nominal trajectory.

## Strengths

- Needs no additional online rollouts or environment access, which matters for the common case where a lab has offline logs but limited robot time for RL fine-tuning.
- Explicitly targets a failure mode (lack of recovery behavior) that pure SFT post-training is known to leave unaddressed, rather than chasing another point of in-distribution success rate.
- Reports gains on both standard LIBERO/MetaWorld success rate and on the perturbation-focused LIBERO-Plus/LIBERO-ReAct settings, suggesting the method isn't purely optimizing for the new benchmark it introduces.

## Weaknesses

- Offline relabeling into "semantic key states" depends on how cleanly the underlying task decomposes into intermediate progress milestones; tasks without clean sub-goal structure may not benefit as much.
- As an offline method, it is bounded by the state/action coverage of the original dataset — it can teach recovery toward states that were visited, but not arbitrary generalization beyond the data's support.
- The paper's own name collides with an unrelated "OGPO" (Off-policy Generative Policy Optimization) from the diffusion-policy literature, which risks confusion when searching for follow-up work.

## Open Questions

- How much does performance depend on the granularity/quality of the automatic key-state extraction, and does it transfer across embodiments without re-tuning?
- Could this be combined with a lightweight online phase to patch the remaining out-of-support recovery gaps cheaply?
- How does OGPO compare directly against the growing family of test-time recovery methods (e.g., failure-aware retry, counterfactual re-planning) that solve the same problem at inference time instead of training time?

## Significance

OGPO is a clean example of the broader VLA post-training trend away from pure imitation and toward goal/process-reward shaping, and LIBERO-ReAct adds a reusable benchmark specifically for recovery behavior — a property current leaderboards mostly don't measure.

## Links

- [Paper](https://arxiv.org/abs/2610.12914)
- [NeurIPS 2026 poster](https://neurips.cc/virtual/2026/poster/152279)
