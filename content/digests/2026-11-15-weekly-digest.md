---
title: "Weekly Research Digest — 2026-11-15"
date: 2026-11-15
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 13
---

## Weekly Research Digest — 2026-11-15

> 13 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/gemini-robotics-2-5-accelerates-real-world-physical-intelligence]] Gemini Robotics 2.5: Accelerating Real-World Physical Intelligence | blog (Google DeepMind) | DeepMind's newest flagship VLA piloted on an Apptronik Apollo 2 humanoid at a Mercedes-Benz factory (96% reported success), paired with a new open jailbreak-resistance safety benchmark. |
| [[papers/vla/sla-scaling-spatial-language-action-model-continual-pretraining]] SLA: Scaling Spatial-Language-Action Model via Continual Pre-training | arXiv | Injects 3D-aligned spatial supervision into continual pretraining on top of π0.5 (architecture unchanged), reporting +24pp real-world success over the baseline. |
| [[papers/vla/oopsierecover-learning-transferable-vla-corrections-semantic-interventions]] OopsieRecover: Learning Transferable VLA Corrections from Semantic Interventions | arXiv | ⭐ HIGH PRIORITY: Fixes VLA failure modes from a handful of human corrective demonstrations via abduction, generalizing to novel scene variations without per-scene DAgger-style recollection (84% vs 28% success vs. HG-DAgger). |
| [[papers/vla/t2mem-learning-test-time-memory-for-robotics]] T²Mem: Learning Test-Time Memory for Robotics | arXiv | ⭐ HIGH PRIORITY: Test-time-training memory module compresses observation history into "fast weights" for long-horizon, partially-observable manipulation, validated with a sharp counterfactual-memory ablation (300/300 vs. 1/300 success). |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/robojepa-scaling-robotic-latent-world-models]] RoboJEPA: Scaling Robotic Latent World Models | arXiv | Meta FAIR's 8B-parameter JEPA latent world model, trained on 15k hours across 12 embodiments, establishes a compute scaling law for imagination error in robotic world models. |
| [[papers/world-models/hydra-0-action-flow-generalist-world-modeling-control]] Hydra-0: Action Flow for Generalist World Modeling and Control | arXiv (NeurIPS 2026) | Represents actions as pixel-plane motion flow to unify human/UMI/robot embodiments, with both forward (evaluation) and inverse (human-to-robot transfer) modes, focused on deformable-object manipulation. |
| [[papers/world-models/ropedia-w0-scaling-loco-manipulation-world-models-across-embodiments]] Ropedia W0: Scaling Loco-Manipulation World Models across Embodiments with Human Experience | arXiv | First egocentric human+robot world foundation model targeting combined locomotion-and-manipulation, trained on a new ~13k-hour corpus with real-time distilled rollouts. |
| [[papers/world-models/genie-4-deepmind-real-time-world-model-robotics]] Genie 4: A Real-Time World Model with Early Robotics Integration | blog (Google DeepMind) | Real-time interactive world model with native audio, paired experimentally with Gemini Robotics for an Apptronik Apollo humanoid rehearsal demo — a notable industry trend signal, though the robotics angle is demo-stage and unverified rather than a benchmarked contribution. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/reinforcement-learning-enables-scaling-generalist-robot-policy-improvement]] Reinforcement Learning Enables Scaling Generalist Robot Policy Improvement | arXiv | ⭐ HIGH PRIORITY: Controlled scaling study showing critic-guided RL policy extraction, not filtered SFT, is what lets online RL post-training of generalist robot policies generalize to unseen objects and scenes. |
| [[papers/rl-robotics/latent-rl-priors-data-efficient-dexterous-manipulation]] Latent RL Priors for Data-Efficient Dexterous Manipulation | arXiv | Freezing a sim-RL-distilled flow-matching action decoder and adapting only a lightweight visual front-end beats fine-tuned π0.5/GR00T N1.7 with 5-10x fewer demos in low-data dexterous/bimanual manipulation (sim-only results so far). |
| [[papers/rl-robotics/agenticroborl-coding-agent-post-training-agentic-robotics]] AgenticRoboRL: Bringing Coding-Agent Post-Training to Agentic Robotics | arXiv | ⭐ HIGH PRIORITY: Applies SFT-then-multi-turn-RL post-training to robot planners that invoke VLA skills, lifting LIBERO-PRO planner success from 18.1% to 71.0% via reusable harness adapters (simulation only). |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/halo-apple-perceptive-humanoid-motion-from-simulation]] HALO: Perceptive Humanoid Motion from Simulation | arXiv | ⭐ HIGH PRIORITY: Apple's humanoid system shows whole-body skill transfer scales with simulated environment diversity (1000 vs. 10 vs. 1 homes), not just data volume, reaching 91% zero-shot real-world success across 6 unseen environments on a Unitree G1. |
| [[papers/humanoid/terrain-indexed-motion-priors-geometric-support-extreme-humanoid-parkour]] Terrain-Indexed Motion Priors and Geometric Support for Extreme Humanoid Parkour | arXiv | Noetix's terrain-conditioned (rather than rigidly-tracked) motion priors enable zero-shot sim-to-real extreme parkour on the Noetix E1 humanoid (29/30 discrete obstacles, 4/5 continuous courses). |

---
*Generated automatically. All entries verified via web search.*
