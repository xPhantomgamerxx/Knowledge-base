---
title: "Weekly Research Digest — 2026-09-06"
date: 2026-09-06
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 22
---

## Weekly Research Digest — 2026-09-06

> 22 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/zeta-controlled-study-zero-shot-cross-embodiment-vla-transfer]] ZETA: A Controlled Study of Zero-Shot Cross-Embodiment VLA Transfer for Tabletop Manipulation | arXiv | Rigorous ablation isolating which design factors actually drive cross-embodiment VLA transfer, with a new 14-embodiment sim+real benchmark. |
| [[papers/vla/lavla-latent-cluster-analysis-vision-language-action-models]] Latent Cluster Analysis for Vision-Language-Action Models | arXiv | Rare mechanistic interpretability probe of a production-scale VLA's (GR00T N1.5) action decoder. |
| [[papers/vla/toward-unified-robot-learning-representation-vla-world-models]] Toward Unified Robot Learning: Bridging Representation, Vision-Language-Action, and World Models | arXiv | Position/survey proposing a 3-axis framework unifying representation learning, VLA, and world models, which currently develop in isolation. |
| [[papers/vla/robotok-internet-scale-data-engine-human-demonstration-retrieval]] RoboTok: An Internet-Scale Data Engine for Human Demonstration Retrieval and Dexterous Manipulation Learning | arXiv | ⭐ HIGH PRIORITY: Actor-centered latent motion space retrieves matching manipulation demos from web-scale video, treating the internet as continually-growing supervision. |
| [[papers/vla/xr-2-scaling-bimanual-household-manipulation-1500-hours]] Scaling Bimanual Household Manipulation from 1,500 Hours of Demonstrations to On-Policy Corrections | arXiv | ⭐ HIGH PRIORITY: Clean scaling study isolating demo-volume vs. DAgger on-policy correction gains (58%→93%) for a 5B-parameter VLA (XR-2). |
| [[papers/vla/driving-vla-zero-shot-transfer-across-embodiments]] Towards Zero-Shot Transfer Across Embodiments For Driving VLAs | arXiv | Shows naive multi-dataset pooling doesn't guarantee driving-VLA generalization; introduces BEV-Forcing to distill geometric priors into the backbone. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/world-labs-atlas-omni-world-model-spatial-intelligence]] Atlas: An Omni World Model for Spatial Intelligence | blog | Well-funded industry world model pitched for robotics real-to-sim (photo→sim-ready RGB-D); benchmark claims are self-reported, no paper or API yet. |
| [[papers/world-models/wm-loco-world-model-augmented-visual-locomotion-humanoids-foothold-constrained-terrain]] World-Model-Augmented Visual Locomotion for Humanoids on Foothold-Constrained Terrain | arXiv | Rare world-model application to legged locomotion (not manipulation), validated on real Unitree G1 over stepping-stones, gaps, and stairs. |
| [[papers/world-models/modeling-what-changes-sparse-residual-world-models-object-centric-manipulation]] Modeling What Changes: Sparse, Residual World Models for Object-Centric Manipulation | arXiv | Counter-trend efficiency paper (change-gate + residual delta) against the dominant "bigger video-diffusion backbone" trend; MuJoCo-only, early-stage. |
| [[papers/world-models/veriphy-agentic-physical-reasoning-world-model-evaluation-refinement]] VeriPhy: Agentic Physical Reasoning for World Model Evaluation and Refinement | arXiv | Auditable, provenance-carrying agentic evaluator for physical plausibility of generated video/world-model output — a runnable system, not just another benchmark. |
| [[papers/world-models/wise-world-model-guided-imagination-scheduling-vla-post-training]] WISE: World-model-guided Imagination Scheduling for Efficient Post-training of VLA Models | arXiv | ⭐ HIGH PRIORITY: Schedules/bounds world-model imagination horizons during VLA post-training to curb compounding rollout error. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/rl-bootstrapping-openvla-oft-novel-robot-embodiment]] RL-Only Bootstrapping of OpenVLA-OFT for a Novel Cable-Driven Robot Embodiment | arXiv | ⭐ HIGH PRIORITY: Zero-demo RL (PPO→GRPO) transfer of a generalist VLA to a non-standard cable-driven robot, no teleop data needed. |
| [[papers/rl-robotics/efficient-real-world-online-rl-centralized-training-critic-decomposition]] Efficient Real-World Online RL for Robot Manipulation via Centralized Training and Critic Decomposition | arXiv | CTDE + task/grasp critic decomposition scales real-world human-in-the-loop RL across multiple physical robot actors. |
| [[papers/rl-robotics/facet-0-robotic-foundation-model-contact-rich-precise-manipulation]] Facet-0: A Robotic Foundation Model for Contact-Rich Precise Manipulation | arXiv | ⭐ HIGH PRIORITY: Joint action–wrench flow matching + RL post-training for sub-millimeter assembly (82% success, 0.5mm, 50ms), new ManuFacet-1K dataset. |
| [[papers/rl-robotics/robo-valuerl-reliable-value-estimation-offline-to-online-rl]] Robo-ValueRL: Reliable Value Estimation for Offline-to-Online Reinforcement Learning | arXiv | Open-source framework diagnosing value-estimate reliability for offline-to-online RL on humanoid industrial manipulation. |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/haf-adapting-generalist-vlas-humanoid-whole-body-loco-manipulation]] HAF: Adapting Generalist VLAs to Humanoid Whole-Body Loco-manipulation via Hierarchical Action Flow and Spectral Latent RL | arXiv | ⭐ HIGH PRIORITY: Staged action-denoising + latent RL post-training adapts generalist VLAs to full humanoid whole-body control without touching the backbone; real-time (~0.12s/step) on real hardware. |
| [[papers/humanoid/fetchman-visual-humanoid-loco-manipulation-simulated-experiences]] FetchMan: Learning Visual Humanoid Loco-Manipulation Policies from Simulated Experiences | arXiv | ⭐ HIGH PRIORITY: Flow-GRPO (online RL for flow-matching policies) breaks through the plateau where BC-from-sim alone stalls; 73.3% zero-shot sim-to-real on Unitree G1. |
| [[papers/humanoid/adapt-agile-diffusion-action-priors-text-driven-humanoid-control]] ADAPT: Agile Diffusion Action Priors for Robust and Steerable Online Text-Driven Humanoid Control | arXiv | ETH Zurich; collapses text-to-motion + tracking into one closed-loop diffusion action-prior + residual-RL controller for online, command-switching humanoid control. |
| [[papers/humanoid/agibot-world-2026-theme-3-reinforcement-learning-dataset]] AgiBot World 2026 — Theme 3: Reinforcement Learning Dataset | blog | New real-world (not sim) RL-oriented dataset theme (9,638 trajectories/164h, contact-rich tasks), signaling a shift toward RL-post-training data. |
| [[papers/humanoid/coordex-coordinating-body-hand-priors-dexterous-loco-manipulation]] CoorDex: Coordinating Body and Hand Priors for Continuous Dexterous Humanoid Loco-Manipulation | arXiv | Sustains dexterous finger-level manipulation through continuous locomotion on real Unitree G1 + WUJI hand, avoiding the common "stop-to-manipulate" limitation. |
| [[papers/humanoid/handoff-humanoid-agentic-task-space-whole-body-control-distilled-teachers]] HANDOFF: Humanoid Agentic Task-Space Whole-Body Control via Distilled Complementary Teachers | arXiv | Compact 10-D task-space interface + mixture-of-experts distillation addresses the planner-to-controller interface gap for agentic humanoid stacks. |
| [[papers/humanoid/data-standards-humanoid-robotics-missing-infrastructure]] Data Standards for Humanoid Robotics: The Missing Infrastructure for Physical AI | position paper | Tied to a real ISO effort (ISO/WD 26264-1); argues the field's bottleneck is non-cumulative/non-interoperable data, not raw scarcity. |

---
*Generated automatically. All entries verified via web search.*
