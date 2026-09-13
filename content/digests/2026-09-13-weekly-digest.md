---
title: "Weekly Research Digest — 2026-09-13"
date: 2026-09-13
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 20
---

## Weekly Research Digest — 2026-09-13

> 20 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/v-link-recovering-lost-visual-representations-action-dit]] V-Link: Recovering Lost Visual Representations in Action DiT for Vision-Language-Action Models | arXiv | Recovers geometric/semantic VLM features lost in the handoff to the diffusion action expert, +18-31% on RoboTwin/LIBERO-Plus over GR00T N1.6 |
| [[papers/vla/phr-vla-planning-horizon-reasoning]] PHR-VLA: Planning Horizon Reasoning for Vision-Language-Action Models | arXiv | Auxiliary future-dynamics head gives VLAs look-ahead reasoning with no test-time rollout cost, real-world disassembly success 63%→82% |
| [[papers/vla/atlasvla-persistent-world-ego-state-modeling]] AtlasVLA: Persistent World-Ego State Modeling for Vision-Language-Action Models | arXiv | Dual-memory (4D world state + ego-task-progress) fixes wrist-camera-only VLA forgetting, +17.5% on real-world long-horizon tasks |
| [[papers/vla/lost-in-reconstruction-salt-action-tokenizer-language-alignment]] Lost in Reconstruction: Aligning Action Representations with Language in Vision-Language-Action Models | arXiv | ⭐ HIGH PRIORITY: SALT action tokenizer preserves verb-grounding info lost by reconstruction-only VQ-VAE, 72% vs 31% (FAST) on SimplerEnv |
| [[papers/vla/look-where-it-matters-adaptive-visual-refinement-vla]] Look Where It Matters: Adaptive Visual Refinement for Vision-Language-Action Models | arXiv | Register tokens absorb ViT attention-capacity spillover, restoring clean spatial attention for precise manipulation |
| [[papers/vla/vla-precision-asymmetric-co-bootstrapping-online-rl]] VLA-Precision: Asymmetric Co-Bootstrapping for Efficient Real-World Online RL of Vision-Language-Action Models | CoRL 2026 | ⭐ HIGH PRIORITY: Two-timescale RL post-training combining human-intervention bootstrapping with value calibration for real-world (not sim) VLA precision fine-tuning |
| [[papers/vla/decal-physically-grounded-dexterous-vla-contact-aware-latent-co-imagination]] DeCAL: Towards Physically-Grounded Dexterous Vision-Language-Action Models via Contact-Aware Latent Co-Imagination | EMNLP 2026 | Contact-aware vision-tactile gating and co-imagination for dexterous VLA control under visual occlusion during contact |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/openwam-an-open-modular-exploration-towards-systematic-world-action-model-pretraining]] OpenWAM: An Open, Modular Exploration Towards Systematic World-Action Model Pretraining | arXiv | Open, controlled ablation study and infra stack distilling what actually drives WAM performance, plus a strong open checkpoint |
| [[papers/world-models/worldagen-unified-state-action-prediction-with-test-time-world-model-training]] WorldAgen: Unified State-Action Prediction with Test-Time World Model Training | arXiv | ⭐ HIGH PRIORITY: Uses real exploratory rollouts to test-time-train a world model head, beating static SOTA on CALVIN/LIBERO under deployment shift |
| [[papers/world-models/learning-to-use-imagination-progress-conditioned-future-utilization-for-world-action-models]] Learning to Use Imagination: Progress-Conditioned Future Utilization for World Action Models | arXiv | Introduces execution-progress conditioning so WAMs adaptively trust imagined futures, validated on 5 sim benchmarks + 2 real platforms |
| [[papers/world-models/solarwm-open-data-and-scalable-training-for-long-horizon-video-world-models]] SolarWM: Open Data and Scalable Training for Long-Horizon Video World Models | arXiv | Fully open 1.43M-clip data engine and backbone-native recipe turning Wan2.2/LTX-2.5/MiniMax-H3 into real-time long-horizon world models |
| [[papers/world-models/spatially-aware-world-action-model-via-geometric-latent-diffusion]] Spatially Aware World Action Model via Geometric Latent Diffusion | arXiv | Injects depth as latent frames into a frozen video-diffusion tokenizer to give WAMs 3D awareness without retraining the tokenizer |
| [[papers/world-models/q-learning-with-world-models]] Q-Learning With World Models | arXiv | ⭐ HIGH PRIORITY: Uses a world model only for test-time search over a Q-learning policy's imagined futures, avoiding compounding-bias from training on generated rollouts |
| [[papers/world-models/sg-wam-self-guided-world-modeling-in-geometry-aware-policy-space]] SG-WAM: Self-Guided World Modeling in Geometry-Aware Policy Space | arXiv | EMA self-distilled, pixel-free world modeling inside policy latent space hits 98.5% LIBERO from just a 0.9B model |
| [[papers/world-models/dreamsteer-latent-world-models-can-steer-vla-policies-during-deployment-without-any-finetuning]] DreamSteer: Latent World Models Can Steer VLA Policies During Deployment Without Any Finetuning | arXiv | ⭐ HIGH PRIORITY: Zero-finetuning deployment-time re-ranking of frozen-VLA action candidates using a latent world model and value model |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/assembling-two-parts-in-one-hand]] Assembling Two Parts in One Hand | CoRL 2026 / arXiv | RL-trained single-hand (no fixture, no second arm) in-hand assembly with zero-shot sim-to-real transfer, 75-85% real success across 3 object pairs |
| [[papers/rl-robotics/beyond-noise-steering-dual-latent-space-reinforcement-learning-for-generative-robot-policy]] Beyond Noise Steering: Dual-Latent Space Reinforcement Learning for Generative Robot Policy | arXiv | ⭐ HIGH PRIORITY: Extends DSRL-style latent-space RL post-training of frozen generative/diffusion policies with a second representation-modulation latent |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/ihmc-fast-resilient-adaptable-loco-manipulation-behaviors]] A System for Fast, Resilient, and Adaptable Loco-Manipulation Behaviors on Humanoid Robots | arXiv | IHMC's decade-long runtime-editable behavior-authoring system validated on Atlas, Nadia, and Unitree H1-2 |
| [[papers/humanoid/humanoid-safe-stop-learned-stoppability-value]] Humanoid Safe Stop via Learned Stoppability Value | arXiv | Learned and Hamilton-Jacobi-reachability-grounded estimators let a humanoid know in advance whether an e-stop is actually feasible |
| [[papers/humanoid/robotacdex-dexterous-visual-tactile-action-dataset-humanoid-manipulation]] RoboTacDex: A Dexterous Visual-Tactile-Action Dataset for Humanoid Manipulation | arXiv | Adds synchronized tactile feedback to a 6k-trajectory bimanual dexterous-manipulation dataset on the open Unitree G1 platform |

---
*Generated automatically. All entries verified via web search.*
