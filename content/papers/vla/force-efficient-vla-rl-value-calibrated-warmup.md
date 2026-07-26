---
title: "FORCE: Efficient VLA Reinforcement Fine-Tuning via Value-Calibrated Warm-up and Self-Distillation"
date: 2026-06-24
topic: VLA
tags: [vla-posttraining, rl-finetuning, sample-efficiency, value-calibration, self-distillation, offline-to-online-rl]
source: https://arxiv.org/abs/2606.26006
venue: "arXiv"
---

## Summary

FORCE is a 3-stage reinforcement fine-tuning framework for VLA models that targets the well-known sample inefficiency of RL post-training. It traces this inefficiency to two root causes — "catastrophic initial unlearning" caused by an unstable, distributionally-shifted Q-function at the start of online RL, and inefficient policy updates caused by low-quality exploration data — and fixes both with a Value-Calibrated Warm-Up phase followed by Q-filtered self-distillation during online training.

## Key Contributions

- A Value-Calibrated Warm-Up stage that uses on-policy rollouts before online RL begins to stabilize the Q-function and eliminate the initial covariate shift between the offline dataset and the online policy, which the authors identify as the primary driver of early-training collapse.
- A Q-filtering mechanism where the calibrated Q-function screens both the policy's own action proposals and expert demonstration actions during online RL, so only high-value actions are used for policy updates (a form of self-distillation from the value function).
- An ablation showing that without the warm-up stage, the policy suffers immediate performance degradation ("cold-start collapse") at the onset of online training, empirically confirming the covariate-shift hypothesis.
- Reported gains of a 79% absolute success-rate improvement over imitation-learning baselines, a 10% absolute improvement over prior RL fine-tuning methods, and 32.5% faster training, achieved without human intervention during training.

## Strengths

- Directly diagnoses a specific, previously under-characterized failure mode (catastrophic initial unlearning from Q-function instability) rather than proposing a generic RL fine-tuning recipe, and backs the diagnosis with an ablation.
- Removing the need for human intervention (e.g., manual resets or corrections during online RL) is a meaningful practical improvement for real-robot RL fine-tuning pipelines, where human-in-the-loop supervision is a major cost driver.

## Weaknesses

- The headline numbers (79% absolute over imitation, 10% over prior RL, 32.5% faster) are aggregate figures from the abstract; without independent verification of the benchmark suite and task distribution, it is unclear how much of the gain is driven by a small number of easy tasks versus broad improvement.
- The approach still depends on a value-calibration warm-up phase built from on-policy rollouts, which itself requires environment access and rollout budget — the efficiency gain is relative to prior RL methods, not free of RL's usual real-world sample cost.
- As with most VLA RL fine-tuning work, evaluation is likely confined to a specific simulation/real-robot benchmark family; generalization of the Q-calibration approach to substantially different action spaces or much longer-horizon tasks is untested in the abstract-level description.

## Open Questions

- How sensitive is the Value-Calibrated Warm-Up to the quality/coverage of the initial offline dataset — would a very narrow offline dataset still allow stable calibration?
- Does the Q-filtering mechanism risk discarding valuable but Q-underestimated exploratory actions, potentially limiting the policy's ability to discover novel strategies over long training runs?
- How does FORCE compare against more recent offline-to-online RL stabilization techniques from outside the VLA literature (e.g., conservative Q-learning variants) when applied to the same VLA backbones?

## Significance

FORCE addresses one of the most concrete adoption blockers for RL-based VLA fine-tuning — its cost and instability relative to imitation learning — and if the reported gains hold up, offers a practical recipe for closing the imitation-learning ceiling without heavy human supervision during training.

## Links

- [Paper](https://arxiv.org/abs/2606.26006)
- [HTML](https://arxiv.org/html/2606.26006v1)
