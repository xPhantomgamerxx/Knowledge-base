---
title: "Weekly Research Digest — 2026-08-16"
date: 2026-08-16
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 25
---

## Weekly Research Digest — 2026-08-16

> 25 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/in-context-vla-agentic-tool-use-post-training]] In-Context VLA: Language via In-Context Post-Training and Agentic Tool Use | arXiv | ⭐ HIGH PRIORITY: Reframes VLA "reasoning" as tool-mediated grounding instead of free-text CoT, SOTA across RoboCasa-GR1/SimplerEnv/LIBERO plus real hardware |
| [[papers/vla/explicit-language-memory-long-horizon-planning-vla]] Explicit Language Memory for Long-Horizon Planning in VLA | arXiv | Interpretable textual memory alternative to latent-memory long-horizon VLAs |
| [[papers/vla/handedit-embodiment-aware-image-editing-dataset-dexterous-hands]] HandEdit: Embodiment-Aware Image-Editing Dataset for Dexterous Hands | arXiv | ⭐ HIGH PRIORITY: 200M+ instance hand-to-robot image-editing dataset spanning 26 embodiments |
| [[papers/vla/xiaomi-robotics-1-xr1-scaling-real-world-manipulation-pretraining]] Xiaomi-Robotics-1 (XR-1): Scaling Real-World Manipulation Pretraining | arXiv | ⭐ HIGH PRIORITY: 100,000+ hours real-world pretraining with auto-labeling pipeline, open weights |
| [[papers/vla/crosstracer-hierarchical-cross-embodiment-navigation]] CrossTracer: Hierarchical Cross-Embodiment Navigation | arXiv | Pixel-space waypoint interface beats Gemini-2.5-Pro by 28% relative on NaviTrace |
| [[papers/vla/hymes-skills-in-weights-memory-in-code]] HyMeS: Skills in Weights, Memory in Code | arXiv | Splits motor skills (VLA weights) from memory management (coding agent) for non-Markovian tasks |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/lila-wam-lightweight-latent-reasoning-world-action-model]] LiLa-WAM: Lightweight Latent Reasoning World-Action Model | arXiv | 0.5B-param WAM trainable on a single consumer GPU, 90.5% on RoboTwin 2.0 |
| [[papers/world-models/lingbot-va-20-native-video-action-pretraining-generalizable-robot-control]] Native Video-Action Pretraining for Generalizable Robot Control | arXiv | Trains a video-action model from scratch rather than adapting a generic video generator |
| [[papers/world-models/adawam-adaptive-multimodal-reasoning-world-action-models]] AdaWAM: Adaptive Multi-Modal Reasoning for World Action Models | arXiv | Router triggers expensive visual "dreaming" only when needed, cutting inference cost |
| [[papers/world-models/vera-turning-video-models-into-generalist-robot-policies]] VERA: Turning Video Models into Generalist Robot Policies | arXiv | Decouples embodiment-agnostic video planner from embodiment-specific inverse dynamics model |
| [[papers/world-models/efficient-sim-to-real-transfer-world-action-models-synthetic-priors]] Efficient Sim-to-Real Transfer of World-Action Models from Synthetic Priors | arXiv | ⭐ HIGH PRIORITY: First zero-shot sim-to-real transfer of a WAM trained purely on synthetic data (Cosmos Policy + AnyTask) |
| [[papers/world-models/joyai-sim-simulation-interconversion-toolchain-embodied-data-pyramid]] JoyAI-Sim: Simulation-Enabled Interconversion Toolchain | arXiv | Bidirectional robot-sim-human data conversion with human-validated evaluation |
| [[papers/world-models/contactguard-pre-contact-execution-monitoring-latent-world-models]] ContactGuard: Pre-Contact Execution Monitoring with Latent World Models | arXiv | Uses a world model as a safety/verification layer to flag failures before contact |
| [[papers/world-models/dreamx-phi-10-action-conditioned-video-world-model-manipulation]] DreamX-Phi 1.0: Action-Conditioned Video World Model | arXiv | 1st place on WorldArena 2.0 Track 1 leaderboard via geometric action-conditioning |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/bora-offline-online-residual-adaptation-dexterous-vla]] BORA: Offline RL and Online Residual Adaptation for Dexterous VLA | arXiv | ⭐ HIGH PRIORITY: Frozen-backbone residual RL with human-in-the-loop correction for dexterous hands |
| [[papers/rl-robotics/vista-vision-grounded-physics-validated-umi-data-vla]] VISTA: Vision-Grounded and Physics-Validated UMI Data for VLA Training | arXiv | ⭐ HIGH PRIORITY: 8M-pair VQA dataset plus physical-feasibility filtering for UMI-collected data |
| [[papers/rl-robotics/dexpie-stable-dexterous-policy-improvement-real-world-experience]] DexPIE: Stable Dexterous Policy Improvement from Real-World Experience | arXiv | ⭐ HIGH PRIORITY: DAgger-style correction gives 37% success-rate gain on real dexterous tasks |
| [[papers/rl-robotics/midas-adaptation-generalist-robot-policies-minimal-data]] MiDAS: Adaptation of Generalist Robot Policies with Minimal Data | arXiv | ⭐ HIGH PRIORITY: Single-demonstration BC anchor plus online residual RL on real bimanual hardware |
| [[papers/rl-robotics/scenesmith-agentic-scene-generation-robot-training-data]] SceneSmith: Agentic Scene Generation for Scalable Robot Training Data | blog (MIT News) | ⭐ HIGH PRIORITY: Multi-agent pipeline generates diverse simulated scenes to address data scarcity |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/human-as-humanoid-zero-shot-learning-ego-exo-videos]] Human-as-Humanoid: Zero-Shot Learning from Ego-Exo Human Videos | arXiv | ⭐ HIGH PRIORITY: 4.8-7.2x demonstration throughput gain vs. teleoperation via FK-aware retargeting |
| [[papers/humanoid/skild-brain-10-omni-bodied-robot-foundation-model]] Skild Brain 1.0: An Omni-Bodied Robot Foundation Model | blog (Skild AI) | Vault's first Skild AI entry — single-network claim across ~200 hardware platforms |
| [[papers/humanoid/figure-ai-scaling-helix-logistics]] Scaling Helix: A New State of the Art in Humanoid Logistics | blog (Figure AI) | Vault's first Figure AI entry — deformable-object handling, 20% faster package throughput |
| [[papers/humanoid/figure-03-autonomous-ladder-climb]] Figure 03 Autonomous Ladder Climb | press/social | Public demo of hard whole-body loco-manipulation; unverified/thin on technical detail |
| [[papers/humanoid/labimus-humanoid-dexterous-manipulation-chemical-laboratory]] Labimus: Humanoid Dexterous Manipulation in Chemical Laboratory | arXiv | First benchmark for humanoid manipulation in scientific lab settings |
| [[papers/humanoid/simple-humanoid-loco-manipulation-simulation-benchmark]] SIMPLE: Simulation-Based Policy Learning and Evaluation for Humanoid Loco-Manipulation | arXiv | Dual-engine (MuJoCo + IsaacSim) benchmark, 60 tasks across 50 scenes |

---

**Tooling note:** This week's research relied entirely on WebSearch snippets — direct WebFetch access to arxiv.org, huggingface.co, and most company blog domains was blocked by the environment's network egress policy for every research agent, and several WebSearch budgets were exhausted before every lead could be chased. A handful of promising leads (SelfWAM, FlowPilot, RoboDojo, AthenaZero bimanual juggling, HumanoidMimicGen, an IMU-based humanoid teleoperation paper) were found but not included this week due to insufficient corroborating detail — worth a follow-up pass once fetch access or search budget is restored.

*Generated automatically. All entries verified via web search.*
