---
title: "MIM-VLA: Learning Physical Interaction Representations from Gripper Motor Feedback"
date: 2026-10-06
topic: VLA
tags: [vla, tactile-sensing, representation-learning, robotics]
source: https://arxiv.org/abs/2610.08425
venue: "arXiv"
---

## Summary

MIM-VLA learns to sense physical interaction properties (like object stiffness/resistance) using only the gripper's own motor signals, current, position, velocity, and a validity flag, encoded as a 128-dimensional interaction token, rather than requiring dedicated tactile or force sensors. In tests across 13 object pairs, it correctly identifies the higher-resistance object in 75.0% of trials, compared to 48.8% (near chance) for a SmolVLA baseline.

## Key Contributions

- A method for extracting physical-interaction information purely from standard gripper motor telemetry, without additional tactile or force sensing hardware.
- A compact 128-dimensional interaction token encoding recent motor current, position, velocity, and signal validity.
- A controlled 13-object-pair discrimination evaluation directly comparing against a baseline VLA (SmolVLA) that lacks this representation.

## Strengths

- Sensor-free (no additional tactile/force hardware) approach to physical property sensing is highly practical, since it works on any gripper with standard motor telemetry already available.
- Clear, large improvement over baseline (75.0% vs. 48.8%, near chance) on a well-defined discrimination task demonstrates the signal has genuine value.

## Weaknesses

- Tested on a narrow discrimination task (identifying the higher-resistance object among 13 pairs) rather than a full downstream manipulation task where this representation would need to improve actual task success.
- Motor-feedback-based sensing is inherently coarser than dedicated tactile sensors and likely cannot distinguish finer contact properties (texture, slip) that true tactile sensing captures.

## Open Questions

- Does incorporating the MIM-VLA interaction token into a full manipulation policy (not just a discrimination probe) measurably improve task success on contact-rich tasks?
- How does performance degrade with gripper type/hardware variation, given the representation is tied to motor-signal characteristics specific to a given gripper?

## Significance

A low-cost, sensor-free alternative to dedicated tactile sensing for contact-aware manipulation, relevant to the many robot platforms that lack tactile hardware but still need some notion of object compliance/resistance during grasping.

## Links

- [Paper](https://arxiv.org/abs/2610.08425)
