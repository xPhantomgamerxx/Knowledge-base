---
title: "Z-1: Efficient Reinforcement Learning for Vision-Language-Action Models"
date: 2026-06-30
topic: VLA
tags: [vla-posttraining, rl-finetuning, grpo, flow-matching, pi0.5, RoboCasa, online-rl]
source: https://arxiv.org/abs/2606.31846
venue: "arXiv"
---

## Summary

Z-1 is an RL post-training framework for flow-based VLA models, built on top of π0.5, that moves beyond pure behavior cloning by applying task-wise Group Relative Policy Optimization (GRPO) across 24 standard RoboCasa manipulation tasks. Starting from SFT on only publicly released RoboCasa demonstrations, Z-1's RL stage raises the average success rate from 67.4% to 80.6% (+13.2 points), addressing the common limitation that BC-trained VLA policies cannot learn from their own rollout failures.

## Key Contributions

- Combines shared-prefix rollout construction with tree-structured trajectory branching to make online GRPO rollout collection more compute-efficient for flow-based action generation
- Introduces completion-aware reward calibration to give more informative learning signal than sparse task-success rewards alone
- Uses selective joint training of the VLM backbone and the action expert (rather than optimizing only the action head or only the full model), balancing stability and adaptability during RL
- Achieves state-of-the-art results on the RoboCasa benchmark under the public-demonstration-data setting: 80.6% average success across 24 tasks, a 13.2-point gain over the SFT initialization and better than previously published SOTA models
- Provides ablations isolating the contribution of each design choice (rollout sharing, tree branching, reward calibration, joint training strategy)

## Strengths

- Targets a real, well-known gap in current VLA training pipelines — behavior cloning cannot exploit the policy's own failed rollouts — with a concrete, evaluated RL recipe rather than a purely conceptual proposal
- The shared-prefix and tree-structured rollout construction is a sensible efficiency trick specifically suited to flow-matching/diffusion action generation, where sampling many rollouts is expensive
- Built on a strong, realistic base model (π0.5) and evaluated across 24 diverse RoboCasa tasks rather than a handful of cherry-picked ones, giving a broader picture of where RL helps and where it doesn't
- Uses only publicly released demonstration data for the SFT stage, making the starting point more reproducible than approaches relying on proprietary datasets

## Weaknesses

- The paper itself reports Z-1 is less competitive than X-WAM on stove tasks, indicating long-horizon transport, spatial reasoning, and recovery from intermediate failures remain difficult even after RL post-training — the method does not uniformly close the gap on hard task categories
- Evaluation is confined to RoboCasa (a simulated household-tasks benchmark); no real-robot results are reported, so it's unclear how the GRPO recipe's gains transfer under real sensor noise, contact dynamics, and physical latency
- Online RL post-training inherently requires many rollouts even with the efficiency tricks, and the paper does not report absolute compute/wall-clock cost relative to the SFT stage, making it hard to judge practicality against pure BC pipelines

## Open Questions

- How well does the completion-aware reward calibration generalize to tasks without well-defined intermediate completion signals (e.g., truly open-ended manipulation)?
- Would the shared-prefix rollout / tree-branching efficiency gains hold up on real hardware, where rollout branching is far more constrained than in simulation?
- Does the selective joint VLM/action-expert training strategy generalize to other flow-based VLA backbones beyond π0.5, or is it tuned specifically to that model's architecture?

## Significance

Z-1 is a concrete data point in the emerging trend of applying RL (specifically GRPO-style group-relative methods popularized in LLM post-training) to flow-based VLA policies, demonstrating a non-trivial (+13.2 point) improvement over SFT purely from online policy optimization — evidence that RL post-training, not just larger/better pretraining data, is becoming a meaningful lever for VLA capability gains.

## Links

- [Paper](https://arxiv.org/abs/2606.31846)
