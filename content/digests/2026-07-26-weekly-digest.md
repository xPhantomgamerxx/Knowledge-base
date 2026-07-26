---
title: "Weekly Research Digest — 2026-07-26"
date: 2026-07-26
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 22
---

## Weekly Research Digest — 2026-07-26

> 22 new entries this week across 4 topic areas. This week's cross-cutting sweep for VLA post-training / data-augmentation content turned up an unusually large batch — 17 of the 22 new entries are flagged high priority.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/robottt-context-scaling-robot-policies]] RoboTTT: Context Scaling for Robot Policies | arXiv | ⭐ HIGH PRIORITY: Test-time-training "fast weights" scale VLA context to 8K timesteps, enabling one-shot in-context imitation and on-the-fly policy improvement without extra inference latency. |
| [[papers/vla/flowdagger-human-in-the-loop-latent-space-policy-adaptation]] FlowDAgger: Human-in-the-Loop Adaptation of Generative Robot Policies in Latent Space | arXiv | ⭐ HIGH PRIORITY: "Action inversion" lets frozen flow/diffusion policies be DAgger-adapted from a handful of human corrections without full fine-tuning or online RL. |
| [[papers/vla/z1-efficient-rl-vla]] Z-1: Efficient Reinforcement Learning for Vision-Language-Action Models | arXiv | ⭐ HIGH PRIORITY: GRPO-based RL post-training lifts π0.5 from 67.4% to 80.6% success across 24 RoboCasa tasks. |
| [[papers/vla/force-efficient-vla-rl-value-calibrated-warmup]] FORCE: Efficient VLA Reinforcement Fine-Tuning via Value-Calibrated Warm-up and Self-Distillation | arXiv | ⭐ HIGH PRIORITY: A Q-function warm-up phase fixes catastrophic initial unlearning in VLA RL fine-tuning, +79% absolute success over imitation baselines. |
| [[papers/vla/ttt-vla-test-time-latent-prompt-optimization]] TTT-VLA: Test-Time Latent Prompt Optimization for Vision-Language-Action Models | arXiv | ⭐ HIGH PRIORITY: Adapts a learned latent prompt (not model weights) online at deployment to handle distribution shift. |
| [[papers/vla/retrieve-dont-retrain-vla-new-tasks-test-time]] Retrieve, Don't Retrain: Extending Vision Language Action Models to New Tasks at Test Time | arXiv | ⭐ HIGH PRIORITY: A frozen retrieval-augmented policy adds new tasks by indexing demonstrations instead of fine-tuning. |
| [[papers/vla/expo-ft-sample-efficient-rl-finetuning-vla]] EXPO-FT: Sample-Efficient Reinforcement Learning Finetuning for Vision-Language-Action Models | arXiv | ⭐ HIGH PRIORITY: Q-guided candidate selection plus human-in-the-loop corrections make RL fine-tuning of VLAs sample-efficient on precision/dynamic tasks. |
| [[papers/vla/supervise-what-survives-geometry-guided-vla-adaptation-synthetic-video]] Supervise What Survives: Geometry-Guided VLA Adaptation from Synthetic Robot Videos | arXiv | ⭐ HIGH PRIORITY: Uses synthetic robot video only for geometric auxiliary supervision (not pseudo-actions), avoiding the sim-to-real action mismatch of prior approaches. |
| [[papers/vla/rynnbrain-11-embodied-foundation-model]] RynnBrain 1.1: Towards More Capable and Generalizable Embodied Foundation Model | arXiv | Alibaba DAMO's 2B/9B/122B-A10B embodied foundation model family adds contact-point prediction and native 3D grounding, evaluated across three distinct robot embodiments. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/temporal-ratio-video-action-generalization-gap]] Understanding and Mitigating the Video-Action Generalization Gap via Temporal Ratio | arXiv | ⭐ HIGH PRIORITY: Identifies why video-pretrained foundation models lose compositional generalization after being fine-tuned into VLAs, and fixes it with an inference-time guidance metric. |
| [[papers/world-models/world-labs-acquires-scenix]] World Labs Acquires SceniX | blog | ⭐ HIGH PRIORITY: Fei-Fei Li's World Labs acquires a Stanford robotics-sim spinout to fuse generative 3D world models with simulation pipelines for synthetic robot training data. |
| [[papers/world-models/gigaworld-1-world-models-robot-policy-evaluation]] GigaWorld-1: A Roadmap to Build World Models for Robot Policy Evaluation | arXiv | Open-sourced WMBench (324k+ rollouts, 7 world-model families) shows evaluator quality tracks action-faithfulness over long horizons, not photorealism. |
| [[papers/world-models/mu0-scalable-3d-interaction-trace-world-model]] μ0: A Scalable 3D Interaction-Trace World Model | arXiv | Predicts embodiment-agnostic 3D interaction traces instead of pixels or actions, letting it pretrain from action-free video and transfer across embodiments. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/freeform-preference-learning-robotic-manipulation]] Freeform Preference Learning for Robotic Manipulation | arXiv | ⭐ HIGH PRIORITY: Multi-axis natural-language preferences (speed, safety, placement quality) give a denser reward signal than binary preference learning, +38pp over baselines. |
| [[papers/rl-robotics/trust-your-instincts-confidence-driven-test-time-rl-vla]] Trust Your Instincts: Confidence-Driven Test-Time RL for Vision-Language-Action Models | arXiv | ⭐ HIGH PRIORITY: Test-time RL that uses a VLA's own generation confidence as an intrinsic reward, approaching oracle RL performance with no ground-truth reward. |
| [[papers/rl-robotics/leveraging-offline-supervision-rl-large-scale-vla]] Leveraging Offline Supervision for Efficient and Generalizable Reinforcement Learning in Large-Scale Vision-Language-Action Models | arXiv | ⭐ HIGH PRIORITY: Hybrid offline-online RL training retains RL's OOD generalization advantage while cutting the costly online interaction needed to get there. |
| [[papers/rl-robotics/sarl-semantic-reinforcement-learning-generalist-robot-policies]] Adapting Generalist Robot Policies with Semantic Reinforcement Learning (SARL) | arXiv | ⭐ HIGH PRIORITY: Adapts generalist VLAs by running RL over language prompts instead of raw actions, composing existing skills for novel long-horizon OOD tasks. |
| [[papers/rl-robotics/enpire-agentic-robot-policy-self-improvement-real-world]] ENPIRE: Agentic Robot Policy Self-Improvement in the Real World | arXiv | ⭐ HIGH PRIORITY: AI coding agents run the full policy-improvement loop on a real robot fleet, hitting 99% success on dexterous tasks and halving training time from 1→8 robots. |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/legs-teleop-free-vla-humanoid-gaussian-splatting-world]] LEGS: Fine-Tuning Teleop-Free VLAs for Humanoid Loco-manipulation in an Embodied Gaussian Splatting World | arXiv | ⭐ HIGH PRIORITY: Gaussian-splatting simulation generates teleop-free fine-tuning data for humanoid VLAs that matches or beats real teleoperated demonstrations. |
| [[papers/humanoid/humanoidumi-robot-free-demonstrations-humanoid-whole-body-manipulation]] HumanoidUMI: Bridging Robot-Free Demonstrations and Humanoid Whole-Body Manipulation | arXiv | ⭐ HIGH PRIORITY: Portable VR/handheld gripper rig collects humanoid whole-body manipulation demonstrations with no robot or teleoperation hardware required. |
| [[papers/humanoid/1x-neo-hands-tendon-driven-dexterous-hand]] 1X NEO Hands — 25-DoF tendon-driven, force-transparent dexterous hand | blog | 1X's new NEO hand uses quasi-direct-drive tendons for native force sensing/control, demoed on LEGO assembly, screwdriver use, and sign language. |
| [[papers/humanoid/boston-dynamics-atlas-training-humanoid-hard-work]] Training a Humanoid Robot for Hard Work | blog | GPU-parallel simulation RL lets Atlas lift 100+ lb loads using proprioceptive/force sensing rather than vision, generalizing zero-shot beyond its training weight range. |

---
*Generated automatically. All entries verified via web search.*
