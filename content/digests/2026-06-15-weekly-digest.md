---
title: "Weekly Research Digest — 2026-06-15"
date: 2026-06-15
topics: [VLA, WorldModels, RL-Robotics]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 11
---

## Weekly Research Digest — 2026-06-15

> 11 new entries this week across 3 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/seetraceact-visibility-aware-latent-planning-cross-embodiment-demos]] SeeTraceAct | arXiv 2606.02745 | Demo-conditioned VLA with visibility-aware end-effector trace prediction; introduces RoboCasa-DC cross-embodiment benchmark; +12.5pp real-world success |
| [[papers/vla/3dthinkvla-latent-3d-priors-vla-co-training]] 3DThinkVLA | arXiv 2606.04436 | Injects latent 3D geometry and reasoning priors into VLAs via co-training + anchor token; fixes prompt-induced reasoning gap without backbone changes |
| [[papers/vla/affordancevla-affordance-aware-vla-action-generation]] AffordanceVLA | arXiv 2606.06155 | Which/Where/How2Act affordance modules + MoT architecture bridge VLM semantics to precise robot control; includes automated affordance data pipeline |
| [[papers/vla/memoryvla-plus-plus-temporal-modeling-memory-imagination-vla]] MemoryVLA++ | arXiv 2606.09827 | Cognitive-science-inspired temporal VLA with working memory, episodic memory, and imagination; +9/26/28% on general/memory/imagination-dependent tasks |
| [[papers/vla/hierarchical-vla-agents-orchestrating-robot-policies]] Hierarchical VLA Agents (Google DeepMind) | arXiv 2606.10267 | First systematic options-framework study of Hi-VLA design; distils practical principles for planner/controller interfaces across short- and long-horizon tasks |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/tau0-wm-unified-video-action-world-model-agibot]] τ₀-WM (AgiBot) | arXiv 2606.01027 | 5B-parameter open robotic foundation model trained on 27.3K hours; unifies policy, video prediction, and action evaluation in one diffusion backbone |
| [[papers/world-models/motionwam-foundation-world-action-model-humanoid-loco-manipulation]] MotionWAM | arXiv 2606.09215 | Real-time (4.9 Hz, 7× faster than Cosmos Policy) unified WAM for humanoid loco-manipulation; removes upper/lower-body split with a single motion latent |
| [[papers/world-models/making-foresight-actionable-agra-representation-alignment-wam]] Making Foresight Actionable (AGRA) | arXiv 2606.12217 | AGRA objective aligns video diffusion features to a semantic encoder to fix the reconstruction-vs-control representation mismatch in WAMs (HKU/XPENG) |
| [[papers/world-models/repwam-world-action-modeling-representation-visual-action-tokenizers]] RepWAM | arXiv 2606.13674 | Replaces reconstruction tokenisers in WAMs with semantically aligned visual-action tokenizers; strong gains across real-world manipulation and simulation |
| [[papers/world-models/targeting-world-models-adversarial-robot-learning-pipelines]] Targeting World Models (Adversarial) | arXiv 2606.09499 | First formal study of data-poisoning attacks through world models in robot learning pipelines; highlights critical supply-chain security gap |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/sarm2-stage-aware-reward-modeling-self-improving-robot-manipulation]] SARM2 + SPIRAL | arXiv 2606.10305 | Multi-task stage-aware reward model (MMoE + action-primitive vocabulary) + SPIRAL self-improvement loop; autonomous real-robot policy improvement without new demos |

---
*Generated automatically. All entries verified via web search.*
