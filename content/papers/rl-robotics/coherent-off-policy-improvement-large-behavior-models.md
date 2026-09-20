---
title: "Coherent Off-Policy Improvement of Large Behavior Models with Learned Rewards"
date: 2026-06-02
topic: RL-Robotics
tags: [vla-posttraining, inverse-rl, reward-learning, offline-to-online, imitation-learning]
source: https://arxiv.org/abs/2606.02194
venue: "arXiv"
---

## Summary

Proposes "coherent imitation learning," an inverse-RL method that learns a dense reward function from expert demonstrations with theoretical guarantees, enabling off-policy improvement of large pretrained behavior models (VLA-scale policies) without the sample inefficiency that plagues RL fine-tuning under sparse rewards.

## Key Contributions

- Learns a dense reward via IRL from demonstrations rather than relying on sparse task-success signals for RL fine-tuning
- Provides theoretical guarantees that the learned reward supports coherent (non-degrading) improvement of the behavior-cloned policy
- Reports maintaining or improving performance on all six tested sparse manipulation tasks, achieving ≥90% success on five of six, and outperforming RL baselines that use sparse rewards directly

## Strengths

- Directly targets a known weak point of residual/RL fine-tuning approaches for large pretrained policies: sample inefficiency under sparse rewards
- Strong, clearly-stated empirical bar (≥90% success on 5/6 tasks) that is easy to benchmark against
- Theoretical grounding for "coherence" (non-degradation) is a meaningful property for practitioners worried about RL fine-tuning silently making a good pretrained policy worse

## Weaknesses

- IRL-derived rewards are only as good as the demonstrations used to learn them; performance on tasks with sparse/noisy demonstration coverage is unclear
- "Coherence" guarantees likely rest on assumptions (e.g., demonstration quality, coverage) that may not hold in messier real-world data regimes
- Available material doesn't clarify how compute/data costs compare against straightforward sparse-reward RL fine-tuning at scale

## Open Questions

- How does the learned reward's quality/coherence degrade as demonstration data becomes noisier or less complete, a realistic condition for large-scale robot datasets?
- How does this compare directly against other recent dense/process-reward approaches rather than only against plain sparse-reward RL?

## Significance

As VLA-scale "large behavior models" become the default starting point for robot policies, methods that let practitioners improve them off-policy via learned dense rewards — with a guarantee against silently regressing behavior — address a real deployment risk that pure RL fine-tuning currently carries.

## Links

- [Paper](https://arxiv.org/abs/2606.02194)
