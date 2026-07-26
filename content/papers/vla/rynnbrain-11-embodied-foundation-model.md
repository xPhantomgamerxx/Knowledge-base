---
title: "RynnBrain 1.1: Towards More Capable and Generalizable Embodied Foundation Model"
date: 2026-07-20
topic: VLA
tags: [embodied-foundation-model, 3d-grounding, cross-embodiment, humanoid, Alibaba-DAMO]
source: https://arxiv.org/abs/2607.17977
venue: "arXiv"
---

## Summary

RynnBrain 1.1 is Alibaba DAMO Academy's successor to RynnBrain 1.0, a family of embodied foundation models spanning 2B, 9B, and 122B-A10B (sparse-MoE) scales trained under a unified spatio-temporal, physically-grounded framework for embodied perception, spatial reasoning, localization, grounding, and planning. It adds two new capabilities over 1.0 — instruction-conditioned contact-point and in-plane grasp-orientation prediction, and native metric 3D grounding (3D bounding boxes from single RGB images with camera intrinsics) — and pairs the perception/reasoning backbone with RynnBrain-VLA, a unified cross-embodiment action model evaluated on real humanoid and dexterous-hand hardware.

## Key Contributions

- Scales a single unified decoder-only vision-language architecture (dense and sparse-MoE variants) across 2B/9B/122B-A10B parameters, with the 122B-A10B model claimed as the first embodied foundation model at that scale
- Introduces instruction-conditioned contact-point prediction with in-plane grasp orientation, giving the model explicit "where and how to interact with objects" outputs beyond generic localization
- Extends grounding from 2D image-plane localization to native 3D grounding, predicting metric 3D bounding boxes (position, dimensions, orientation) from a single RGB image plus camera intrinsics
- Introduces RynnBrain-VLA, which bridges the perception/reasoning backbone into real-robot control through a unified cross-embodiment action space, and evaluates it on three heterogeneous platforms — Unitree G1 (humanoid), Astribot-S1 (bimanual), and a Tianji-Wuji dexterous hand — across furniture interaction, food preparation, and table-service tasks, reporting improvements over Qwen-based VLA baselines
- Releases RynnBrain-Bench, an evaluation suite of 3,616 video clips and roughly 12,000 curated open-ended questions spanning Object Cognition, Spatial Cognition, Grounding, and Pointing, alongside open model weights (2B/8B checkpoints on Hugging Face) and code on GitHub

## Strengths

- Demonstrates a genuinely unified model across three very different scales (2B to 122B-A10B) rather than releasing disjoint architectures per scale, which supports easier comparison of how capability scales with size
- Cross-embodiment evaluation on three real, structurally different robots (bipedal humanoid, bimanual mobile manipulator, dexterous hand) is a meaningfully broader real-hardware test than most VLA papers that stick to a single arm/gripper setup
- Extending grounding to metric 3D (not just 2D pixel boxes) and adding explicit contact-point/grasp-orientation prediction directly targets information that downstream manipulation policies actually need, rather than only general-purpose VQA-style grounding
- Open release of weights, benchmark, and code (RynnBrain-Bench, Hugging Face checkpoints, GitHub repo) supports independent verification and reuse, unlike many industry lab reports that only publish numbers

## Weaknesses

- As a corporate/lab technical report rather than a peer-reviewed paper, the comparison against "Qwen-based VLA baselines" is self-selected; it is unclear whether the strongest available open or closed competitors (beyond Qwen-derived VLAs) were included, so the magnitude of claimed improvement should be treated cautiously
- The publicly documented material does not detail failure modes or task success-rate breakdowns per embodiment/task category — claims of "strong cross-platform generalization" are not accompanied by transparent per-task numbers in the material reviewed, making it hard to judge where the model still struggles
- Contact-point and 3D grounding predictions are evaluated primarily via the newly introduced RynnBrain-Bench, a benchmark designed by the same team, which raises the usual concern about benchmark-model co-design inflating reported gains relative to independent evaluation
- The 122B-A10B model's real-hardware deployment characteristics (latency, on-robot compute requirements) are not addressed in the available material, despite this being a critical practicality question for a model at that scale intended for real-time robot control

## Open Questions

- How much of RynnBrain-VLA's cross-embodiment success comes from the unified action-space design versus simply from the scale and quality of the underlying RynnBrain 1.1 perception backbone?
- Do the contact-point and 3D-grounding improvements translate into measurable gains in downstream manipulation success rate, or primarily in perception-benchmark scores?
- How does inference latency and compute cost scale across the 2B/9B/122B-A10B variants when deployed for real-time closed-loop robot control, particularly on the largest MoE model?
- How does RynnBrain 1.1 compare against other recent large embodied foundation models (not just Qwen-based VLAs) on both RynnBrain-Bench and independent, third-party benchmarks?

## Significance

RynnBrain 1.1 is a notable data point in the trend toward large, unified embodied foundation models that combine general spatio-temporal/physical grounding with explicit interaction-relevant outputs (contact points, 3D boxes) and validate the resulting perception backbone through a cross-embodiment action model on real, diverse hardware — evidence that industry labs are pushing embodied foundation models toward genuinely general-purpose physical reasoning rather than task- or robot-specific policies.

## Links

- [Paper](https://arxiv.org/abs/2607.17977)
- [GitHub](https://github.com/alibaba-damo-academy/RynnBrain)
