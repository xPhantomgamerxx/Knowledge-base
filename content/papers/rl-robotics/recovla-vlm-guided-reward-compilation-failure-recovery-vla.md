---
title: "ReCoVLA: VLM-Guided Reward Compilation for Failure Recovery in Vision-Language-Action Policies"
date: 2026-06-08
topic: RL-Robotics
tags: [rl, vla, reward-modeling, failure-recovery, sim-to-real, vla-posttraining]
source: https://arxiv.org/abs/2606.09630
venue: "arXiv"
---

## Summary

ReCoVLA is a failure-conditioned residual recovery framework that keeps a pretrained VLA frozen and uses an external VLM as a semantic reward selector — predicting a recovery descriptor and reward mask that drives in-simulation residual-policy RL training, followed by zero-shot sim-to-real deployment. It raises average simulation success from 36.7% to 66.7%, and outperforms baselines by 18.3 percentage points in physical Fetch robot experiments.

## Key Contributions

- Keeps the base VLA entirely frozen and learns only a residual recovery policy, which limits the risk of catastrophic forgetting or capability regression from RL fine-tuning of the full policy.
- Uses a VLM as a semantic reward selector to generate task-relevant recovery descriptors and reward masks automatically, avoiding hand-engineered reward functions for each failure type.
- Demonstrates zero-shot sim-to-real transfer of the residual recovery policy, with a physical validation on a real Fetch robot rather than simulation-only results.

## Strengths

- The frozen-base-policy-plus-residual-recovery design is architecturally conservative and practical: it doesn't risk degrading the base VLA's general competence to fix specific failure recovery behavior.
- Real physical robot validation (Fetch), not just simulation, and an 18.3pp improvement over baselines gives a concrete, checkable claim beyond simulation-only results.
- Automating reward specification via VLM-generated descriptors and masks reduces the reward-engineering burden that has historically limited RL applicability to diverse failure types.

## Weaknesses

- Reliance on the VLM's ability to correctly identify failure states and generate appropriate recovery descriptors means errors in VLM judgment propagate directly into the RL reward signal — the paper's handling of VLM misjudgment is not detailed in available coverage.
- Simulation success rate of 66.7% after improvement, while a large jump from 36.7%, still leaves roughly a third of simulated recovery attempts failing, suggesting substantial headroom remains.

## Open Questions

- How does ReCoVLA's residual recovery policy generalize to failure modes not represented in its simulation training distribution?
- Does the VLM reward selector need to be re-tuned or re-prompted per robot embodiment, or does it transfer across platforms with the same base VLA?

## Significance

A well-scoped contribution to the growing body of VLA failure-recovery work in this vault (FAR, HAVE, CoRe), notable for combining frozen-base-policy conservatism with automated VLM-driven reward generation and real hardware validation.

## Links

- [Paper](https://arxiv.org/abs/2606.09630)
