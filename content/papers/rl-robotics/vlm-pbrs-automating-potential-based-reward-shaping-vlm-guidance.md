---
title: "Automating Potential-based Reward Shaping with Vision Language Model Guidance"
date: 2026-06-25
topic: RL-Robotics
tags: [reward-shaping, vlm-reward-model, sparse-reward-rl, preference-learning]
source: https://arxiv.org/abs/2606.27180
venue: "arXiv"
---

## Summary

Henrik Müller and Daniel Kudenko (L3S Research Center, Leibniz University Hannover) propose VLM-PBRS, a method that automates potential-based reward shaping (PBRS) by learning the potential function from a vision-language model's preferences over pairs of images, rather than requiring a human-engineered heuristic. Because PBRS is theoretically guaranteed to preserve the optimal policy regardless of the shaping function used, this lets practitioners plug in a learned, VLM-derived potential without sacrificing the standard optimality guarantees of the underlying MDP.

## Key Contributions

- A pipeline that queries a lightweight VLM for pairwise preferences between state images (e.g., "which of these two states is closer to the goal?") and trains a potential function model from these preference labels, removing the need for hand-crafted shaping heuristics.
- Preserves the classical PBRS theoretical guarantee (policy invariance) even when the learned potential function is updated online/dynamically during training, allowing continuous refinement of the potential without introducing bias toward suboptimal policies.
- Positions VLMs as a cheap, scalable substitute for human preference annotators specifically for the reward-shaping sub-problem (rather than for full reward learning), narrowing VLM involvement to a role where errors are more contained by the PBRS formalism.
- Demonstrates improved sample efficiency in sparse-reward settings and claims increased robustness to reward hacking relative to naive VLM-as-reward approaches.

## Strengths

- Building on PBRS specifically (rather than learning an unconstrained reward function from the VLM) is a principled design choice — it bounds the damage a noisy/biased VLM preference signal can do, since the optimal policy set is provably unchanged.
- Using preferences rather than absolute scalar potentials sidesteps well-known VLM calibration issues (VLMs are typically much better at relative/comparative judgments than at outputting well-calibrated absolute scores).
- The "low-cost, lightweight VLM" framing is a practical contribution: many VLM-reward papers assume access to large proprietary models; if a small VLM suffices for the shaping role, that's a meaningful accessibility improvement.
- Allowing the potential function to be updated dynamically during training (rather than fixed upfront) should better track a non-stationary policy's actual behavior/exploration frontier.

## Weaknesses

- Reward shaping only accelerates learning toward whatever the base sparse reward already specifies as "success" — it doesn't help if the sparse reward itself is misspecified, so VLM-PBRS inherits any weaknesses of the underlying task reward design.
- The quality of the shaping signal is bottlenecked by the VLM's visual/spatial reasoning about task progress from single images or image pairs; tasks with progress that isn't visually obvious from a static frame (e.g., requiring memory of past states, force/contact information, or fine-grained manipulation subtleties) seem poorly suited to this preference-over-images approach.
- Evaluation appears to be on MuJoCo-style / simulated continuous-control benchmarks rather than real robotic manipulation with a genuine vision-language stack; the extent to which VLM preference quality holds up on cluttered, realistic robot scenes (vs. clean simulated renders) is untested.
- Querying a VLM for pairwise preferences repeatedly during training introduces inference cost/latency that scales with training steps; the paper's summarized results don't clearly quantify this overhead versus the sample-efficiency gains.

## Open Questions

- How robust is the learned potential function to VLM preference inconsistency/noise, and is there a a formal characterization of how much noise the PBRS guarantee can tolerate before empirical performance degrades?
- Does the approach scale to real-world robot manipulation tasks with a genuine camera-based observation pipeline, or does it remain validated only in simulation?
- Could VLM preference queries be cached/amortized (e.g., via a distilled small reward model) to reduce the online inference cost during RL training?
- How does VLM-PBRS compare against alternative automated reward-shaping baselines that don't use VLMs (e.g., learned progress estimators from offline data, or count-based/curiosity exploration bonuses) on the same benchmarks?

## Significance

VLM-PBRS is a notable example of constraining VLM-derived reward signals inside a theoretically-safe reward-shaping formalism (PBRS) rather than letting the VLM define the reward outright, offering a template for using foundation models as reward-shaping assistants without giving up classical RL optimality guarantees.

## Links

- [Paper](https://arxiv.org/abs/2606.27180)
