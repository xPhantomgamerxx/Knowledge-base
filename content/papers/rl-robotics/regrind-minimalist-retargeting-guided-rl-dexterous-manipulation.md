---
title: "REGRIND: A Minimalist Retargeting-Guided Reinforcement Learning Recipe for Dexterous Manipulation"
date: 2026-07-13
topic: RL-Robotics
tags: [rl, dexterous-manipulation, sim-to-real, motion-retargeting]
source: https://arxiv.org/abs/2607.11874
venue: "arXiv"
---

## Summary

REGRIND retargets human hand-object motion to a robot reference that preserves spatial and contact relationships, then trains a residual RL policy in simulation to track object-centric keypoints along that reference, transferring zero-shot to hardware. It demonstrates fluid, human-like dexterous behaviors on contact-rich tool-use tasks (scissors, screwdriver) across two multi-fingered hands, with hardware analysis of what governs sim-to-real transfer.

## Key Contributions

- A "minimalist" retargeting-guided RL recipe, explicitly positioned against more complex pipelines — the paper's framing suggests a deliberate simplicity-first design choice worth noting given the field's tendency toward increasingly elaborate pipelines.
- Retargets human motion while explicitly preserving spatial and contact relationships rather than joint-angle mimicry alone, which matters for contact-rich tool use where contact geometry, not just hand pose, determines task success.
- Includes hardware analysis of what specifically governs sim-to-real transfer success, rather than only reporting aggregate success rates — a useful methodological addition for practitioners.
- Validated across two distinct multi-fingered hands, testing generalization across hardware rather than a single dexterous platform.

## Strengths

- Object-centric keypoint tracking (rather than joint-angle imitation) as the residual RL objective is a sensible design choice for contact-rich tool use, where what matters is the relationship between the tool and the task object, not exact hand kinematics.
- The explicit hardware analysis of sim-to-real transfer factors is genuinely useful for the field beyond this specific method — understanding *why* transfer succeeds or fails is scarcer in the literature than success-rate reporting alone.
- Testing on two different multi-fingered hands is a stronger generalization claim than typical single-platform dexterous manipulation papers.

## Weaknesses

- The paper is explicitly not VLA-specific — it is a general dexterous-manipulation sim-to-real RL recipe rather than a method for post-training or adapting VLA policies, so its direct applicability to the vault's VLA post-training focus is more limited than most other entries this week.
- "Minimalist" framing invites the question of what capability, if any, is traded away relative to more complex retargeting-plus-RL pipelines — this tradeoff isn't detailed in available coverage.

## Open Questions

- Does the object-centric keypoint tracking approach scale to tasks with more complex or changing tool geometries than scissors/screwdriver, where contact relationships are less stable?
- What specific factors did the hardware analysis identify as most predictive of sim-to-real transfer success, and are these actionable for other groups' sim-to-real pipelines?

## Significance

A useful, if VLA-adjacent rather than VLA-specific, contribution to dexterous manipulation sim-to-real RL, distinguished by its explicit hardware transfer analysis and cross-hand generalization testing — complements the already-logged "One Demonstration Is Enough for Real-World Robotic Reinforcement Learning" as another entry in the growing dexterous sim-to-real literature.

## Links

- [Paper](https://arxiv.org/abs/2607.11874)
