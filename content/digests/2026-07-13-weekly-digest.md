---
title: "Weekly Research Digest — 2026-07-13"
date: 2026-07-13
topics: [VLA, WorldModels, RL-Robotics]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 12
---

## Weekly Research Digest — 2026-07-13

> 12 new entries this week across 3 topic areas (July 7–13 papers plus belated additions from June not previously logged).

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/lift3d-vla-3d-geometry-dynamics-aware-vla]] Lift3D-VLA | arXiv 2607.06564 | 3D point-cloud VLA with GC-MAE dual-objective SSL; +10.8%/+11.1% on MetaWorld/RLBench over best prior VLA |
| [[papers/vla/lingbot-vla-20-open-source-cross-embodiment]] LingBot-VLA 2.0 (Robbyant/Ant Group) | blog release | 6B cross-embodiment VLA on 60K hrs / 20 morphologies / 17 manufacturers; <130ms inference, open-source |
| [[papers/vla/lerobot-v060-world-model-policies-open-robotics]] LeRobot v0.6.0 (Hugging Face) | blog / toolkit release | VLA-JEPA + FastWAM + LingBot-VA world model policies; closes the evaluate-correct-train loop in open robotics |
| [[papers/vla/policytrim-intrinsic-policy-efficiency-vla-rl]] PolicyTrim | arXiv 2606.22540 | RL post-training reduces VLA inference frequency without architectural changes or new demos |
| [[papers/vla/embodied-r15-evolving-physical-intelligence-foundation-models]] Embodied-R1.5 | arXiv 2606.11324 | 8B EFM on Qwen3-VL; SOTA on 16/24 embodied benchmarks, fine-tunes to VLA beating π₀.₅ |
| [[papers/vla/embodied-cpp-portable-inference-runtime-vla-wam]] Embodied.cpp | arXiv 2607.02501 | Portable C++ runtime for VLA/WAM deployment on CPU/GPU/NPU; latency-first closed-loop design |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/rynnworld-4d-4d-embodied-world-model-robotic-manipulation]] RynnWorld-4D (Alibaba) | arXiv 2607.06559 | First world model co-generating RGB+depth+optical flow in one denoising loop; strong bimanual Sim2Real |
| [[papers/world-models/rynnworld-teleop-action-conditioned-world-model-digital-teleoperation]] RynnWorld-Teleop (Alibaba) | arXiv 2607.06558 | Digital teleoperation: replaces physical robot with generative world model for data synthesis at 40+ FPS |
| [[papers/world-models/dswam-dual-system-world-action-foundation-model-fine-grained-manipulation]] DSWAM | arXiv 2607.04927 | Dual-system WAM: System 1 executor + optional System 2 VLM planner for complex instruction decomposition |
| [[papers/world-models/from-world-models-to-world-action-models-tutorial-robotics]] WM→WAM Tutorial | arXiv 2607.00836 | Concise design-space taxonomy covering 4 WAM paradigms; clearest conceptual roadmap for the WM→WAM transition |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/dvla-rl-reinforcement-learning-denoising-trajectories-discrete-diffusion-vla]] dVLA-RL | arXiv 2606.23623 | PPO-style RL for discrete diffusion VLAs via denoising-trajectory MDP; SOTA on LIBERO |
| [[papers/rl-robotics/taccorl-tactile-feedback-vla-simulation-cotraining]] TacCoRL | arXiv 2606.11743 | Tactile feedback in VLAs via sim-real co-training + RL on contact rollouts; no large-scale tactile pretraining needed |

---
*Generated automatically. All entries verified via web search.*
