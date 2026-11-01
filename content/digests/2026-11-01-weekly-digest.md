---
title: "Weekly Research Digest — 2026-11-01"
date: 2026-11-01
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 9
---

## Weekly Research Digest — 2026-11-01

> 9 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/world-to-wrist-task-conditioned-future-wrist-modeling-fine-grained-manipulation]] World-to-Wrist: Task-Conditioned Future Wrist Modeling for Fine-Grained Robot Manipulation | arXiv | Predicts future wrist-camera latents (not full frames) as a cheap, targeted auxiliary signal for contact-rich manipulation; code released. |
| [[papers/vla/what-makes-an-efficient-vla-action-head-design-scaling-latency]] What Makes an Efficient VLA? Navigating Action-Head Design, Scaling, and Latency | arXiv | Controlled, latency-paired sweep finds action-head initialization from the language backbone dominates decoder architecture or loss choice — a useful correction to the efficient-VLA literature. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/zimablue-evolving-generalizable-world-action-models-scalable-video-pretraining]] ZimaBlue: Evolving Generalizable World Action Models through Scalable Video Pre-training | arXiv | Reports a scaling-law data point: 0→120k+ hours of egocentric video pretraining lifts zero-shot real-robot success from 36.1% to 77.8%. |
| [[papers/world-models/forewam-foresight-without-seeing-latent-futures-world-action-models]] Foresight Without Seeing: Latent Futures for World Action Models (ForeWAM) | arXiv | Skips video generation entirely via single-prefill KV caching, reporting 6.27x latency reduction over Fast-WAM — a direct efficiency rebuttal to video-heavy world-action models. |
| [[papers/world-models/dreamwam-beyond-rgb-future-prediction-world-action-models]] DreamWAM: Beyond RGB Future Prediction for World Action Models | arXiv | Train-time-only motion/geometry/semantics supervision (disabled at inference) reports the largest real-world OOD robustness gain (74.4% vs 55.6%) of this quarter's "what should a WAM predict" cluster. |
| [[papers/world-models/right-future-for-action-action-relevant-predictive-states-wam]] The Right Future for Action: Learning Action-Relevant Predictive States in World Action Models | arXiv | The most rigorous entry in this quarter's "what should a WAM predict" cluster — a controlled teacher ablation (V-JEPA2/DINOv2/VGGT/none) isolating where future-state supervision actually helps and hurts. |
| [[papers/world-models/unitree-unifolm-x2-autonomous-sparring-world-model]] Unitree UnifoLM-X2-1.0: Real-Time World-Model-Driven Autonomous Humanoid Sparring | blog | Claimed real-time world-model-driven adversarial humanoid control demo, but autonomy and "real-time" claims are disputed by independent reporting — treat with caution. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/value-as-memory-online-value-guided-post-training-robot-policies]] Value as Memory (VaM): Online Value-Guided Post-training for General Robot Policies | arXiv | ⭐ HIGH PRIORITY: Staged offline→DAgger→autonomous-rollout post-training pipeline with a value-source ablation disentangling action-policy gains from value-estimate gains; reports ~29–33pt absolute success gains on long-horizon contact-rich tasks. |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/boston-dynamics-atlas-13-dof-four-finger-hand]] Boston Dynamics Unveils New 13-DOF Four-Finger Tactile Hand for Atlas | blog | A major humanoid vendor deliberately drops anthropomorphic 5-finger design for a manipulation- and manufacturability-optimized 4-finger hand with dense tactile sensing — a notable hardware-design statement, though unverified beyond company PR. |

---
*Generated automatically. All entries verified via web search.*
