---
title: "Weekly Research Digest — 2026-10-25"
date: 2026-10-25
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 8
---

## Weekly Research Digest — 2026-10-25

> 8 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/versacamvla-camera-configurable-vla-policies]] VersaCamVLA: Camera-Configurable VLA Policies for Robotic Manipulation | arXiv (NeurIPS 2026) | Scene-token interface makes a pretrained VLA robust to changes in camera count/pose at deployment — a practical robustness gap, not just another benchmark gain. |
| [[papers/vla/fast-vla-you-only-think-once-robot-manipulation]] Fast-VLA: You Only Think Once for Robot Manipulation | arXiv | Runs the 4B VLM once per episode, then a small actor queries a cached task memory — reported 11–17x amortized inference speedup with ~92–96% success on RoboTwin 2.0/LIBERO. |
| [[papers/vla/vlms-are-native-action-models-explicit-action-space-grounding]] VLMs are Native Action Models: Unleashing the Manipulation Capabilities of VLMs with Explicit Action-Space Grounding | arXiv | Argues pretrained VLMs can act as manipulation policies natively, with no learned action head, via wrist-camera-grounded text actions. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/supermimic-scaling-humanoid-whole-body-control-differentiable-world-model]] SuperMimic: Scaling Humanoid Whole-Body Control with One Differentiable World Model | arXiv | Reports >1000x GPU-hour reduction for humanoid motion tracking by jointly training a differentiable world model with the policy instead of model-free RL. |
| [[papers/world-models/bejepa-goal-conditioned-humanoid-behavior-world-model]] BeJEPA: A Goal-Conditioned Humanoid Behavior World Model via Unsupervised RL | arXiv | JEPA-latent goal-conditioned world model for humanoid disturbance recovery, validated with real Unitree G1 ground-recovery deployment. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/how-and-how-not-to-use-data-augmentation-vla-post-training]] How (and How Not) to Use Data Augmentation in VLA Post-Training | arXiv (NeurIPS 2026 workshop) | ⭐ HIGH PRIORITY: First systematic study showing critic-only augmentation helps RL-based VLA post-training while actor-input augmentation collapses training — concrete, actionable rule (+7.8/+10.0 pts OOD success on π0.5/GR00T N1.5). |
| [[papers/rl-robotics/balanced-data-diet-exploration-bottleneck-mega-scale-rl-robot-control]] A Balanced Data Diet: Addressing the Exploration Bottleneck in Mega-Scale RL for Robot Control | arXiv | Success-Guided Sampling fixes a scaling bottleneck in million-environment parallel RL, with reported zero-shot sim-to-real transfer on contact-rich assembly. |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/lambda0-scaling-open-world-egocentric-human-data-humanoid-loco-manipulation]] λ₀: Scaling Open-World Egocentric Human Data for Humanoid Loco-Manipulation | arXiv | ⭐ HIGH PRIORITY: 500-hour robot-free human dataset (HumanVerse) with a fraction-varying ablation showing how much open-world human data actually buys on top of fixed robot data, plus reported zero-shot Unitree G1 transfer. |

---
*Generated automatically. All entries verified via web search.*
