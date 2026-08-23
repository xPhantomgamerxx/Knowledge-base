---
title: "Weekly Research Digest — 2026-08-23"
date: 2026-08-23
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 29
---

## Weekly Research Digest — 2026-08-23

> 29 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/eximo-vlm-guided-exploration-vla-policies]] EXIMO: VLM Guided Exploration of VLA Policies | arXiv | ⭐ HIGH PRIORITY: VLM-planned autonomous exploration replaces teleoperated data collection for VLA post-training |
| [[papers/vla/tau0-vla-hierarchical-robot-foundation-model-test-time-computation]] τ0-VLA: a Hierarchical Robot Foundation Model with World-Model-Guided Test-Time Computation | arXiv | ⭐ HIGH PRIORITY: confidence-gated world-model search allocates extra test-time compute only where needed |
| [[papers/vla/stellavla-in-context-structured-demonstration-generalizable-vla]] StellaVLA: In-Context Structured Demonstration for Generalizable VLA | arXiv | ⭐ HIGH PRIORITY: annotation-free in-context conditioning tops the VLA-Arena leaderboard, no fine-tuning needed |
| [[papers/vla/imagining-recovery-inference-time-counterfactual-realignment-vla]] Imagining Recovery: Inference-Time Counterfactual Realignment for VLA | arXiv | ⭐ HIGH PRIORITY: training-free recovery from goal/scene disruptions via imagined counterfactual continuation |
| [[papers/vla/reflex-fast-predictive-vla-reaction-critical-manipulation]] Reflex: Enabling Fast and Predictive VLA Models for Reaction-Critical Manipulation | arXiv | New latency-aware benchmark (ReflexBench) + efficient policy for dynamic manipulation, 65ms deployment latency |
| [[papers/vla/foca-future-oriented-conditioning-data-efficient-vla-adaptation]] FOCA: Future-Oriented Conditioning for Data-Efficient VLA Adaptation | arXiv / ICML 2026 | ⭐ HIGH PRIORITY: new SOTA few-shot adaptation, 95.7% success on LIBERO with only 20 demos |
| [[papers/vla/bridging-morphology-gap-intent-conditioned-fine-tuning-dexterous-vla]] Bridging the Morphology Gap: Intent-Conditioned Fine-Tuning for Dexterous VLA | arXiv | ⭐ HIGH PRIORITY: data-efficient fine-tuning recipe for moving low-DoF-pretrained VLAs onto dexterous hands |
| [[papers/vla/gen-15-embodied-foundation-models-one-shot-learners]] GEN-1.5: Embodied Foundation Models are One-Shot Learners | blog | ⭐ HIGH PRIORITY: Generalist AI claims emergent one-shot task learning from a single demonstration, no fine-tuning (unverified beyond blog claims) |
| [[papers/vla/hidden-in-plain-sight-diffusion-based-unrestricted-attacks-vla]] Hidden in Plain Sight: Diffusion-Based Unrestricted Robotic Attacks on VLA Models | arXiv | Adversarial-robustness paper using diffusion-generated (rather than norm-bounded) perturbations against VLA policies |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/egowam-world-action-models-beyond-pixels-egocentric-human-data]] EgoWAM: World Action Models Beyond Pixels with In-the-Wild Egocentric Human Data | arXiv | ⭐ HIGH PRIORITY: controlled study finds DINO/3D-flow targets beat raw pixel prediction by up to 4x OOD for human-video-to-robot transfer |
| [[papers/world-models/r2rdreamer-3d-aware-data-augmentation-spatially-generalized-manipulation]] R2RDreamer: 3D-aware Data Augmentation for Spatially-generalized 2D Manipulation Policies | arXiv | ⭐ HIGH PRIORITY: real-to-real 3D demonstration editing + video completion for spatial generalization |
| [[papers/world-models/halo-wa-hybrid-attention-latent-guided-online-rl-world-action-models]] HALO-WA: Hybrid-Attention Latent-Guided Online RL for World-Action Models | arXiv | ⭐ HIGH PRIORITY: online RL adapter reading WAM internals raises precision-manipulation success from 26.4% to 87% |
| [[papers/world-models/wh0-generative-world-models-scalable-egocentric-hand-manipulation-data]] Wh0: Generative World Models as Scalable Sources of Egocentric Human Hand Manipulation Data | arXiv | ⭐ HIGH PRIORITY: world model as synthetic-data engine, zero-shot dexterous success 8.3%→38.9% across 18 real tasks |
| [[papers/world-models/wla-0-world-language-action-model-unified-world-modeling]] World-Language-Action Model (WLA-0) | arXiv | Autoregressive-Transformer alternative to the now-dominant diffusion-Transformer WAM architecture |
| [[papers/world-models/paiworld-3d-consistent-world-foundation-model-manipulation]] PAIWorld: A 3D-Consistent World Foundation Model for Robotic Manipulation | arXiv | Explicit multi-view geometric reasoning fixes cross-view drift/depth inconsistency in multi-camera WAMs |
| [[papers/world-models/physisforcing-physics-reinforced-world-simulator-manipulation]] PhysisForcing: Physics Reinforced World Simulator for Robotic Manipulation | arXiv | Pixel + semantic alignment losses raise closed-loop world-model success 16.0%→24.0% |
| [[papers/world-models/dim-wam-world-action-modeling-diverse-historical-event-memory]] DIM-WAM: World-Action Modeling with Diverse Historical Event Memory | arXiv | Multi-scale memory banks raise RMBench average success from 28.4% to 69.8% on long-horizon tasks |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/temporal-grpo-beyond-trajectory-level-credit-vla-rl]] Temporal GRPO: Beyond Trajectory-Level Credit in VLA RL | arXiv | ⭐ HIGH PRIORITY: step-level credit assignment for GRPO-based VLA RL fine-tuning |
| [[papers/rl-robotics/recovla-vlm-guided-reward-compilation-failure-recovery-vla]] ReCoVLA: VLM-Guided Reward Compilation for Failure Recovery in VLA Policies | arXiv | ⭐ HIGH PRIORITY: frozen-base + residual RL recovery, validated zero-shot on real Fetch hardware |
| [[papers/rl-robotics/score-support-constrained-rl-real-world-policy-improvement]] SCORE: Support-Constrained RL Enables Real-World Policy Improvement without Real-World Experience | arXiv | ⭐ HIGH PRIORITY: flow-steered support-constrained sim RL improves real dexterous manipulation with zero extra real data |
| [[papers/rl-robotics/robot-self-improvement-human-video-dynamics-models]] Robot Self-Improvement via Human-Video Dynamics Models | arXiv | ⭐ HIGH PRIORITY: training-free failure correction via human-video dynamics model, 40%→81% across 7 tasks and multiple backbones |
| [[papers/rl-robotics/regrind-minimalist-retargeting-guided-rl-dexterous-manipulation]] REGRIND: A Minimalist Retargeting-Guided RL Recipe for Dexterous Manipulation | arXiv | Object-centric keypoint retargeting + residual RL for contact-rich tool-use, with sim-to-real transfer analysis |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/toward-certified-functional-safety-industrial-humanoid-robots]] Toward Certified Functional Safety for Industrial Humanoid Robots | arXiv | Identifies the "fail-passive gap": legged humanoids violate standard industrial safety-certification assumptions |
| [[papers/humanoid/whole-body-planning-humanoids-confined-spaces-self-collision-avoidance]] Whole-Body Planning for Humanoids Navigating Confined Spaces | arXiv | Three-stage plan-then-residual-RL pipeline for humanoid navigation through tight, cluttered spaces |
| [[papers/humanoid/humantracker-comprehensive-human-aligned-motion-tracking-benchmark]] HumanTracker: Comprehensive Human-Aligned Motion Tracking Benchmark | arXiv | ~153-hour benchmark + preference-aligned HumanScore metric catches artifacts kinematic-error metrics miss |
| [[papers/humanoid/noitom-hiphi-617-hour-high-precision-human-motion-dataset]] Noitom Robotics Releases HiPHI: 617-Hour High-Precision Human Motion Dataset | blog | Large public studio-precision mocap + interaction dataset for humanoid imitation learning |
| [[papers/humanoid/adapt-humanoid-robots-professional-style-tennis]] AdaPT: Humanoid Robots Learn Professional-Style Tennis | blog | Style-specific motion imitation from broadcast footage, in-the-wild serving on Unitree G1 / Dobot Atom |
| [[papers/humanoid/unitree-superman-humanoid-record-jump-sprint-speed]] Unitree Unveils "Superman" Humanoid with Record Jump and Sprint Speed | blog | Unverified hardware showcase (2m jump, 12.66 m/s sprint) timed with Unitree's Shanghai IPO |
| [[papers/humanoid/agility-robotics-digit-v5]] Agility Robotics Unveils Digit V5 | blog | Fence-free industrial humanoid targeting Dec. 2026 deployment, alongside Agility's $2.5B SPAC listing |

---
*Generated automatically. All entries verified via web search.*
