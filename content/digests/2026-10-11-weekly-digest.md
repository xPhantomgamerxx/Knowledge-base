---
title: "Weekly Research Digest — 2026-10-11"
date: 2026-10-11
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 44
---

## Weekly Research Digest — 2026-10-11

> 44 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/ici-vla-in-context-imitation-spatiotemporally-aligned-demonstrations]] ICI-VLA: In-Context Imitation with Spatiotemporally Aligned Demonstrations for Vision-Language-Action Models | arXiv / IEEE CDC 2026 | ⭐ HIGH PRIORITY: Frozen-weight in-context task adaptation via aligned demo retrieval, beating naive ICL and OpenVLA-OFT on LIBERO/RoboTwin/real robots. |
| [[papers/vla/infinova-infinite-novel-view-augmentation-viewpoint-invariant-robot-policies]] InfiNoVA: Infinite Novel View Augmentation for Viewpoint Invariant Robot Policies | arXiv / TPC Workshop @ SC'26 | ⭐ HIGH PRIORITY: Gaussian-splat-based viewpoint augmentation gives 5.4x robustness to unseen camera placements over prior VISTA baseline. |
| [[papers/vla/turbovla-real-time-vla-32hz-rtx4090]] TurboVLA: Real-Time Vision-Language-Action Model at 32 Hz on an RTX 4090 with <1 GB VRAM | arXiv | 0.2B-param VLA hitting 97.7% LIBERO at 31ms/<1GB VRAM on a consumer GPU, bypassing the usual LLM-backbone bottleneck. |
| [[papers/vla/devol-one-autoregressive-mixture-transformers-vla-latent-world-modeling]] Devol-ONE: One Autoregressive Mixture of Transformers to Unify Vision-Language-Action and Latent World Modeling | arXiv | Single MoT architecture unifying VLA control and V-JEPA-initialized world modeling; 98.4% LIBERO, 71.4% zero-shot LIBERO-Plus. |
| [[papers/vla/where-predictive-supervision-goes-shapes-what-vla-policies-learn]] Where Predictive Supervision Goes Shapes What VLA Policies Learn | arXiv | Analysis paper arguing *how* future-prediction supervision enters a VLA's visual stream, not just its presence, drives robustness. |
| [[papers/vla/ati-vla-action-centric-predictive-vla-actionable-alignment-adaptive-injection]] ATI-VLA: Action-Centric Predictive Vision-Language-Action Models via Actionable Alignment Then Adaptive Injection | arXiv / NeurIPS 2026 | Fixes known modality-misalignment weakness of predictive VLAs; 97.9% LIBERO, 70% real-robot long-horizon. |
| [[papers/vla/fewer-tokens-better-action-gpt-6-astra-robot-agents]] Fewer Tokens, Better Action: GPT-6 Astra Robot Agents with 14% Higher Success Rate but 65% Fewer Tokens | arXiv | Code-execution planning framework (PyRUA-Lean) cuts LLM-agent token/cost overhead while raising task success. |
| [[papers/vla/wbag-whole-body-attached-geometry-safety-framework-vla]] WBAG: A Whole-Body and Attached-Geometry Safety Framework for Vision-Language-Action Manipulation | arXiv | Safety layer covering the whole robot body and grasped-object geometry, not just the end-effector; best on SafeLIBERO. |
| [[papers/vla/is-success-all-you-need-input-perturbations-vla-tabletop-manipulation]] Is Success All You Need? Investigating the Impact of Input Perturbations on VLA Behaviour in Tabletop Manipulation Tasks | arXiv | Shows success-rate alone hides behavioral degradation under perturbation; proposes trajectory-quality metrics. |
| [[papers/vla/chunkvla-am-parallel-action-chunking-additive-manufacturing]] ChunkVLA-AM: Parallel Action Chunking for Vision-Language-Action Robot Control in Additive Manufacturing | arXiv | Real-hardware case study deploying action-chunked OpenVLA-OFT for 3D-print post-processing (92.9% over 42 trials). |
| [[papers/vla/continuous-conditioning-vlas-emg-visual-task-descriptors]] Continuous Conditioning of VLAs with Augmenting EMG and Visual Task Descriptors | arXiv / IROS WORLDS Workshop 2026 | Shows EMG and visual-annotation conditioning can beat language prompts for VLA task specification in cluttered scenes. |
| [[papers/vla/encoded-but-not-in-control-grounding-gap-vision-language-robot-policies]] Encoded but Not in Control: Revealing the Grounding Gap in Vision-Language Robot Policies | arXiv | Finds target info is encoded internally but not acted upon — a representational-to-behavioral "grounding gap" in VLAs/WAMs. |
| [[papers/vla/a-safe-action-is-not-enough-feasible-future-decoding-vla-policies]] A Safe Action Is Not Enough: Feasible-Future Decoding for Vision-Language-Action Policies | arXiv | Introduces a "feasibility-likelihood gap" and a training-free reranker (VICS-G) for safer VLA decoding. |
| [[papers/vla/smart-zero-shot-sim-to-real-articulated-object-manipulation-synthetic-pretraining]] SMART: Zero-Shot Sim-to-Real Articulated Object Manipulation via Large-Scale Synthetic Pretraining | arXiv | ⭐ HIGH PRIORITY: 1M+ synthetic demo dataset (2,500+ articulated objects) enabling 76.7% zero-shot real-robot success. |
| [[papers/vla/vla-acl-action-consistent-visual-token-pruning]] VLA-ACL: Action-Consistent Visual Token Pruning for Efficient Vision-Language-Action Models | arXiv | Action-consistency-supervised pruning cuts 87.5% of visual tokens, 75% compute, 1.5x speedup on frozen VLAs. |
| [[papers/vla/esp-energy-score-policy-one-step-multimodal-action-generation]] ESP: Energy-Score Policy for One-Step Multimodal Action Generation | arXiv | Energy-score training objective enables one-pass multimodal action generation, cutting latency 28.4ms→3.35ms. |
| [[papers/vla/stairvla-stage-aware-hierarchical-action-generation]] StairVLA: Stage-Aware Hierarchical Action Generation for Vision-Language-Action Models | arXiv | Stage-aware high-level/refiner split improves both LIBERO accuracy (96.5%→97.8%) and latency (115ms→44ms). |
| [[papers/vla/bigym-2-benchmarking-humanoid-household-manipulation]] BiGym 2.0: Benchmarking Learned and Agent-Developed Policies for Humanoid Household Manipulation | arXiv | New open-sourced Unitree G1 humanoid benchmark comparing VLA fine-tuning, IL, demo-RL, and LLM coding agents head-to-head. |
| [[papers/vla/vidal-visual-dynamics-grounded-action-latent-space-vla]] ViDAL: A Visual Dynamics-Grounded Action Latent Space for Vision-Language-Action Models | arXiv | Grounds latent action space in predicted visual dynamics; 98.1% LIBERO plus two real-robot platforms. |
| [[papers/vla/warefly-vla-uav-navigation-human-tracking-smart-warehouses]] WareFly-VLA: A Vision-Language-Action Framework for UAV Navigation and Human Tracking in Smart Warehouses | arXiv (submitted to Robotics and Autonomous Systems) | Rare VLA benchmark for drones rather than arms/humanoids; exposes a sharp generalization drop for repurposed manipulation VLAs. |
| [[papers/vla/acttune-action-aware-precision-gpu-adaptation-energy-efficient-vla-inference]] ActTune: Action-Aware Precision and GPU Operating-Point Adaptation for Energy-Efficient Vision-Language-Action Inference | arXiv | Per-call precision/GPU-tuning cuts VLA inference energy up to 76.8% with 2.02x speedup and higher success. |
| [[papers/vla/mim-vla-physical-interaction-representations-gripper-motor-feedback]] MIM-VLA: Learning Physical Interaction Representations from Gripper Motor Feedback | arXiv | Sensor-free object-stiffness discrimination (75% vs 48.8% baseline) from gripper motor telemetry alone. |
| [[papers/vla/vommi-collecting-leveraging-portable-demonstrations-mobile-manipulation]] VOMMI: Collecting and Leveraging Portable Demonstrations for Mobile Manipulation | arXiv | ⭐ HIGH PRIORITY: $100-200 portable RGB rig for mobile-manipulation data collection without the robot, beating OpenPI 0.5 by 8.3pts. |
| [[papers/vla/adapting-vla-models-unknown-visual-disruptions-during-execution]] Adapting Vision-Language-Action Models to Unknown Visual Disruptions During Execution | arXiv | ⭐ HIGH PRIORITY: SALT uses self-supervised test-time adaptation from the unexecuted action-chunk remainder, +9pts success under visual corruption. |
| [[papers/vla/commit-while-futures-agree-consequence-aware-adaptive-action-chunking]] Commit While Futures Agree: Consequence-Aware Adaptive Action Chunking for Robot Manipulation | arXiv | World-model-guided adaptive chunk-commit length cuts failure rate up to 71.8% relative, training-free. |
| [[papers/vla/towards-efficient-robotic-manipulation-models-self-recursive-pruning]] Towards Efficient Robotic Manipulation Models with Self-Recursive Pruning | arXiv | Training-free recursive pruning retains >90% of OpenVLA's success at 50% weight pruning on LIBERO-Object. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/dreamtrue-action-faithful-robot-world-model-counterfactual-post-training]] DreamTrue: Action-Faithful Robot World Model with Counterfactual Post-Training | arXiv | Counterfactual post-training plus a reward-model RL loop cuts human-rated interaction defects from 48% to 6%, winning the AgiBot World Challenge 2026 world-model track. |
| [[papers/world-models/vigar-rethinking-world-action-model-compositional-in-context-manipulation]] Rethinking World-Action Model for Compositional and In-Context Robotic Manipulation (ViGAR) | arXiv | Adds explicit subtask-level planning to world-action models via a shared-representation subgoal planner/executor split for long-horizon compositional manipulation. |
| [[papers/world-models/hwam-humanoid-world-action-model-joint-state-action-generation]] HWAM: Humanoid World Action Model With Joint State-Action Generation | arXiv | Names and fixes the humanoid "action-execution gap" by jointly predicting realized proprioceptive state alongside reference actions, beating Fast-WAM 70.6% vs 43.3% on a precision task. |
| [[papers/world-models/lac-wm-cross-embodiment-robot-foundation-world-models-latent-actions]] Cross-Embodiment Robot Foundation World Models with Latent Actions (LAC-WM) | ICML 2026 | Fei-Fei Li/Meta co-authored ICML 2026 poster showing shared latent action spaces scale across embodiments while explicit action conditioning actively degrades with more embodiments. |
| [[papers/world-models/delta-wam-distilling-action-tangent-fields-world-action-models]] ΔWAM: Distilling Action Tangent Fields into World Action Models | arXiv | Zero-overhead distillation refocuses WAM video-prediction supervision on action-caused dynamics rather than static appearance, improving robustness to visual perturbations. |
| [[papers/world-models/pewam-keep-the-effect-drop-the-actor-programmable-effect-to-execution-world-action-models]] Keep the Effect, Drop the Actor: Programmable Effect-to-Execution World-Action Models (PEWAM) | arXiv | A compact 71.5M-parameter model discards arm-motion conditioning for object-centric "effect programs," running the same compiled demo unmodified across four robot arms. |
| [[papers/world-models/wm-craftnet-world-synesthesia-model-dexterous-in-hand-manipulation]] WM-Craftnet: World Synesthesia Model for Generalizable and Robust Dexterous In-Hand Manipulation | CoRL 2026 (Spotlight, top 4.4%) | CoRL 2026 Spotlight fusing proprioception/depth/tactile into one world-model state driving RL policy directly (no generative rollouts), with a clean-depth reconstruction trick for sim-to-real. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/uniintervene-pp-adaptive-intervention-agent-real-world-rl]] UniIntervene++: An Adaptive Intervention Agent for Efficient Real-World Reinforcement Learning | arXiv | ⭐ HIGH PRIORITY: Adaptive, fully-online intervention agent cuts human supervision to 0.77% of timesteps while beating baselines on 5 real-world sparse-reward manipulation tasks. |
| [[papers/rl-robotics/roboprompt-intuitive-robot-policy-steering-sparse-human-input]] RoboPrompt: Intuitive Robot Policy Steering with Sparse Human Input | arXiv | ⭐ HIGH PRIORITY: Hardware-free noise-space steering lets humans correct Diffusion Policy/π0.5/FastWAM with sparse clicks/traces, doubling as DAgger data for further fine-tuning. |
| [[papers/rl-robotics/embodiedrsi-active-continual-robot-learning-hypothesis-guided-co-evolution]] EmbodiedRSI: Active Continual Robot Learning Through Hypothesis-Guided Co-Evolution | arXiv | ⭐ HIGH PRIORITY: Agentic hypothesis-graph harness actively picks physical experiments to continually patch robot foundation models, hitting 77% on RoboCasa365. |
| [[papers/rl-robotics/agentic-rsr-real-to-sim-to-real-scene-reconstruction-execution-grounded-robot-policies]] Agentic RSR: Real-to-Sim-to-Real through Scene Reconstruction and Execution-Grounded Robot Policies | arXiv | LLM coding agent reconstructs a sim scene from one workspace video and authors/retries a manipulation policy before real-robot deployment, across 18 scenes and 2 robots. |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/hulk-learning-whole-body-forceful-loco-manipulation-humanoids]] HULK: Learning Whole-Body Forceful Loco-Manipulation for Humanoids | arXiv | MPC-guided RL teacher-distillation lets a Unitree G1 carry heavy loads while staying balanced under 130N pushes. |
| [[papers/humanoid/intermimicgen-scaling-humanoid-loco-manipulation-self-evolving-motion-imitation]] InterMimicGen: Scaling Humanoid Loco-Manipulation through Self-Evolving Motion Imitation | arXiv | A self-evolving data flywheel expands scarce human-object-interaction mocap into scalable humanoid training data. |
| [[papers/humanoid/humanoid-horizon-extending-task-horizon-whole-body-loco-manipulation]] Humanoid Horizon: Extending Task Horizon in Whole-Body Loco-Manipulation via Parallel Training, Dynamic Starting, and Reward Gating | arXiv | Diagnoses easy-reward bias and catastrophic forgetting as the cause of long-horizon humanoid task failure and fixes both. |
| [[papers/humanoid/dataset-free-compliant-humanoid-loco-manipulation-dynamic-online-posture]] Dataset-Free Compliant Humanoid Loco-Manipulation with Dynamic Online Posture | arXiv | First mocap-dataset-free whole-body controller, with compliant balance recovery demoed on a real Unitree G1. |
| [[papers/humanoid/general-humanoid-loco-manipulation-egocentric-whole-body-human-data-pretraining]] Towards a General Humanoid Loco-Manipulation Model via Egocentric Whole-Body Human Data Pretraining | arXiv | 500-hour wearable egocentric dataset (HumanVerse-500) plus staged VLA pretraining (λ0) sets new SOTA on SIMPLE. |
| [[papers/humanoid/humanoidtoolbench-benchmarking-humanoid-tool-use-selection-mobile-execution]] HumanoidToolBench: Benchmarking Humanoid Tool Use from Selection to Mobile Execution | arXiv | New benchmark jointly testing tool selection and mobile execution exposes concrete GR00T N1.7 failure modes. |
| [[papers/humanoid/mate-multi-agent-virtual-teleoperation-humanoid-collaboration-data-collection]] MATE: Multi-Agent Virtual Teleoperation Platform for Humanoid Collaboration Data Collection | arXiv | Shared-sim multi-operator teleoperation makes scalable multi-robot humanoid collaboration data collection possible. |

---
*Generated automatically. All entries verified via web search.*
