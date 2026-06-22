---
title: "Dexora: Open-source VLA for High-DoF Bimanual Dexterity"
date: 2026-05-18
topic: VLA
tags: [bimanual, dexterous-manipulation, open-source, teleoperation, dual-arm, ICRA]
source: https://arxiv.org/abs/2605.18722
venue: "ICRA 2026"
---

## Summary

Dexora is the first open-source VLA system targeting dual-arm, dual-hand high-DoF manipulation. It introduces a hybrid teleoperation pipeline that decouples gross arm kinematics (via a custom exoskeleton backpack) from fine finger motion (markerless tracking via Apple Vision Pro) and drives both a physical platform and an identical MuJoCo digital twin for scalable data collection.

## Key Contributions

- First open-source VLA natively designed for dual-arm, dual-hand manipulation at high DoF
- Hybrid teleoperation pipeline decoupling arm and finger control for efficient data collection
- Combined dataset: 100K simulated (361 hours) + 10K real teleoperated episodes (177.5 hours)
- Outperforms state-of-the-art VLA models on both basic and dexterous manipulation benchmarks
- Full code and datasets released for community use

## Significance

Fills a critical gap in the open-source robotics community by providing a reproducible, high-DoF bimanual VLA system along with a large-scale, dual-modality dataset that can serve as a benchmark for future dexterous manipulation research.

## Links

- [Paper](https://arxiv.org/abs/2605.18722)
- [GitHub](https://github.com/ZZongzheng0918/Dexora)
