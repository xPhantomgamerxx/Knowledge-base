---
title: "Weekly Research Digest — 2026-05-11"
date: 2026-05-11
topics: [VLA, WorldModels, RL-Robotics]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 8
---

## Weekly Research Digest — 2026-05-11

> 8 new entries this week across 3 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/anticipation-vla-long-horizon-embodied-tasks-subgoal-generation]] Anticipation-VLA | arXiv 2605.01772 | Hierarchical VLA with adaptive anticipation model that recursively generates visual subgoals to tackle compounding errors in long-horizon tasks |
| [[papers/vla/roboalign-test-time-reasoning-language-action-alignment-vla]] RoboAlign | arXiv 2603.21341 | Two-stage SFT+RL framework that aligns language-action token representations, yielding 106.6% real-world improvement over SFT baseline with <1% extra data |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/being-h07-latent-world-action-model-egocentric-videos]] Being-H0.7 | arXiv 2605.00078 | Latent world-action model using learnable query slots as a compact reasoning interface, pretrained on large-scale egocentric video instead of pixel prediction |
| [[papers/world-models/roboalign-r1-multimodal-reward-alignment-robot-video-world-models]] RoboAlign-R1 | arXiv 2605.03821 | Introduces RobotWorldBench and GRPO-based RL post-training to align video world models with decision-relevant quality metrics rather than pixel reconstruction |
| [[papers/world-models/do-world-action-models-generalize-better-than-vlas-robustness-study]] Do WAMs Generalize Better than VLAs? | arXiv 2603.22078 | First large-scale robustness comparison showing WAMs outperform VLAs under visual and language perturbation on augmented LIBERO-Plus and RoboTwin 2.0-Plus benchmarks |
| [[papers/world-models/mwm-mobile-world-models-action-conditioned-consistent-prediction]] MWM: Mobile World Models | arXiv 2603.07799 | Action-conditioned consistency post-training and ICSD distillation to eliminate rollout drift in navigation world models under multi-step planning |
| [[papers/world-models/mask-world-model-predicting-what-matters-robust-robot-policy-learning]] Mask World Model | arXiv 2604.19683 | Predicts semantic masks instead of pixels in a video diffusion world model, imposing a geometric bottleneck that filters visual distractors and improves generalization |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/flashsac-fast-stable-off-policy-rl-high-dimensional-robot-control]] FlashSAC | arXiv 2604.04539 | Stabilized off-policy SAC with norm bounding and reduced gradient updates, outperforming PPO on 60+ tasks with humanoid sim-to-real training time cut from hours to minutes |

---
*Generated automatically. All entries verified via web search.*
