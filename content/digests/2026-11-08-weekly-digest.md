---
title: "Weekly Research Digest — 2026-11-08"
date: 2026-11-08
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 7
---

## Weekly Research Digest — 2026-11-08

> 7 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/from-pixels-to-actions-native-vision-language-action-policies]] From Pixels to Actions: Towards Native Vision-Language-Action Policies (NEO-VLA) | arXiv | Encoder-free VLA tokenizing pixels directly into the backbone reports beating frozen VLM-encoder baselines (90.9% vs. 79.5%/84.5% on LIBERO) — a direct challenge to the "bolt an action head onto a VLM" default recipe. |
| [[papers/vla/contextflow-in-context-flow-matching-robot-manipulation]] ContextFlow: In-Context Flow Matching for Robot Manipulation | ECCV 2026 | ⭐ HIGH PRIORITY: In-context imitation learning with a continuous flow-matching action head beats ICRT by 35pp on unseen LIBERO configs and reportedly matches fine-tuned π0 with zero fine-tuning. |
| [[papers/vla/simpleicl-in-context-robot-learning-made-simple]] In-Context Robot Learning Made Simple: A Democratized Recipe for Manipulation Tasks (SimpleICL) | arXiv | ⭐ HIGH PRIORITY: Proposes an explicit problem definition for robot in-context learning plus a minimalist, low-cost recipe — useful framing contribution, but benchmark evidence is currently thin. |
| [[papers/vla/simvla-zero-shot-sim-to-real-mobile-manipulation]] SimVLA: Zero-Shot Sim-to-Real VLA Learning for Mobile Manipulation | arXiv | ⭐ HIGH PRIORITY: VLA trained entirely on synthetic data (zero teleoperation) reportedly outperforms a 50-real-demo baseline on real mobile-manipulation tasks. |
| [[papers/vla/huro-robotizing-human-videos-scalable-vla-pretraining]] HuRo: Robotizing Human Videos for Scalable VLA Pretraining | arXiv (CoRL 2026, reported) | ⭐ HIGH PRIORITY: Open-sourced pipeline converts ~630K human-video episodes into robot-aligned training data, reporting OOD completion rising from 34.9% to 72.2% with its pretraining added. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/think-like-world-model-act-like-vla]] Think Like a World Model, Act Like a VLA: Distilling World-Model Representations into Compact Robot Policies | arXiv | Distills a frozen world model's cached features into a compact VLA via feature alignment, avoiding the inference-time cost of running a world model jointly with the policy. |
| [[papers/world-models/dyna-2-world-action-model-human-video-scaling-law]] DYNA-2: A World-Action Model Pre-Trained on 1 Million Hours of Human Video | company technical report | ⭐ HIGH PRIORITY: Dyna Robotics claims a human-to-robot scaling law from pure human-video pretraining (no robot data) and 1.55x production pass-rate gains over DYNA-1 — notable but entirely self-reported, no peer review or independent reproduction. |

### Reinforcement Learning for Robotics

No new notable releases this week. Extensive searching (post-training RL, test-time adaptation, preference optimization, human-in-the-loop DAgger-style correction, online/residual RL, reward modeling) surfaced only items already logged in this vault (e.g. FlowDAgger, FlowPRO, Learning-while-Deploying, DexVerse, Large Reward Models, PARTS) or outside the ~3-month window.

### Humanoid Robotics

No new notable releases this week. Candidates found (Boston Dynamics CEO change, Agility Robotics/AGCO commercial deal, RLWRLD's CoRL 2026 acceptances, ViLoMan) were either non-technical business news or already logged in this vault under earlier dates.

---
*Generated automatically. All entries verified via web search.*
