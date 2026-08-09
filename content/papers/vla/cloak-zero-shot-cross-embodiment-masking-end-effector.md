---
title: "Cloak: Zero-Shot Cross-Embodiment Manipulation by Masking the End-Effector from the VLA"
date: 2026-06-22
topic: VLA
tags: [vla, cross-embodiment, zero-shot-transfer]
source: https://arxiv.org/abs/2606.22836
venue: "arXiv"
---

## Summary

Cloak masks the robot's own end-effector from the wrist-camera view during training — rendered out via known geometry rather than a learned segmentation model — so that a VLA trained on one gripper transfers zero-shot to unseen grippers, arms, and even a five-fingered hand.

## Key Contributions

- A geometry-based (not learned) end-effector masking method, avoiding the extra failure mode and compute cost of a segmentation model in the loop.
- Demonstrated zero-shot transfer to unseen grippers, arms, and a multi-fingered hand purely by removing the training embodiment's visual signature from the input.
- A simple, targeted intervention rather than a new architecture or training objective, making it easy to combine with existing VLA pipelines.

## Strengths

- The core insight — that a VLA can overfit to the visual appearance of the specific gripper it was trained with, and that removing this cue is enough to unlock zero-shot cross-embodiment transfer — is a clean, testable hypothesis and (if it holds broadly) a remarkably cheap fix relative to full cross-embodiment retraining.
- Using known geometry for masking rather than a learned segmenter avoids introducing new error sources and keeps the method simple to reproduce.

## Weaknesses

- Masking the end-effector removes information (e.g., current gripper aperture, finger contact state) that can be genuinely useful for fine manipulation, so there's a plausible trade-off between cross-embodiment transfer and single-embodiment precision that the paper would need to characterize carefully.
- Zero-shot transfer to a five-fingered hand is a large embodiment gap from a parallel-jaw training gripper; success here may depend heavily on task simplicity (e.g., pick-and-place) rather than dexterous manipulation that requires embodiment-specific finger coordination.
- Requires known end-effector geometry/kinematics for the masking render, which is a reasonable assumption for most robot arms but adds a setup dependency.

## Open Questions

- Does masking hurt performance on the training embodiment itself by removing useful proprioceptive-visual cues?
- How does transfer quality scale with task difficulty — does it hold for contact-rich or dexterous tasks, or mainly for coarse reaching/grasping?
- Is the effect specific to wrist-camera views, or does it also help with third-person camera setups where the arm is more visible?

## Significance

A simple, elegant intervention addressing a real and under-examined failure mode (embodiment-specific visual overfitting) in cross-embodiment VLA transfer — notable for its simplicity relative to the more architecturally heavy cross-embodiment methods appearing this quarter.

## Links

- [Paper](https://arxiv.org/abs/2606.22836)
