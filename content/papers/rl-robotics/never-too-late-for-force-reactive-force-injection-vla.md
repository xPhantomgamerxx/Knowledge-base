---
title: "Never Too Late for Force: Accelerating VLA Post-Training with Reactive Force Injection"
date: 2026-07-17
topic: RL-Robotics
tags: [vla, force-control, post-training, contact-rich, force-injection, rss-workshop, manipulation]
source: https://arxiv.org/abs/2607.14236
venue: "arXiv 2607.14236 / RSS 2026 Workshop on Foundation Models for Robot Planning (FM4RoboPlan)"
---

## Summary

This paper proposes Reactive Force Injection, a VLA post-training strategy that accelerates adaptation to contact-rich tasks by injecting force feedback signals into the training loop at key interaction moments. The method targets the common failure mode where VLAs trained on visual and proprioceptive data lack the force-aware reactivity required for precise contact manipulation, without requiring large-scale force-labeled pretraining datasets.

## Key Contributions

- Reactive Force Injection: post-training paradigm that selectively injects force feedback at contact-adjacent states during VLA fine-tuning
- Accelerates convergence to contact-rich manipulation compared to vision-only post-training baselines
- Compatible with standard VLA fine-tuning pipelines; does not require purpose-built force pretraining data
- Oral presentation at RSS 2026 FM4RoboPlan workshop, indicating community recognition

## Significance

Provides a practical, data-efficient route to endow pretrained VLAs with force-aware reactivity post hoc — addressing the final-mile gap between visually competent VLAs and the precise, force-sensitive control demanded by industrial and dexterous manipulation tasks.

## Links

- [Paper](https://arxiv.org/abs/2607.14236)
