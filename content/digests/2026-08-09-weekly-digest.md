---
title: "Weekly Research Digest — 2026-08-09"
date: 2026-08-09
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 36
---

## Weekly Research Digest — 2026-08-09

> 36 new entries this week across 4 topic areas. This week's sweep surfaced an unusually large cluster of VLA/policy post-training work — 17 of the 36 entries touch test-time adaptation, human-in-the-loop correction, preference optimization, or data synthesis for VLAs, flagged ⭐ HIGH PRIORITY below.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/ego2robot-scalable-robot-data-synthesis-egocentric-human-data]] Ego2Robot | arXiv | ⭐ HIGH PRIORITY: Largest ego-to-robot synthetic dataset yet (18.5k hrs, 15 morphologies) for VLA pretraining. |
| [[papers/vla/prigo-test-time-primitive-guidance-diffusion-flow-policies]] PriGo | arXiv | ⭐ HIGH PRIORITY: Test-time primitive guidance steers diffusion/flow policies without retraining. |
| [[papers/vla/retrieve-then-steer-online-success-memory-test-time-adaptation-vla]] Retrieve-then-Steer | arXiv | ⭐ HIGH PRIORITY: Online success-memory test-time adaptation for frozen generative VLAs. |
| [[papers/vla/wizard-robotic-policy-adaptation-weight-space-meta-learning]] WIZARD | arXiv | ⭐ HIGH PRIORITY: Predicts LoRA weight updates in one forward pass — gradient-free VLA adaptation. |
| [[papers/vla/set-supervised-diffusion-policy-action-chunking-corrections]] Set-Supervised Diffusion Policy | arXiv / RSS 2026 | ⭐ HIGH PRIORITY: Contrastive supervision from DAgger-style correction pairs, peer-reviewed at RSS. |
| [[papers/vla/vla-ad-offline-semantic-guidance-efficient-vla-distillation]] VLA-AD | arXiv | ⭐ HIGH PRIORITY: 44x VLA distillation via offline VLM semantic supervision; headline numbers need independent checking. |
| [[papers/vla/retrieval-vla-training-free-in-context-adaptation]] Retrieval-VLA | CVPR 2026 | ⭐ HIGH PRIORITY: Training-free episodic-memory in-context adaptation, peer-reviewed at CVPR. |
| [[papers/vla/dypes-vla-shared-dynamics-embodiment-specific-control-cross-embodiment]] DyPES-VLA | arXiv | Splits shared dynamics priors from embodiment-specific control across arm/dual-arm/humanoid. |
| [[papers/vla/cross-embodiment-transfer-behavior-aligned-representations]] Cross-Embodiment Transfer via Behavior-Aligned Representations | arXiv | New benchmark + representation study for transferring from action-free data. |
| [[papers/vla/cloak-zero-shot-cross-embodiment-masking-end-effector]] Cloak | arXiv | Simple end-effector masking trick enables zero-shot gripper/hand transfer. |
| [[papers/vla/primitivevla-reusable-motion-primitives-efficient-generalizable-manipulation]] PrimitiveVLA | arXiv | Primitive-based "disassemble & assemble" framing matches 100%-data baseline with 50% data on LIBERO. |
| [[papers/vla/instant-fold-in-context-imitation-learning-deformable-manipulation]] Instant-Fold | arXiv | Single-demo in-context learning for cloth folding, sim-to-real zero-shot claim. |
| [[papers/vla/generalist-ai-gen1-thousand-hands-cross-embodiment-end-effector]] Generalist AI — GEN-1 "Thousand Hands" | blog | ⭐ HIGH PRIORITY: 9,000 gripper/tool variants from 500k+ hrs real data; unverified vendor claims. |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/feedback-world-model-precise-guidance-diffusion-policy]] Feedback World Model | arXiv | ⭐ HIGH PRIORITY: Closed-loop world-model guidance corrects diffusion policies online, no retraining. |
| [[papers/world-models/wayve-gaia-4-multimodal-world-models-closed-loop-simulation]] Wayve GAIA-4 | blog | Closed-loop multimodal (video+radar) driving world model for safety evaluation at scale. |
| [[papers/world-models/deform360-massive-multiview-visuotactile-dataset-deformable-world-models]] Deform360 | arXiv / ECCV 2026 | Large visuotactile dataset for comparing 2D vs. 3D world-model paradigms on deformables. |
| [[papers/world-models/how-should-world-models-be-evaluated-decision-making-position]] How Should World Models Be Evaluated? | arXiv | Position paper arguing for interventional-reasoning-centric evaluation over visual realism. |
| [[papers/world-models/gauge-measurement-grounded-benchmark-physical-fidelity-simulation-video-world-models]] GAUGE | arXiv | Measurement-grounded physical-fidelity benchmark spanning simulators and video world models. |
| [[papers/world-models/vlaflow-unified-training-framework-co-training-future-latent-alignment]] VLAFlow | arXiv | ⭐ HIGH PRIORITY: Controlled ablation shows future-latent-alignment + language co-training beats either alone. |
| [[papers/world-models/dream-tac-unified-tactile-world-action-model-contact-rich-manipulation]] Dream-Tac | arXiv | Tactile world-action model, +31.7% action accuracy on contact-rich tasks over vision-only. |
| [[papers/world-models/geniworld-generalizable-interactive-world-model-visual-actions]] GeniWorld | arXiv | URDF-rendered visual-action conditioning reduces scene overfitting, doubles as policy evaluator. |
| [[papers/world-models/omega-0-latent-predictive-world-action-model-concurrent-humanoid-loco-manipulation]] ω₀ | arXiv | Concurrent (non-hierarchical) humanoid loco-manipulation WAM + new 40hr real-world household dataset. |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/rtcf-retrieve-in-time-correct-in-frequency-test-time-correction-vla]] RTCF | arXiv | ⭐ HIGH PRIORITY: Causal memory alignment corrects long-horizon VLA execution error, training-free. |
| [[papers/rl-robotics/unintervene-agentic-intervention-efficient-real-world-rl]] UniIntervene | arXiv | ⭐ HIGH PRIORITY: Learns when to auto-intervene, cutting human supervision cost in real-world RL. |
| [[papers/rl-robotics/mapl-multi-objective-preference-learning-robot-locomotion]] MAPL | arXiv | ⭐ HIGH PRIORITY: LLM-generated multi-criteria preferences replace hand-engineered locomotion rewards. |
| [[papers/rl-robotics/rarm-confidence-gated-progress-reward-modeling-rl-manipulation]] RARM | arXiv | Reward model from a single demonstration, confidence-gated to resist reward hacking. |
| [[papers/rl-robotics/densereward-dense-reward-learning-failure-synthesis-robotic-manipulation]] DenseReward | arXiv | ⭐ HIGH PRIORITY: Dense per-timestep reward model trained on 27k synthesized failure trajectories. |
| [[papers/rl-robotics/progress-reward-modeling-robotic-learning-survey]] Progress Reward Modeling Survey | arXiv | First unified survey of the fast-growing progress-reward-modeling literature. |
| [[papers/rl-robotics/torl-vla-tactile-guided-online-reinforcement-learning-contact-rich-manipulation]] TORL-VLA | arXiv | ⭐ HIGH PRIORITY: Online RL refines tactile VLA actions at deployment for shifted contact conditions. |
| [[papers/rl-robotics/d-vla-high-concurrency-distributed-asynchronous-rl-framework]] D-VLA | arXiv | ⭐ HIGH PRIORITY: Distributed async RL training infrastructure for billion-parameter VLAs. |
| [[papers/rl-robotics/sp3o-reinforcement-learning-segment-preferences-without-reward-modeling]] SP3O | arXiv | ⭐ HIGH PRIORITY: Reward-model-free, critic-free segment-preference RL; robotics + LLM domains. |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/teleopit-full-embodiment-humanoid-teleoperation-system]] Teleopit | arXiv | Full-body VR teleoperation with hand-agnostic retargeting, 90-95% success from 96 demos. |
| [[papers/humanoid/thorarena-benchmarking-humanoid-physical-interaction-motion-force-demonstrations]] ThorArena | arXiv | First benchmark jointly scoring tracking, stability, and robustness under real external force. |
| [[papers/humanoid/heft-heavy-payload-full-size-humanoid-teleoperation-privileged-motion-guidance]] HEFT | arXiv | Teacher-student control for heavy-payload (24kg on 65kg robot) full-size humanoid teleoperation. |
| [[papers/humanoid/humanoidarena-benchmarking-egocentric-hierarchical-whole-body-learning]] HumanoidArena | arXiv | Benchmark shows hierarchical humanoid control is fragile across different low-level trackers. |
| [[papers/humanoid/light-loco-parkour-versatile-perceptive-whole-body-locomotion-multi-skill-distillation]] Light-Loco-Parkour | arXiv | End-to-end onboard-only perceptive locomotion with learned, gate-free skill transitions. |

---
*Generated automatically. All entries verified via web search.*
