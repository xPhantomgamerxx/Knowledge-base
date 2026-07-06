---
title: "Weekly Research Digest — 2026-07-06"
date: 2026-07-06
topics: [VLA, WorldModels, RL-Robotics]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 17
---

## Weekly Research Digest — 2026-07-06

> 17 new entries this week across 3 topic areas (includes July 2026 papers plus belated additions from April–June not previously logged).

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/neuro-symbolic-safety-guidance-vla-constrained-flow-matching]] Neuro-Symbolic Safety Guidance for VLA via Constrained Flow Matching | arXiv 2607.01378 | First trajectory-level safety framework for flow-matching VLAs; predictive collision avoidance |
| [[papers/vla/learning-action-priors-cross-embodiment-robot-manipulation]] Learning Action Priors for Cross-embodiment Robot Manipulation | arXiv 2606.26095 | Two-stage motion prior pretraining before VLA alignment improves cross-embodiment generalization |
| [[papers/vla/last-hd-latent-physical-reasoning-scalable-human-data]] LaST-HD: Learning Latent Physical Reasoning from Scalable Human Data | arXiv 2606.23685 | Aligns human-hand and robot demonstrations in shared latent space for scalable dexterous skill learning |
| [[papers/vla/apt-action-expert-pretraining-vla-instruction-generalization]] APT: Action Expert Pretraining Improves VLA Instruction Generalization | arXiv 2606.12366 | Bayesian factorization + pretraining order fix for OOD language generalization in VLAs |
| [[papers/vla/vla-pro-cross-task-procedural-memory-transfer]] VLA-Pro: Cross-Task Procedural Memory Transfer | arXiv 2605.29562 | Runtime LoRA adapter retrieval from procedural memory bank for cross-task VLA generalization |
| [[papers/vla/intentvla-short-horizon-intent-modeling-aliased-robot-manipulation]] IntentVLA: Short-Horizon Intent Modeling for Aliased Manipulation | arXiv 2605.14712 | Solves observation aliasing with history-conditioned intent representations + new AliasBench |
| [[papers/vla/loopvla-recurrent-refinement-vla-models]] LoopVLA: Recurrent Refinement for VLA Models | arXiv 2605.09948 | 45% smaller VLA model via looped Transformer; 1.7× faster inference |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/abot-m05-unified-mobility-manipulation-world-action-model]] ABot-M0.5: Unified Mobility-and-Manipulation WAM | arXiv 2607.00678 | First WAM designed for combined navigation+arm control; addresses 3 structural mismatches in prior WAMs |
| [[papers/world-models/roboworld-neural-simulators-generalist-robot-policy-evaluation]] RoboWorld: Neural Simulators for Robot Policy Evaluation | arXiv 2607.01060 | World models as scalable policy evaluation tools without physical robot access |
| [[papers/world-models/worldsample-closed-loop-real-robot-rl-world-modelling]] WorldSample: Closed-loop Real-robot RL with World Modelling | arXiv 2607.02431 | Real-robot rollouts ground world model generation, reducing hallucination for RL augmentation |
| [[papers/world-models/orca-world-foundation-model-multimodal-world-signals]] Orca: The World is in Your Mind | ECCV 2026 / arXiv 2606.30534 | General world foundation model (BAAI) trained on 125K hours of video; unified Next-State-Prediction |
| [[papers/world-models/himem-wam-hierarchical-memory-gated-world-action-models]] HiMem-WAM: Hierarchical Memory-Gated WAM | arXiv 2606.10363 | Boundary-triggered memory gates at skill transitions enable robust long-horizon manipulation |
| [[papers/world-models/echo-memory-controlled-study-memory-action-world-models]] Echo-Memory: Controlled Study of Memory in Action World Models | arXiv 2606.09803 | First controlled ablation of memory design choices in world action models |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/one-demonstration-enough-real-world-robotic-rl]] One Demonstration Is Enough for Real-World Robotic RL | arXiv 2607.01651 | AutoSERL: single demo matches 20-demo SERL baseline with automated interventions |
| [[papers/rl-robotics/aspire-agentic-skills-discovery-robotics]] ASPIRE: Agentic Skills Discovery for Robotics | arXiv 2607.00272 | NVIDIA-led system; 77% LIBERO-Pro gain, 31% zero-shot long-horizon vs. 4% prior |
| [[papers/rl-robotics/rho-coding-agent-roboticist-neurosymbolic-policies]] RHO: Your Coding Agent is Secretly a Roboticist | arXiv 2606.16458 | Coding agents discover neurosymbolic robot policies via reward-based RL; new SOTA on Robosuite |
| [[papers/rl-robotics/last-r1-reinforcing-manipulation-adaptive-physical-latent-reasoning]] LaST-R1: Reinforcing Manipulation via Adaptive Physical Latent Reasoning | arXiv 2604.28192 | LAPO jointly optimizes latent CoT reasoning + action generation; 99.9% LIBERO success rate |

---
*Generated automatically. All entries verified via web search.*
