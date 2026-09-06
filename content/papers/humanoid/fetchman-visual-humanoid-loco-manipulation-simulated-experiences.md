---
title: "FetchMan: Learning Visual Humanoid Loco-Manipulation Policies from Simulated Experiences"
date: 2026-08-17
topic: Humanoid
tags: [humanoid, vla-posttraining, sim-to-real, reinforcement-learning, flow-matching, loco-manipulation]
source: https://arxiv.org/abs/2608.17027
venue: "arXiv"
---

## Summary

FetchMan trains a visual humanoid loco-manipulation policy entirely in simulation across more than 150,000 procedurally varied scenes, then deploys it zero-shot to a real Unitree G1 with no real-world data or per-scene tuning. The core finding is that behavior cloning on synthetic demonstrations alone hits a low performance ceiling, but refining the cloned flow-matching policy with online RL (Flow-GRPO) on a single sparse reward substantially improves real-world grasping behavior.

## Key Contributions

- A large-scale (150,000+ scene) sim-to-real pipeline for humanoid reach-and-pick tasks, paired with FetchMan-Bench, a simulation benchmark for evaluating visual loco-manipulation policies.
- Empirical demonstration that behavior cloning of synthetic demonstrations plateaus at a low ceiling — the cloned policy tends to grasp prematurely from too far away — while RL fine-tuning (via Flow-GRPO, which adapts online policy-gradient RL to flow-matching action generation) corrects this by learning to walk fully into reach before grasping.
- Zero-shot real-world transfer without any real-world fine-tuning data or per-scene calibration, achieving 73.3% success on unseen real-world scenes for single-object reach-and-pick.
- A practical application of Flow-GRPO's ODE-to-SDE conversion and reduced-denoising-step training to a real embodied control setting (rather than image/video generation, its original use case).

## Strengths

- The BC-then-RL ablation is a clean, interpretable result: it isolates exactly what RL fixes (premature grasping) rather than reporting only an aggregate success-rate improvement, which makes the contribution easy to trust and reuse.
- Achieving 73.3% zero-shot real-world success with no real-world data or per-scene tuning is a strong sim-to-real result, especially at the claimed scale of 150,000+ training scenes.
- Applying Flow-GRPO — originally developed for training flow-matching generative/image models via online RL — to a visuomotor control policy is a useful cross-pollination that other flow-matching-based VLA and loco-manipulation efforts are likely to adopt.

## Weaknesses

- Task scope is narrow: single-object reach-and-pick is a relatively simple loco-manipulation primitive compared to the multi-step, contact-rich tasks that other current humanoid work targets (e.g., insertion, tool use, bimanual coordination).
- 73.3% success, while solid for zero-shot sim-to-real, still leaves a substantial real-world failure rate that would need to close further before practical deployment; the paper doesn't clarify failure modes in detail.
- Relies on procedural scene generation at scale (150,000+ scenes) — the diversity and realism of this synthetic scene distribution relative to real deployment environments isn't independently validated beyond the reported success rate.

## Open Questions

- How does the Flow-GRPO refinement stage scale to more complex, multi-stage manipulation tasks beyond single-object reach-and-pick, where sparse rewards become harder to shape?
- What is the real-world sample efficiency if a small amount of real-world data were incorporated alongside the sim-only RL refinement — would it close the remaining ~27% failure gap significantly?
- How sensitive is zero-shot transfer to the specific procedural scene generation pipeline — would a different simulator or asset library reproduce similar results?

## Significance

A clear, well-isolated demonstration that RL post-training (via Flow-GRPO) is what pushes a simulation-trained visuomotor policy past the ceiling of behavior cloning alone for real-world humanoid deployment — reinforcing the broader field trend that RL fine-tuning, not just more imitation data, is necessary to close the sim-to-real gap for flow/diffusion-based control policies.

## Links

- [Paper](https://arxiv.org/abs/2608.17027)

