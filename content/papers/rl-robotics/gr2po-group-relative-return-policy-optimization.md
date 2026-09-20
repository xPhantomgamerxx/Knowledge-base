---
title: "GR2PO: Group Relative Return Policy Optimization for Continuous Robot Control"
date: 2026-09-16
topic: RL-Robotics
tags: [reinforcement-learning, critic-free, grpo, continuous-control, edge-deployment]
source: https://arxiv.org/abs/2609.19850
venue: "arXiv"
---

## Summary

Extends GRPO-style critic-free policy optimization to dense-reward continuous robot control by estimating discounted returns from parallel trajectory rollouts and applying group normalization at each rollout timestep, avoiding the need to train a value network while still capturing long-term outcomes.

## Key Contributions

- Identifies that naive critic-free GRPO-style methods fail on dense-reward continuous control because they apply immediate rewards directly rather than accounting for long-term returns
- Introduces return estimation combined with per-timestep group normalization for relative advantage computation without a learned critic
- Demonstrates competitive performance against actor-critic baselines (PPO, SAC) and tests edge-device inference feasibility on NVIDIA Jetson TX2

## Strengths

- Removes a real source of instability/overhead in continuous-control RL (value-function approximation error) while retaining long-horizon credit assignment via return estimation
- Practical edge-deployment testing (Jetson TX2) is a nice applied touch not always present in RL algorithm papers

## Weaknesses

- Evaluated on classic continuous-control benchmarks (Ant, Walker2d, Humanoid) rather than real manipulation or VLA fine-tuning settings, so relevance to today's VLA post-training pipelines is inferential, not demonstrated
- Group-relative methods require multiple parallel rollouts per update, which is fine in simulation but can be costly for real-robot RL where GRPO-style approaches often struggle
- Code is not yet released ("after acceptance"), so claims are not independently verifiable yet

## Open Questions

- Does GR2PO's advantage over actor-critic methods hold when applied to real-robot or VLA fine-tuning settings, where rollouts are far more expensive than in MuJoCo-style benchmarks?
- How sensitive is performance to group size, and what's the practical rollout budget needed for stable training?

## Significance

GRPO-derived critic-free methods have become popular for LLM RL and are increasingly explored for VLA/robot RL; extending the recipe soundly to dense-reward continuous control addresses a real gap in that transfer.

## Links

- [Paper](https://arxiv.org/abs/2609.19850)
