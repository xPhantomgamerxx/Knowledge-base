---
title: "SPOT: Spatial Perception-Oriented Long-Horizon Humanoid Teleoperation"
date: 2026-09-07
topic: Humanoid
tags: [teleoperation, data-collection, vr-interface, egocentric-perception]
source: https://arxiv.org/abs/2609.07933
venue: "arXiv"
---

## Summary

Introduces a VR teleoperation interface that decouples the operator's visual exploration from robot head/camera/torso actuation by rendering a robot-mounted binocular fisheye stream onto a stabilized virtual hemisphere, so operators can look around within a wide-field view without commanding the robot's cameras, aimed at improving long-horizon humanoid demonstration collection.

## Key Contributions

- Viewpoint-decoupled, IMU-stabilized wide-field stereo rendering: fisheye stream sampled via equisolid projection onto a hemispherical display, counter-rotated to stabilize the world frame independent of the robot's actual camera motion
- Combines a robot-mounted binocular fisheye camera with a wide stereoscopic VR display and "free-looking" that separates operator gaze from robot actuation
- Evaluates across four perception-critical tasks with ten human operators, reporting consistent reductions in completion time, search time, and grasp attempts versus both exocentric and conventional egocentric teleoperation baselines

## Strengths

- Addresses a genuinely underexplored bottleneck: most humanoid teleop interfaces couple operator head motion directly to robot camera motion, which is known to cause search inefficiency and motion sickness on long-horizon tasks — SPOT's decoupling is a clean, well-motivated fix
- Ten-operator user study with multiple task types and multiple named baselines gives reasonably credible comparative evidence
- Directly targets the data-collection bottleneck that limits scale for humanoid imitation-learning datasets, complementing policy-architecture papers

## Weaknesses

- A ten-operator study, while more rigorous than many teleop papers, is still a small human-subjects sample; individual operator skill/variance could dominate results
- No discussion of whether policies trained on SPOT-collected data actually perform better downstream than policies trained with conventional teleop — the evaluation is of the interface's ergonomics, not its downstream data quality
- Hardware dependency on a specific fisheye/hemispherical rendering setup may limit rapid adoption relative to simpler head-mounted interfaces

## Open Questions

- Does data collected via SPOT translate into measurably better downstream VLA policy performance compared to data from conventional teleop interfaces?
- How does SPOT's decoupled-gaze paradigm interact with tasks that genuinely require synchronized head/camera movement (e.g., active visual search while moving)?
- Does the approach scale to full whole-body teleoperation (including locomotion) or is it primarily validated for stationary/manipulation-focused tasks?

## Significance

Tackles the data-collection side of the humanoid VLA pipeline rather than the model side, which is increasingly recognized as the key lever for scaling humanoid generalization — better teleop ergonomics directly increases the rate and quality of demonstration collection.

## Links

- [Paper](https://arxiv.org/abs/2609.07933)
