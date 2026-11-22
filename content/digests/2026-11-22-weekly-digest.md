---
title: "Weekly Research Digest — 2026-11-22"
date: 2026-11-22
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 20
---

## Weekly Research Digest — 2026-11-22

> 20 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/nvidia-groot-2-isaac-lab-3-corl-2026]] GR00T 2 and Isaac Lab 3.0 | blog / CoRL 2026 | NVIDIA's open world-action model + Newton-backed sim stack for humanoids; third-party benchmark claims unverified. |
| [[papers/vla/lerobot-v070-interactive-rollouts-world-action-models]] LeRobot v0.7.0 | blog | Adds mid-episode steering and remote policy serving — useful infra for human-in-the-loop correction workflows. |
| [[papers/vla/scalevla-552b-deepseek-backbone-robot-action-policy]] ScaleVLA (552B DeepSeek-V4.1-Flash backbone) | arXiv | Controlled backbone-scaling study for VLA sample efficiency/generalization; authorship/ID not independently confirmed. |
| [[papers/vla/chronos-policy-learning-robot-policies-physical-time]] Chronos Policy | arXiv | Time-aware RoPE for diffusion-transformer policies, improving robustness to asynchronous sensing/control timing. |
| [[papers/vla/tfp-physical-time-missing-dimension-robot-policy-memory]] Physical Time as a Missing Dimension of Robot Policy Memory | arXiv | Memory state evolves over measured real time rather than step count; tested on duration-constrained tasks. |
| [[papers/vla/ttt-rm-test-time-training-residual-memory-robot-policies]] Test-Time Training as Residual Memory for Robot Policies | arXiv | ⭐ HIGH PRIORITY: reframes TTT fast-weight state to store only non-recoverable info, complementing retrieval memory. |
| [[papers/vla/verify-act-distill-test-time-compute-adaptation-vla]] Verify, Act, Distill | arXiv | ⭐ HIGH PRIORITY: distills verified test-time-compute rollouts back into the policy via LoRA, closing the inference-time-verification loop. |
| [[papers/vla/ttt-vla-exploring-training-human-demonstrations]] TTT in VLA Models: Exploring Training with Human Demonstrations | arXiv | ⭐ HIGH PRIORITY: transparent negative result — TTT layers on InternVLA-A1/π0.5 show no clear benefit from demonstration memory. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/roboimagine-world-models-semantic-visual-feedback]] Learning Robotic World Models with Semantic and Visual Feedback (RoboImagine) | arXiv | Post-trains world models with VLM-judge + pixel preference optimization instead of reconstruction loss alone. |
| [[papers/world-models/nvidia-cosmos-3-open-checkpoints-robot-av-simulation]] NVIDIA Releases Four Open Cosmos 3 Checkpoints | blog | Open-weight action-conditioned simulation checkpoints for robot-arm and AV world simulation. |
| [[papers/world-models/does-your-world-model-know-actions-have-consequences]] Does Your World Model Know Actions Have Consequences? | CoRL 2026 Workshop | Position paper flagging that common world-model metrics don't actually verify action-sensitivity. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/repair-distilling-rl-specialists-vla-policies]] Beyond Policy Patches (REPAIR) | arXiv | ⭐ HIGH PRIORITY: value-guided distillation of RL specialists into a single flow-matching VLA to fix long-horizon precision failures. |
| [[papers/rl-robotics/phil-proactive-human-in-the-loop-intervention-preference-learning]] Correct Robots Before They Make Mistakes (PHIL) | arXiv | ⭐ HIGH PRIORITY: proactive, pre-failure human intervention via trajectory prediction + preference learning; beats HG-DAgger. |
| [[papers/rl-robotics/wicl-world-in-context-learning-agentic-robot-manipulation]] World In-Context Learning for Agentic Robot Manipulation (WICL) | arXiv | ⭐ HIGH PRIORITY: weight-free test-time adaptation via scene-rehearsal and a retrievable Task Memory with claimed cross-embodiment transfer. |
| [[papers/rl-robotics/tempo-efficient-test-time-adaptation-robot-policies]] Efficient Test-Time Adaptation For Robot Policies (TEMPO) | arXiv / NeurIPS 2026 | ⭐ HIGH PRIORITY: lightweight actor-only test-time adaptation using a frozen critic, for on-device RL locomotion policies (Go1/Go2/G1). |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/agibot-go-3-preview-world-reasoning-action-model]] AGIBOT GO-3 Preview | blog / Innovation Day 2026 | Claims top-3 embodied AI benchmark rankings and an open-source pledge; unverified pending a technical report. |
| [[papers/humanoid/airoa-0-long-horizon-cross-embodiment-manipulation-handheld-data]] AIRoA-0 | arXiv | ⭐ HIGH PRIORITY: π0.5-based VLA trained on 16,151h of human handheld data with zero robot data, 78% vs 27% baseline success. |
| [[papers/humanoid/locomanilab-unified-testbed-humanoid-loco-manipulation]] LocoManiLab | arXiv | New benchmark isolating controller quality from policy quality across 12 baselines incl. π0.5. |
| [[papers/humanoid/festival-video-to-stage-sim-to-real-dance-humanoid]] From Festival Video to the Stage | arXiv | Single-GPU, single-video-to-hardware sim-to-real pipeline for expressive whole-body dance on a commercial Unitree G1. |
| [[papers/humanoid/boston-dynamics-atlas-wheeled-legs-whole-body-control]] Boston Dynamics: Wheeled Atlas | blog/video | Controller-generalization stress test at the actuator limit; press-only, no technical report. |

---
*Generated automatically. All entries verified via web search.*
