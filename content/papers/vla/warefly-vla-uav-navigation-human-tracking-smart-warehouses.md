---
title: "WareFly-VLA: A Vision-Language-Action Framework for UAV Navigation and Human Tracking in Smart Warehouses"
date: 2026-10-06
topic: VLA
tags: [vla, uav, navigation, robotics]
source: https://arxiv.org/abs/2610.08526
venue: "arXiv (submitted to Robotics and Autonomous Systems, Elsevier)"
---

## Summary

WareFly-VLA applies the VLA paradigm to drones rather than manipulators, targeting warehouse-style target-approach and person-following tasks under occlusion, long-range search, altitude changes, and clutter. The authors built a dataset of 507 human-teleoperated flights in NVIDIA Isaac Sim (8,504 RGB transitions, each paired with a worker description and a 4-DoF control command) and benchmarked four open VLA models (SmolVLA, GR00T N1.7, π0, OpenVLA), finding sharp performance drops under strict generalization and that continuous action modeling outperforms discrete action tokens.

## Key Contributions

- A UAV-specific VLA dataset and benchmark for warehouse navigation and human tracking, built from teleoperated simulation flights.
- A systematic comparison of four existing manipulation-oriented open VLA models repurposed for drone control.
- An empirical finding that continuous action representations beat discrete action tokens for this UAV control setting.

## Strengths

- Extends VLA evaluation to aerial robotics, a domain that gets far less attention than tabletop/humanoid manipulation in current VLA literature.
- Testing under occlusion, long-range search, altitude change, and clutter together gives a reasonably realistic stress test for warehouse deployment scenarios.
- The continuous-vs-discrete action finding is a useful, generalizable data point for UAV-VLA design choices.

## Weaknesses

- Training/evaluation data comes entirely from simulation (Isaac Sim); no real-drone validation is mentioned in the available material.
- Repurposing manipulation-oriented VLA models (SmolVLA, GR00T, π0, OpenVLA) for drone control is a reasonable baseline choice but may understate what a UAV-native architecture could achieve.
- The authors themselves acknowledge performance falls sharply under strict generalization, a notable limitation.

## Open Questions

- Would a UAV-native action/observation encoding (rather than adapting manipulation-style VLAs) close the generalization gap observed?
- How well does simulation-trained performance transfer to a real quadrotor given typical sim-to-real gaps in aerodynamics and sensing?

## Significance

One of relatively few works applying the VLA framework to drones rather than arms/humanoids, highlighting both the opportunity (natural-language-directed UAV tasks) and the current generalization limitations when manipulation-focused VLA architectures are simply repurposed for flight.

## Links

- [Paper](https://arxiv.org/abs/2610.08526)
