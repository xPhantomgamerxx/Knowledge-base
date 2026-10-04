---
title: "Weekly Research Digest — 2026-10-04"
date: 2026-10-04
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 23
---

## Weekly Research Digest — 2026-10-04

> 23 new entries this week across 4 topic areas, with an unusually strong cluster of VLA post-training / test-time-adaptation work (18 of 23 entries flagged high priority).

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/dissecting-advantage-guided-post-training-vla-policies]] Dissecting Advantage-Guided Post-Training for VLA Policies | arXiv | ⭐ HIGH PRIORITY: Controlled ablation isolating which RL post-training design choices (advantage construction, calibration, weighting) actually drive gains. |
| [[papers/vla/self-adaptive-vla-robust-robot-deployment]] Self-Adaptive VLA for Robust Robot Deployment | arXiv | ⭐ HIGH PRIORITY: Post-training recipe letting a VLA self-adapt to deployment-time hardware drift using its own rollouts as context, no inference overhead. |
| [[papers/vla/recastvla-past-interaction-future-control-adaptive-policy-states]] RecastVLA: From Past Interaction to Future Control with Adaptive Policy States | arXiv | ⭐ HIGH PRIORITY: Action-side test-time training giving a flow-matching VLA a persistent policy state; +10.68pp on RoboTwin Clean-to-Clean. |
| [[papers/vla/phyvisgen-physically-visually-high-fidelity-robotic-manipulation-data-generation]] PhyVisGen: Physically and Visually High-Fidelity Robotic Manipulation Data Generation | arXiv | ⭐ HIGH PRIORITY: IPC-based contact simulation + path-traced rendering; policies trained purely on synthetic data hit 65-95% real-robot success. |
| [[papers/vla/vlarl-augmenting-vla-simulation-trained-latent-conditioned-residual-rl]] VLaRL: Augmenting VLA Models with Simulation-Trained Latent-Conditioned Residual RL | arXiv | ⭐ HIGH PRIORITY: Sim-trained residual RL policy conditioned on the VLA's own latent space, deploys to real hardware with no on-robot RL. |
| [[papers/vla/groundingpi-grounding-foundation-model-physical-intelligence-visual-primitives]] GroundingPI: A Grounding Foundation Model towards Physical Intelligence with Visual Primitives | arXiv | 4B grounding model (SFT+GRPO) beats larger GPT-6 Astra on 34 benchmarks; improves downstream manipulation and driving as a visual backbone. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/worldline-action-driven-visual-simulation-robotic-manipulation]] WorldLine: Action-Driven Visual Simulation for Robotic Manipulation | arXiv | Decouples dynamics learning (10,000+ hrs action-free video) from action grounding (2,000+ hrs across 10+ embodiments) via a shared image-space action interface. |
| [[papers/world-models/robocoach-world-models-active-coaches-compositional-robot-skills]] RoboCoach: World Models as Active Coaches for Compositional Robot Skills | arXiv | ⭐ HIGH PRIORITY: Uses a shared world model to imagine failures and target where to collect new demonstrations; 150 demos take success from ~13-40% to 75-84%. |
| [[papers/world-models/world-action-agent-harnessing-vlms-world-action-rehearsal]] World Action Agent: Harnessing VLMs for Robot Manipulation via World Action Rehearsal | arXiv | ⭐ HIGH PRIORITY: VLM agent "rehearses" actions before execution; harness-generated traces fine-tune a small model from 1.7%→43.3% OOD success. |
| [[papers/world-models/data-pyramid-embodied-manipulation-survey]] Data Pyramid for Embodied Manipulation: A Survey | arXiv survey | ⭐ HIGH PRIORITY: Five-tier taxonomy (real-robot, UMI, ego/exo video, sim, general VL data) for how foundation models mix training data sources. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/find-something-you-cant-do-agentic-rl-self-improving-vla]] Find Something You Can't Do: Agentic Real-World RL for Self-Improving VLA Models | arXiv | ⭐ HIGH PRIORITY: Scene-conditioned autonomous practice (no resets) lifts human-assessed success 55%→71.9% across 8 real tasks, no reward labels. |
| [[papers/rl-robotics/parts-real-world-subtask-rl-long-horizon-manipulation-minimal-human-intervention]] From Pretraining to Proficiency: Real-World Subtask RL for Long-Horizon Manipulation (PARTS) | arXiv | ⭐ HIGH PRIORITY: Targets RL fine-tuning only at failing subtask bottlenecks; 32%→61% and 50%→95% success with tens of minutes of real RL. |
| [[papers/rl-robotics/res-hil-human-guided-residual-rl-sample-efficient-dexterous-manipulation]] Res-HIL: Human-Guided Residual RL for Sample-Efficient Dexterous Manipulation | arXiv | ⭐ HIGH PRIORITY: Residual RL on a frozen policy, dual-uses human interventions as supervision and reward; beats 5x-larger imitation datasets with 20 demos. |
| [[papers/rl-robotics/tear-test-time-adaptation-manipulation-policies-actuator-degradation]] Test-Time Adaptation of Manipulation Policies Under Actuator Degradation (TeAR) | arXiv | ⭐ HIGH PRIORITY: Policy-agnostic telemetry-aware action rectification; +12% avg success across 18 policy-task pairs, +10-15% under motor heating. |
| [[papers/rl-robotics/scout-scouting-dynamics-gap-test-time-policy-adaptation]] Scouting the Dynamics Gap: Test-Time Policy Adaptation via Action-Outcome Feedback (SCOUT) | CoRL 2026 | ⭐ HIGH PRIORITY: Meta-learned belief latent adapts to unknown physical dynamics on the fly from action-outcome feedback alone. |
| [[papers/rl-robotics/preferenceflow-test-time-guidance-flow-matching-robot-policies-human-interventions]] PreferenceFlow: Test-Time Guidance of Flow-Matching Robot Policies from Human Interventions | IROS 2026 | ⭐ HIGH PRIORITY: Retraining-free test-time preference guidance from human interventions; 69%→90.5% on real precision insertion. |
| [[papers/rl-robotics/prism-grpo-faster-vla-policy-optimization-splitting-same-outcome-groups]] Prism-GRPO: Faster VLA Policy Optimization via Splitting Same-outcome Groups | arXiv | ⭐ HIGH PRIORITY: Fixes GRPO's wasted-rollout problem on same-outcome groups; up to 56% fewer rollouts to reach target success. |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/dexweave-learning-dexterous-humanoid-loco-manipulation-human-demonstrations]] DexWeave: Learning Dexterous Humanoid Loco-Manipulation from Human Demonstrations | arXiv | Two-stage retargeting preserving lower-body support while refining upper-body interaction; real deployment on Unitree G1 + Inspire hands. |
| [[papers/humanoid/prism-counterfactual-video-generation-scalable-humanoid-loco-manipulation]] Counterfactual Video Generation Enables Scalable Humanoid Loco-Manipulation (PRISM) | CoRL 2026 | ⭐ HIGH PRIORITY: V2V generation expands 4 real videos into 256 synthetic ones; zero-shot real-world carry/pick/drop across object categories. |
| [[papers/humanoid/wb-wam-heterogeneous-body-hand-pretraining-humanoid-loco-manipulation]] WB-WAM: Heterogeneous Body-Hand Pre-training for Humanoid Loco-Manipulation | arXiv | Whole-body World Action Model pretrained on 1,880+ hrs partially-annotated video/motion; 84.0% mean success across 5 real tasks. |
| [[papers/humanoid/tango-humanoid-navigation-cluttered-environments-whole-body-vla]] TANGO: Humanoid Navigation in Cluttered Environments with a Whole-Body VLA Model | arXiv | Reframes navigation as whole-body control (29-DoF); sim-only training, zero-shot 30m real traversal of cluttered office on Unitree G1. |
| [[papers/humanoid/learning-diverse-humanoid-tasks-synthetic-video-scenarios-without-real-world-data]] Learning Diverse Humanoid Tasks via Synthetic Video Scenarios without Real World Data | IEEE/ASME AIM 2026 | ⭐ HIGH PRIORITY: Text-to-video generates diverse human motion demonstrations; retargeted and RL-tracked with zero real demonstration data. |
| [[papers/humanoid/skild-ai-physical-self-play]] Skild AI: Physical Self-Play | blog | ⭐ HIGH PRIORITY: S1 foundation model learns soccer tactics via 140+ simulated years of self-play post-training, transferred to a physical humanoid. |

---
*Generated automatically. All entries verified via web search against primary sources (arXiv abstract pages, project pages, or company blogs).*
