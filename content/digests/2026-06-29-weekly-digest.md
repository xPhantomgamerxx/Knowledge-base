---
title: "Weekly Research Digest — 2026-06-29"
date: 2026-06-29
topics: [VLA, WorldModels, RL-Robotics]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 13
---

## Weekly Research Digest — 2026-06-29

> 13 new entries this week across 3 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/qwen-vla-unifying-vision-language-action-modeling]] Qwen-VLA | arXiv 2605.30280 | Alibaba unified VLA across manipulation, navigation, and embodiments; 97.9% LIBERO, strong cross-embodiment OOD |
| [[papers/vla/robots-need-more-than-vla-and-world-models]] Robots Need More than VLA and World Models | arXiv 2606.06556 | Position paper from ETH/Tübingen/IIT: identifies four missing "interfaces" (data, embodiment, world-model, reward) blocking VLA scaling |
| [[papers/vla/geometric-action-model-robot-policy-learning]] Geometric Action Model (GAM) | arXiv 2606.17046 | KAIST/ETH Zurich: repurposes 3D geometric foundation model as robot policy substrate; 55× faster than VLA/WAM baselines |
| [[papers/vla/la4vla-learning-to-act-without-seeing]] LA4VLA | arXiv 2606.27295 | Language-action pretraining without vision decouples language-grounding from visual shortcuts; +45 pp real-world success |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/nvidia-cosmos-3-omnimodal-world-models-physical-ai]] NVIDIA Cosmos 3 | Technical Report 2606.02800 | World's first open omnimodal world model (text/image/video/audio/action); #1 WorldModelBench Robot, #1 RoboArena policy |
| [[papers/world-models/veo-act-frontier-video-models-robot-manipulation]] Veo-Act | arXiv 2604.04502 | Benchmarks Veo-3 frontier video model as zero-shot robot planner; hierarchical Veo-3 + VLA framework closes the low-level gap |
| [[papers/world-models/oa-wam-object-addressable-world-action-model]] OA-WAM | arXiv 2605.06481 | Object-addressable slot states (persistent address + time-varying content) solve identity entanglement in holistic WAMs |
| [[papers/world-models/flash-wam-modality-aware-distillation-world-action-models]] Flash-WAM | arXiv 2606.05254 | Modality-aware consistency distillation solves video-action SNR asymmetry; enables few-step WAM inference |
| [[papers/world-models/aha-wam-asynchronous-horizon-adaptive-world-action-modeling]] AHA-WAM | arXiv 2606.09811 | Dual DiT (low-freq world planner + high-freq action DiT) with OVCR; 92.80% RoboTwin, 24 Hz, 4.6× speedup |
| [[papers/world-models/efficient-wam-1b-low-cost-future-imagination]] Efficient-WAM | arXiv 2606.10040 | 1B-parameter WAM with coarse future guidance; ~100 ms/chunk, 30× speedup, showing photorealistic video is unnecessary |
| [[papers/world-models/kairos-native-world-model-stack-physical-ai]] Kairos | arXiv 2606.16533 | ACE Robotics 4B open world model; hybrid linear attention, #1 WorldModelBench Robot, beats 28B models at fraction of cost |
| [[papers/world-models/imagewam-image-editing-vs-video-generation-world-action-models]] ImageWAM | arXiv 2606.19531 | Replaces video generation with single image editing; 6× FLOP and 4× latency reduction — next-frame editing is sufficient |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/march-model-assisted-rl-humanoid-perceptive-control-sparse-footholds]] MARCH | arXiv 2606.10288 | Model-assisted RL (CLF reward from simplified dynamics) + teacher-student distillation for humanoid sparse-foothold locomotion |

---
*Generated automatically. All entries verified via web search.*
