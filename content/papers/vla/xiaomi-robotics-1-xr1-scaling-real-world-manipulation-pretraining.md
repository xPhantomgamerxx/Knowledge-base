---
title: "Xiaomi-Robotics-1 (XR-1): Scaling Real-World Manipulation Pretraining with Auto-Labeled UMI Data"
date: 2026-07-17
topic: VLA
tags: [vla, foundation-model, data-scaling, umi, auto-labeling, open-source, vla-posttraining]
source: https://arxiv.org/abs/2607.15330
venue: "arXiv"
---

## Summary

XR-1 is an open-source VLA foundation model pretrained on over 100,000 hours of real-world manipulation trajectories, collected largely via UMI-style handheld devices across 1,700+ scenarios. It couples a pretrained Qwen3-VL backbone with a Diffusion-Transformer action head via a Mixture-of-Transformers architecture, and uses a VLM-powered auto-labeling pipeline to segment and caption long raw trajectories, removing manual-annotation bottlenecks at this scale. It is a distinct model from the vault's already-logged Xiaomi-Robotics-U0 world-foundation-model.

## Key Contributions

- The largest reported real-world manipulation pretraining corpus (100,000+ hours) for an open VLA to date.
- An automatic VLM-based trajectory labeling pipeline that removes manual annotation as a scaling bottleneck.
- A Mixture-of-Transformers architecture pairing a VLM backbone with a DiT action expert, tuned for consumer-GPU deployment.

## Strengths

- Genuinely large-scale open real-world dataset with released weights and code (Apache 2.0).
- Reports strong benchmark margins: RoboCasa 74.5% (+2.6pp), RoboCasa365 57.4% (+23.2pp), VLABench 59.1% (+11.1pp), RoboDojo 13.93% (+58.3% relative) over prior open baselines.
- Deployment-conscious design: asynchronous inference, consumer-GPU-optimized.

## Weaknesses

- Data collected primarily via UMI-style proxy devices rather than the target robot embodiment, leaving an embodiment gap.
- Benchmark gains are self-reported and not yet independently verified on external real-hardware setups.
- The scale of pretraining data raises reproducibility and compute-cost barriers for outside labs.

## Open Questions

- How much of the reported gain comes from raw data scale versus the auto-labeling pipeline versus the MoT architecture?
- How does XR-1 compare directly against π0.7 or GR00T N1.7 on shared real-robot tasks?
- Does the UMI-collection embodiment gap meaningfully limit transfer to robots with different kinematics?

## Significance

A high-priority data-scaling entry directly matching the "scaling real/sim data pipelines for VLAs" cross-cutting priority: a large, open, auto-labeled real-world pretraining corpus is exactly the kind of scaling lever the field is currently missing at open-source scale.

## Links

- [Paper](https://arxiv.org/abs/2607.15330)
- [GitHub](https://github.com/XiaomiRobotics/Xiaomi-Robotics-1)
