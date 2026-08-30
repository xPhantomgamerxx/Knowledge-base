---
title: "Weekly Research Digest — 2026-08-30"
date: 2026-08-30
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 36
---

## Weekly Research Digest — 2026-08-30

> 36 new entries this week across 4 topic areas, with a strong showing (16 entries) in the VLA post-training / data-scaling cross-cutting priority.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/synthicl-scalable-in-context-imitation-learning-synthetic-data]] SynthICL: Scalable In-context Imitation Learning with Synthetic Data | arXiv | ⭐ HIGH PRIORITY: RGB-only synthetic data trains in-context imitation policies hitting 79% success on 16 unseen real tasks from one demo. |
| [[papers/vla/e-tts-embodied-test-time-scaling-framework-robotic-manipulation]] E-TTS: A New Embodied Test-Time Scaling Framework for Robotic Manipulation | arXiv (ECCV 2026) | ⭐ HIGH PRIORITY: history-aware iterative refinement with VLM verifiers gives up to +33% (sim) / +27% (real) on top of standard VLAs. |
| [[papers/vla/self-improving-vla-selected-diffusion-noise-spurious-robust-action]] Self-Improving VLA Policies: Selected Diffusion Noise | arXiv | ⭐ HIGH PRIORITY: training-free test-time noise selection reduces spurious-cue reliance across π0, GR00T-N1.5/1.6. |
| [[papers/vla/logic-vla-temporal-logic-conditioned-vision-language-action-model]] Logic-VLA: A Temporal Logic Conditioned VLA Model | arXiv | ⭐ HIGH PRIORITY: STL-conditioned VLA trained with flow-matching preference optimization over safety-satisfying vs. violating rollouts. |
| [[papers/vla/vane-reliable-test-time-training-vla-future-visual-representation]] VANE: Reliable Test-Time Training for VLA via Future Visual Representation Prediction | arXiv | ⭐ HIGH PRIORITY: TTT that conditions updates on the future visual consequences of actions to avoid corrupting subsequent steps. |
| [[papers/vla/robosynchallenge-mastering-real-world-dexterity-synthesized-manipulation-skills]] RoboSynChallenge: Mastering Real-World Dexterity via Synthesized Manipulation Skills | arXiv (NeurIPS 2026 competition) | ⭐ HIGH PRIORITY: competition benchmark explicitly built to test synthetic-data-trained bimanual policies against real-world-only scoring. |
| [[papers/vla/elastic-efficiently-learning-adaptively-scale-test-time-compute]] ELASTIC: Adaptively Scaling Test-Time Compute for Generative Control Policies | arXiv (CMU) | ⭐ HIGH PRIORITY: meta-MDP allocates sequential vs. parallel test-time compute for diffusion/flow policies, cutting π0.5 latency 34% at matched success. |
| [[papers/vla/g05-galaxea-autoregressive-stream-robot-reasoning-action]] G0.5 (Galaxea): One Autoregressive Stream for Robot Reasoning and Action | arXiv | Major new open VLA foundation model — single decoder stream unifies reasoning and action tokens, no separate VLM encoder + action head. |
| [[papers/vla/ervla-revisiting-embodied-chain-of-thought-generalizable-robot-manipulation]] Revisiting Embodied Chain-of-Thought for Generalizable Robot Manipulation | arXiv | Largest embodied-CoT corpus to date (978K trajectories); reasoning-dropout training hits 86.9% on LIBERO-Plus. |
| [[papers/vla/robodojo-unified-sim-real-benchmark-generalist-robot-manipulation]] RoboDojo: A Unified Sim-and-Real Benchmark for Generalist Robot Manipulation Policies | arXiv | 42 sim + 18 real tasks scoring generalization, memory, precision and long-horizon execution in one benchmark. |
| [[papers/vla/active-real-world-factor-based-evaluation-generalist-robot-policies]] Active Real-World Factor-Based Evaluation for Generalist Robot Policies | arXiv | Frames policy evaluation as sequential experimental design over task-factor space, validated against 700+ real evals per task. |
| [[papers/vla/univiewvla-unified-multiview-vision-language-action-world-modeling]] UniviewVLA: A Unified Multiview VLA Model with World Modeling | arXiv | Infers multiview future scene evolution from two cameras, lifting occlusion-task success from 40.0%→73.3%. |
| [[papers/vla/baton-long-horizon-robot-manipulation-agentic-subtask-exploration]] Don't Drop the BATON: Long-Horizon Manipulation via Agentic Subtask Exploration | arXiv | Coding-agent layer drives long-horizon tasks over a frozen VLA via test-time exploration and checkable handoff contracts. |
| [[papers/vla/ucag-p-unified-camera-centric-action-geometry-pretraining]] One Policy, Many Embodiments: Unified Camera-Centric Action Geometry Pre-training | arXiv (Xiaomi) | Maps arms, humanoids and human hands into a shared camera-frame motion space, enabling joint robot+human training. |
| [[papers/vla/streampi-streaming-multimodal-temporal-modeling-vla]] StreamPI: Streaming Multimodal Temporal Modeling for VLA Models | arXiv (HKU-SAIL) | Adds streaming temporal reasoning to single-frame π0.5 with only ~9.2ms added latency for 5-frame context. |
| [[papers/vla/muvla-recurrent-memory-partially-observable-manipulation-vla]] μVLA: On Recurrent Memory for Partially Observable Manipulation in VLA Models | arXiv | Controlled ablation isolating what pure in-backbone recurrence buys over prior memory-VLA approaches. |
| [[papers/vla/revisiting-parameter-redundancy-vla-vlm-to-vla-adaptation]] Revisiting Parameter Redundancy in VLA Models | arXiv | Challenges the assumption that pruned VLA parameters are truly redundant during VLM-to-VLA adaptation. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/wam-ttt-steering-world-action-models-watching-human-play-test-time]] WAM-TTT: Steering World-Action Models by Watching Human Play at Test Time | arXiv | ⭐ HIGH PRIORITY: test-time training absorbs raw human video into a frozen WAM's adaptive memory via self-supervised prediction. |
| [[papers/world-models/zero-wam-in-context-world-action-modeling-human-videos]] Zero-WAM: In-Context World-Action Modeling from Human Videos | arXiv | ⭐ HIGH PRIORITY: HumanGen pipeline synthesizes 74.2K human-robot ICL pairs; zero-shot task following from a human video prompt. |
| [[papers/world-models/wall-ss-scaling-long-horizon-world-models-next-scale-autoregression]] WALL-SS: Scaling Long-horizon World Models via Next-Scale Autoregression | arXiv | Coarse-to-fine scale-wise generation plus scale-compressed memory targets coherent minute-long rollouts under bounded memory. |
| [[papers/world-models/clap-cross-embodiment-video-world-models-zero-shot-physical-simulators]] CLAP: Cross-Embodiment Video World Models are Zero-Shot Physical Simulators | arXiv | Trains on internet-scale human + robot video toward a universal, embodiment-agnostic physical simulator. |
| [[papers/world-models/phizero-world-model-physical-language]] PhiZero: A World Model Built Around Physical Language | arXiv (CASIA) | "Reason-then-render": predicts a compact discrete physical-language sequence before diffusion-decoding to video, ~175x token reduction. |
| [[papers/world-models/graphop-wm-world-models-morphology-parameter-generalization]] Graph-Operator World Models for Morphology-Parameter Generalization | arXiv | Factorizes dynamics into a morphology-independent basis plus a structured operator for generalizing across robot body variants. |
| [[papers/world-models/maskwam-unifying-mask-prompting-prediction-world-action-models]] MaskWAM: Unifying Mask Prompting and Prediction for World-Action Models | arXiv | Object-centric mask prediction plus first-frame mask prompts cut language ambiguity in cluttered scenes. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/r3-training-robots-reason-natural-language-reinforcement-learning]] R³: Training Robots to Reason in Natural Language via Reinforcement Learning | arXiv (CMU) | ⭐ HIGH PRIORITY: mid-training on reasoning traces + rubric-based RL turns a VLM into a robotic reasoner guiding low-level control. |
| [[papers/rl-robotics/beyond-imitation-self-improving-robot-policies-off-policy-q-planning]] Beyond Imitation: Self-Improving Robot Policies via Off-Policy Q-Planning | arXiv (Georgia Tech) | ⭐ HIGH PRIORITY: a small Q-function bolted onto a frozen BC policy enables online self-improvement without touching billion-parameter weights. |
| [[papers/rl-robotics/rynnvalue-scaling-robotic-value-foundation-models-temporal-distance]] RynnValue: Scaling Robotic Value Foundation Models with Temporal Distance | arXiv (Alibaba DAMO) | ⭐ HIGH PRIORITY: label-free temporal-distance value model lifts real-world RL fine-tuning success from 52.5%→72.5%. |
| [[papers/rl-robotics/dipod-diffusion-policy-optimization-without-drifting-apart]] DiPOD: Diffusion Policy Optimization without Drifting Apart | arXiv (UC Berkeley) | Diagnoses and fixes a "double-drift" instability in diffusion policy-gradient RL via interleaved self-distillation. |
| [[papers/rl-robotics/vlm-pbrs-automating-potential-based-reward-shaping-vlm-guidance]] Automating Potential-based Reward Shaping with VLM Guidance | arXiv | Learns potential-based reward shaping from VLM image-pair preferences while preserving optimal-policy guarantees. |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/humanoid-dart-diffusion-guided-augmentation-loco-manipulation]] Humanoid-DART: Diffusion-guided Augmentation for Humanoid Loco-Manipulation | arXiv | ⭐ HIGH PRIORITY: diffusion-generated goal trajectories plus curriculum relabeling scale humanoid training data from just 4 seed demos. |
| [[papers/humanoid/deed-data-efficient-post-training-retail-humanoid-vla]] DEED: Data-Efficient Post-Training VLA Framework for Retail Humanoids | arXiv | ⭐ HIGH PRIORITY: data-efficient post-training pipeline (RECAP-style experience refinement) deployed on a real supermarket restocking task. |
| [[papers/humanoid/skild-s1-in-context-learning-robotics]] Skild AI: Introducing S1 — In-Context Learning for Robotics | blog | ⭐ HIGH PRIORITY: single human-video demo drives zero-fine-tuning task execution, 66% vs. 9% baseline on unseen long-horizon tasks. |
| [[papers/humanoid/figure-ai-index-crowdsourced-human-video-data-platform]] Figure AI: Index — Crowdsourced Human Video Data Platform | blog / press | ⭐ HIGH PRIORITY: gig-economy data platform reports 16M+ videos from 108 countries feeding Helix's training pipeline, $1B committed. |
| [[papers/humanoid/wolf-vla-whole-body-humanoid-optimal-locomotion-framework]] WOLF-VLA: Whole-Body Humanoid Optimal Locomotion Framework | arXiv | Large optimal-control-generated locomotion dataset trains a language-conditioned whole-body VLA for physically consistent motion. |
| [[papers/humanoid/golem-modular-humanoid-autonomy-ev-battery-disassembly]] GOLEM: Modular Humanoid Autonomy Towards EV Battery Disassembly | arXiv | Open-source modular ROS2 system on a Unitree H1-2 disassembles a real Hyundai Ioniq 5 battery pack across three autonomy levels. |
| [[papers/humanoid/xiaomi-second-generation-humanoid-tieda-debut]] Xiaomi's Second-Generation Humanoid Robot Debuts at WRC 2026 | blog / press | New 66-DoF Xiaomi humanoid trained embedded in the company's own EV factory; embodied model drives fully autonomous action selection. |

---
*Generated automatically. All entries verified via web search.*
