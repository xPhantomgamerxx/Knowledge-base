---
title: "Weekly Research Digest — 2026-08-02"
date: 2026-08-02
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 26
---

## Weekly Research Digest — 2026-08-02

> 26 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/gemini-robotics-2-whole-body-intelligence]] Gemini Robotics 2 | blog | First single VLA release from Google DeepMind to control a full humanoid (Apptronik Apollo 2) from locomotion through fine manipulation. |
| [[papers/vla/nvidia-isaac-groot-lerobot-teleop-integration]] NVIDIA Isaac GR00T comes to LeRobot | blog | ⭐ HIGH PRIORITY: Open end-to-end pipeline (Isaac Teleop → GR00T 1.7 fine-tuning → deployment) now integrated into LeRobot. |
| [[papers/vla/what-to-ignore-what-to-react-visually-robust-rl-vla]] What to Ignore, What to React | arXiv | ⭐ HIGH PRIORITY: Adds invariance/sensitivity auxiliary losses during RL fine-tuning of VLAs to learn task-irrelevant vs. task-altering visual change, at no extra inference cost. |
| [[papers/vla/hand-in-the-loop-dexterous-vla-intervention]] Hand-in-the-Loop (HandITL) | arXiv | ⭐ HIGH PRIORITY: Smooths human takeover of dexterous bimanual VLA policies, cutting intervention jitter 99.8% and grasp failures 87.5%. |
| [[papers/vla/learning-from-history-test-time-verification-adaptation-robotics]] Learning From History (HAVE) | CMU RI | ⭐ HIGH PRIORITY: Verifies candidate actions against a robot's own attempt history at test time instead of risky online weight updates. |
| [[papers/vla/far-failure-aware-retry-test-time-recovery]] FAR: Failure-Aware Retry | arXiv | ⭐ HIGH PRIORITY: Test-time failure-aware retry with contrastive preference learning, validated on real xArm hardware. |
| [[papers/vla/axis-community-data-engine-robot-manipulation]] AXIS: Community-Driven Data Engine | arXiv | ⭐ HIGH PRIORITY: Browser-based crowdsourced teleop + validation engine (207 tasks, 50K+ trajectories) lifting π0.5 success by 5.8 points. |
| [[papers/vla/furniturevla-bimanual-furniture-assembly]] FurnitureVLA | arXiv | ⭐ HIGH PRIORITY: First systematic long-horizon bimanual furniture-assembly VLA study with a scalable sim data-generation pipeline. |
| [[papers/vla/tau-touch-augmented-vla-future-visual-supervision]] τ: Touch-Augmented VLA | arXiv | ⭐ HIGH PRIORITY: Learns tactile representations via JEPA-style future-frame prediction as a free, sensor-free training signal. |
| [[papers/vla/t3vf-test-time-training-visual-foresight-vla]] T³VF | arXiv | ⭐ HIGH PRIORITY: Test-time training using a Visual Foresight VLA's own prediction error as self-supervision. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/test-time-scaling-world-action-models-geometric-verification]] Test-Time Scaling for WAMs | arXiv | ⭐ HIGH PRIORITY: Training-free best-of-N test-time scaling for world action models, gated by cross-view geometric consistency. |
| [[papers/world-models/decart-oasis-3-real-time-world-model]] Decart Oasis 3 | blog / press | ⭐ HIGH PRIORITY: Real-time photorealistic driving world model via API; hands-on review found physics/control still fragile over long sessions. |
| [[papers/world-models/world-labs-real-to-sim-to-real-robot-training]] World Labs: Real-to-Sim-to-Real | blog | ⭐ HIGH PRIORITY: R2S2R engine trains zero-real-data robot policies that transferred to a real ALOHA arm for an hour-long autonomous run. |
| [[papers/world-models/definition-roadmap-world-models]] A Definition and Roadmap for World Models | arXiv | Position paper (Shanghai AI Lab) proposing a renderer/simulator/planner taxonomy to unify inconsistent "world model" terminology. |
| [[papers/world-models/sword-style-robust-world-models-vla-post-training]] Sword | arXiv | ⭐ HIGH PRIORITY: Style-robust world-model simulator explicitly for VLA RL post-training, beating the WoVR baseline on LIBERO. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/learning-while-deploying-fleet-scale-rl-generalist-robot-policies]] Learning while Deploying | arXiv | ⭐ HIGH PRIORITY: Fleet-scale offline-to-online RL post-training across 16 real dual-arm robots, reaching 95% avg. success. |
| [[papers/rl-robotics/ohp-rl-online-human-preference-guidance-rl-manipulation]] OHP-RL | arXiv | ⭐ HIGH PRIORITY: Treats human interventions as preference signals via a state-dependent gate, beating HIL-SERL/HG-DAgger with less human effort. |
| [[papers/rl-robotics/pact-preference-calibrated-human-in-the-loop-rl]] PACT | arXiv | ⭐ HIGH PRIORITY: Fixes credit misassignment in HIL-RL corrections; +24.5% success and 1.3x faster convergence across 5 real tasks. |
| [[papers/rl-robotics/flow-reversal-steering-generalist-robot-policies]] Flow Reversal Steering (FRS) | arXiv | ⭐ HIGH PRIORITY: Inverts flow-matching VLA policies to convert coarse human/VLM guidance into high-quality actions — up to 95pp success gains. |
| [[papers/rl-robotics/from-demonstrations-to-rewards-test-time-prompt-optimization-vlm-reward]] From Demonstrations to Rewards | arXiv | ⭐ HIGH PRIORITY: Test-time prompt optimization for VLM reward models using a handful of demonstrations, no extra training. |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/rldx-1-multi-stream-action-transformer-humanoid]] RLDX-1 | arXiv | ⭐ HIGH PRIORITY: Multi-stream action transformer with synthetic-data augmentation for rare scenarios; 86.8% success vs. ~40% for π0.5/GR00T N1.6. |
| [[papers/humanoid/oasis-sim-data-collection-humanoid-loco-manipulation]] OASIS | arXiv | ⭐ HIGH PRIORITY: Sim-only data pipeline reportedly outperforming real-teleop data for zero-shot transfer to a real Unitree G1. |
| [[papers/humanoid/1x-world-model-lab-launch]] 1X World Model Lab launch | blog | 1X's new lab bets on ground-up embodied world-model pretraining over VLA fine-tuning for NEO's autonomy roadmap. |
| [[papers/humanoid/scaling-behavior-foundation-model-humanoid-robots]] Scaling Behavior Foundation Model | arXiv | Systematic scaling study for humanoid whole-body behavior foundation models; 82% MPKPE reduction in global-frame tracking mode. |
| [[papers/humanoid/vlk-humanoid-loco-manipulation-synthetic-interactions]] VLK | arXiv | ⭐ HIGH PRIORITY: Fully synthetic vision-language-kinematics trajectories via Gaussian-splatting scene reconstruction, validated zero-shot on a real G1. |
| [[papers/humanoid/agibot-world-2026-rich-interaction-dataset]] AgiBot World 2026 — Rich Interaction | blog / dataset | ⭐ HIGH PRIORITY: Open dataset deliberately capturing contact-rich failures/edge cases (drops, slips, spills) with paired tactile+vision data. |

---
*Generated automatically. All entries verified via web search.*
