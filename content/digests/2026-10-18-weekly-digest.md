---
title: "Weekly Research Digest — 2026-10-18"
date: 2026-10-18
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 24
---

## Weekly Research Digest — 2026-10-18

> 24 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/splat2act-captured-scenes-personalized-vla-manipulation]] Splat2Act: From Captured Scenes to Personalized VLA Manipulation | arXiv | ⭐ HIGH PRIORITY: Real2sim2real pipeline personalizes π0.5 to a specific home via Gaussian-Splat twin + synthetic demos, taking pickup success from 0% to 62.5%. |
| [[papers/vla/ogpo-offline-goal-conditioned-policy-optimization-recoverable-vla]] OGPO: Offline Goal-conditioned Policy Optimization for Recoverable Vision-Language-Action Models | arXiv / NeurIPS 2026 | ⭐ HIGH PRIORITY: Offline RL post-training that relabels demos with key-states and process rewards so VLAs learn to recover off-distribution, no online interaction needed. |
| [[papers/vla/rara-retrieval-anchored-representation-alignment-vla]] RARA: Robust Policy Fine-Tuning via Retrieval-Anchored Representation Alignment | arXiv | ⭐ HIGH PRIORITY: Anchors VLA representations to retrieved reference examples during fine-tuning to curb robustness loss from task-specific SFT. |
| [[papers/vla/human-demonstrations-post-training-data-any-robot-body]] Human Demonstrations as Post-Training Data for Any Robot Body: Retargeting the Object, Not the Hand | arXiv | ⭐ HIGH PRIORITY: Retargets the manipulated object's trajectory instead of the hand, making one human demo reusable as post-training data across embodiments. |
| [[papers/vla/graph-reweighted-behavior-cloning-human-interventions-manipulation]] Graph-Reweighted Behavior Cloning with Human Interventions for Precise Robotic Manipulation | arXiv | ⭐ HIGH PRIORITY: Graph-based reweighting of DAgger-style human corrections for precise, intervention-informed behavior cloning. |
| [[papers/vla/one-shot-human-video-guided-adaptation-vla]] One-shot Human Video-Guided Adaptation for Vision-Language-Action Models | arXiv | ⭐ HIGH PRIORITY: Adapts a pretrained VLA to a new task from a single human (not robot) demonstration video, no gradient updates at test time. |
| [[papers/vla/noise-space-learning-vla-adaptation]] Noise Space Learning for VLA Adaptation | arXiv | ⭐ HIGH PRIORITY: Adapts a frozen flow-matching VLA by learning in its noise space rather than weight or action space — cheap, low-risk correction. |
| [[papers/vla/what-matters-quality-aware-vla-pretraining-benchmark]] What Matters in Quality-Aware VLA Pretraining: A Benchmark and Empirical Study | arXiv | ⭐ HIGH PRIORITY: AXIS-Bench + empirical study of weighting/filtering/conditioning strategies for suboptimal demos; sim pretraining lifts real success 9.6%→31.7%. |
| [[papers/vla/core-vla-scalable-robust-conditional-routing-experts]] CoRE-VLA: Towards Scalable and Robust Vision-Language-Action Modeling via Conditional Routing of Experts | arXiv | Mixture-of-experts VLA gated by sensor availability and task intent, degrading gracefully when a modality (e.g. depth) drops out. |
| [[papers/vla/libero-rig-hardware-setup-robustness-benchmark-vla]] LIBERO-RIG: A Hardware-Setup Robustness Benchmark for Vision-Language-Action Models | arXiv | 210-condition sweep of camera/calibration/controller-rate/gripper perturbations; visual-augmentation training doesn't fix hardware-setup robustness gaps. |
| [[papers/vla/forkcast-predictive-recovery-vla-counterfactual-futures]] ForkCast: Predictive Recovery for Vision-Language-Action Policies via Counterfactual Futures | arXiv | Branches multiple counterfactual predicted futures at inference time and selects the one most likely to recover from a failure. |
| [[papers/vla/jittervla-replay-benchmark-motion-smoothness]] JitterVLA: A Replay Benchmark for Motion Smoothness in VLA-Driven Human-Robot Manipulation | arXiv | New replay-based metric for motion jitter/smoothness in VLA execution, pushing evaluation beyond binary task success. |
| [[papers/vla/wave-0-bridging-vla-policies-wams-latent-future-prediction]] WAVE-0: Bridging VLA Policies and WAMs with Lightweight Latent Future Prediction | arXiv | Lightweight latent bridge connecting VLA policies to world-action-model predictive signal without full WAM rollout cost. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/greenwam-world-foundation-model-robotics]] GreenWAM: A World Foundation Model for Robotics | arXiv (Sber) | World-action foundation model spanning 20 robot families via a shared joint-coordinate space, built on Cosmos 3 Edge; beats π0.5-adapted policies on a real humanoid. |
| [[papers/world-models/loopwam-closed-loop-generalist-policy-improvement-deployment-rollouts]] LoopWAM: Closed-Loop Generalist Policy Improvement from Deployment Rollouts | arXiv | ⭐ HIGH PRIORITY: Learns from the full quality spectrum of deployment rollouts (not just curated successes); 23.67%→43.33% over three deploy-and-train rounds on RoboChallenge. |
| [[papers/world-models/thinker-wm-unified-world-model-shared-multimodal-representations]] Thinker-WM: A Unified World Model with Shared Multimodal Representations for Embodied Intelligence | arXiv | Single Unified Dynamics Transformer jointly modeling RGB, metric depth, and action from ~31K hours of mixed egocentric/real-robot/sim data. |
| [[papers/world-models/what-matters-world-modeling-vla]] What Matters for World Modeling in Vision-Language-Action Models? | arXiv | Ablation study isolating which design choices in VLA-plus-world-model architectures actually drive downstream gains. |
| [[papers/world-models/glimpse-explorable-video-world-models-spectral-indexing]] GLIMPSE: Explorable Video World Models with Multi-Precision Spectral Indexing | arXiv | Multi-precision spectral indexing for cheaper exploration of video world models' possible futures. |
| [[papers/world-models/smolwam-compact-latent-world-action-model-edge-devices]] SmolWAM: A Compact Latent World-Action Model for Edge Devices | arXiv | Edge-deployable compact world-action model, joining MiniWAM/Efficient-WAM/Flash-WAM in the efficiency-focused WAM sub-area. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/accrue-continual-off-policy-rl-robot-foundation-models]] ACCRUE: Continual Off-Policy Reinforcement Learning for Robot Foundation Models | arXiv (NVIDIA/KAIST) | Inherited actor/critic across sequential tasks cuts real-robot RL training time 31–68.5% on contact-rich assembly, validated on real hardware. |
| [[papers/rl-robotics/dream-to-remember-continual-steering-generalist-policies-world-models]] Dream to Remember: Continual Steering of Generalist Robot Policies with World Models | arXiv | Uses imagined world-model rollouts (rather than stored demos) to retain old skills while adapting a generalist policy to new tasks. |
| [[papers/rl-robotics/beyond-temporal-proximity-explanatory-world-models-credit-assignment]] Beyond Temporal Proximity: Explanatory World Models for Credit Assignment in RL | arXiv | Uses a world model to build explicit causal links between actions and distant effects, addressing a known weak spot of proximity-based credit assignment. |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/viola-generalist-humanoid-control-policies-human-data]] VioLA: Learning Generalist Humanoid Control Policies from Human Data | arXiv | Shared human/robot motion-latent space lets a 93.2%-human-data corpus (140.6M frames) drive a generalist humanoid policy; zero-shot beats GR00T N1.7 (16.7%) and Ψ0 (0%) on locomotion-instruction-following on a real Unitree G1. |
| [[papers/humanoid/what-elevation-map-cannot-see-semantic-locomotion-humanoid]] What the Elevation Map Cannot See: Semantic-Aware Locomotion and Execution-Aware Navigation for Humanoid Robot | arXiv | Adds semantic perception on top of geometric elevation mapping so humanoid locomotion can distinguish traversable-looking but semantically unsafe terrain. |
| [[papers/humanoid/egomatrix-physically-faithful-dexterous-robot-demonstrations-egocentric-video]] EgoMatrix: Physically Faithful Dexterous Robot Demonstrations from Egocentric Human Videos | arXiv | Emphasizes physical feasibility (not just visual plausibility) when converting egocentric human video into dexterous-hand robot demonstrations. |

---
*Generated automatically. All entries verified via web search.*
