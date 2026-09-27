---
title: "Weekly Research Digest — 2026-09-27"
date: 2026-09-27
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 13
---

## Weekly Research Digest — 2026-09-27

> 13 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/robodrop-curating-vla-post-training-data-gradient-compatibility]] RoboDrop: Curating VLA Post-Training Data via Local Gradient Compatibility | arXiv | ⭐ HIGH PRIORITY: gradient-compatibility scoring lifts real-robot post-training success from 35% to 67.5% by filtering noisy demonstrations. |
| [[papers/vla/redflow-redirect-failure-action-level-corrections-flow-matching-vla]] RedFlow: Redirect Failure into Action-Level Corrections for Flow-matching VLA Policy | arXiv | ⭐ HIGH PRIORITY: turns failed rollouts into action-level corrective supervision for offline RL, lifting real-world success 56.7%→74.7%. |
| [[papers/vla/in-context-robot-learning-vlm-agents]] In-Context Robot Learning with VLM Agents | arXiv | Frontier-VLM agentic loop (GPT-Policy) adapts to new tasks at deployment with no gradient updates. |
| [[papers/vla/counteralign-counterfactual-supervision-vla]] CounterAlign: Counterfactual Supervision for Vision-Language-Action Models | arXiv | Manufactures negative supervision from expert-only data via mismatched-instruction relabeling for offline RL. |
| [[papers/vla/predvla-predictive-sensorimotor-modeling-sub-million-parameter]] PredVLA: Predictive Sensorimotor Modeling for Sub-Million-Parameter Robot Manipulation | arXiv | Sub-1M-parameter predictive-coding policy rivals larger baselines on LIBERO, relevant to on-device deployment. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/world-models-embodied-intelligence-plausible-controllable-actionable]] World Models for Embodied Intelligence: From Plausible to Controllable to Actionable | arXiv | Survey proposing a Plausible/Controllable/Actionable capability taxonomy, reframing evaluation away from visual fidelity. |
| [[papers/world-models/world-action-models-robot-learning-control-survey]] World-Action Models for Robot Learning and Control: A Survey | arXiv | Scoping survey disambiguating the fast-proliferating "World-Action Model" literature via a 7-axis taxonomy. |
| [[papers/world-models/motus2-self-evolving-general-world-model-dexterous-manipulation]] Motus2: A Self-Evolving General World Model for Dexterous Manipulation | arXiv / ShengShu | Shared-weight policy/simulator/evaluator loop for dexterous manipulation, reported ~84% success across 5 real-robot tasks. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/learning-to-act-while-waiting-rl-finetuning-inference-latency]] Learning to Act While Waiting: RL Finetuning of Generalist Robot Policies Under Inference Latency | arXiv | ⭐ HIGH PRIORITY: fixes RL fine-tuning failure caused by large-policy inference latency breaking the Markov assumption. |
| [[papers/rl-robotics/graft-grounded-efficient-online-reinforcement-adaptation-fine-grained-manipulation]] GRAFT: Grounded and Efficient Online Reinforcement Adaptation for Fine-Grained Robot Manipulation | arXiv | ⭐ HIGH PRIORITY: view-specific visual anchors speed online VLA RL adaptation on precision biomedical manipulation tasks. |
| [[papers/rl-robotics/fierce-generalist-robot-policies-fast-specialists-progress-failure-feedback]] FIERCE: From Generalist Robot Policies to Fast Specialists via Progress-Failure Feedback | arXiv | ⭐ HIGH PRIORITY: RL distills generalist VLAs into fast specialists using a learned progress-failure evaluator instead of dense hand-crafted rewards. |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/bridge-open-source-humanoid-platform-morphology-control-co-design]] BRIDGE: An Open-Source Humanoid Platform via Morphology-Control Co-Design for Physical AI | arXiv | Fully open-sourced 88cm humanoid with joint morphology-control co-design, a rare accessible research platform. |
| [[papers/humanoid/swingbot-learning-whole-body-brachiation-humanoid-robots]] SwingBot: Learning Whole-Body Brachiation for Humanoid Robots | arXiv | Learns continuous arm-over-arm brachiation on humanoid hardware via biomimetic-keyframe exploration and privileged-state estimation. |

---
*Generated automatically. All entries verified via web search.*
