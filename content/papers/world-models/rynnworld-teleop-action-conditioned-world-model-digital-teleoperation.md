---
title: "RynnWorld-Teleop: An Action-Conditioned World Model for Digital Teleoperation"
date: 2026-07-07
topic: WorldModels
tags: [data-synthesis, teleoperation, hand-motion, video-diffusion, sim2real, alibaba, scalable-data]
source: https://arxiv.org/abs/2607.06558
venue: "arXiv 2607.06558"
---

## Summary

RynnWorld-Teleop introduces digital teleoperation: a paradigm that decouples robot data collection from physical robot access by replacing the physical robot with a generative world model. An operator's hand-pose stream drives a robot-centric video DiT to synthesize high-fidelity egocentric manipulation videos from a single reference image, running at 40+ FPS on a single H100 GPU.

## Key Contributions

- Digital teleoperation paradigm that replaces physical robot + teleop hardware with a generative world model — enabling data generation from diverse reference images × hand-motion combinations
- Depth-aware skeletal conditioning and progressive human-to-robot training on a video Diffusion Transformer, enabling high-fidelity robot-perspective video synthesis from human hand motion alone
- Zero-shot Sim2Real transfer: policies trained exclusively on digitally teleoperated data achieve effective real-robot performance on dexterous bimanual tasks

## Significance

Addresses the data bottleneck for robot learning by removing the physical robot from the data collection loop entirely; scalable because any human hand motion + any reference scene image can produce new demonstration data at 40+ FPS.

## Links

- [Paper](https://arxiv.org/abs/2607.06558)
- [Pebblous blog](https://blog.pebblous.ai/blog/world-model-robot-data-synthesis/en/)
