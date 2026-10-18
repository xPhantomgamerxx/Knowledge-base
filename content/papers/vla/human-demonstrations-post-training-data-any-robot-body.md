---
title: "Human Demonstrations as Post-Training Data for Any Robot Body: Retargeting the Object, Not the Hand"
date: 2026-10-14
topic: VLA
tags: [vla, cross-embodiment, post-training, data-augmentation, human-video, vla-posttraining]
source: https://arxiv.org/abs/2610.20351
venue: "arXiv"
---

## Summary

This paper flips the usual human-to-robot retargeting problem: instead of retargeting the human hand's kinematics to each robot's end-effector (which has to be redone per embodiment and per hand design), it retargets the manipulated *object's* trajectory, and treats that as the shared, embodiment-agnostic supervision signal for VLA post-training across arbitrary robot bodies.

## Key Contributions

- An object-centric retargeting formulation that sidesteps hand/gripper-specific kinematic mapping, making one human demonstration reusable as post-training data for multiple, structurally different robot embodiments.
- A framing of human video as a general-purpose post-training data source for "any robot body," rather than a dataset tied to one target platform.

## Strengths

- Object-trajectory supervision is a natural fit for task success, since most manipulation tasks are defined by what happens to the object, not by the exact joint trajectory of the actor moving it.
- If the retargeting genuinely generalizes across embodiments without redesign, it meaningfully lowers the marginal cost of adding a new robot body to an existing human-video post-training pipeline.

## Weaknesses

- Object-centric retargeting discards information about *how* the demonstrator's hand/arm achieved the motion (e.g., compliant grasp adjustments, finger pre-shaping), which can matter for contact-rich or dexterous tasks where the path to the object pose, not just the final trajectory, determines success.
- As with most human-video-to-robot pipelines, the approach is only as good as the implicit assumption that the target embodiment's action space can realize the retargeted object trajectory — this likely breaks down for embodiments with very different reachability or dexterity.

## Open Questions

- How does the method handle tasks where the same object trajectory is achievable by very different grasp strategies, some of which are infeasible for a given robot's gripper?
- What is the actual cross-embodiment transfer gain measured against embodiment-specific hand retargeting baselines, on the same task set?

## Significance

Fits the cross-cutting "scaling real data pipelines for VLAs" priority directly: it is a data-generation recipe aimed at making one human demonstration corpus reusable post-training data across many robot bodies, rather than a single-embodiment imitation method.

## Links

- [Paper](https://arxiv.org/abs/2610.20351)
