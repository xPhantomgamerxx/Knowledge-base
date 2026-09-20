---
title: "Weekly Research Digest — 2026-09-20"
date: 2026-09-20
topics: [VLA, WorldModels, RL-Robotics, Humanoid]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 49
---

## Weekly Research Digest — 2026-09-20

> 49 new entries this week across 4 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/function-preserving-data-generation-real-to-sim-to-real]] Function-Preserving Data Generation for Zero-Shot Real-to-Sim-to-Real Manipulation | arXiv | ⭐ HIGH PRIORITY: Constraint-guided synthetic-data augmentation preserves contact geometry for insertion/assembly, enabling zero-shot real-to-sim-to-real transfer with no teleoperated seed trajectories |
| [[papers/vla/ra-vla-retrieval-augmented-vla-test-time-adaptation]] RA-VLA: Retrieval-Augmented VLA for Test-Time Adaptation | ICML 2026 | ⭐ HIGH PRIORITY: Behavior-aligned retrieval fixes the "superficial retrieval + behavioral inertia" bottleneck in training-free test-time VLA adaptation |
| [[papers/vla/unitree-unifolm-wla-10-open-source-humanoid-foundation-model]] Unitree UnifoLM-WLA-1.0: Fully Open-Sourced Humanoid Foundation Model | blog | 6B-param, 2,500-hour open-source humanoid foundation model unifying desktop and whole-body manipulation across grippers and dexterous hands |
| [[papers/vla/gemini-robotics-er-2]] Gemini Robotics ER 2 | blog | DeepMind's upgraded embodied-reasoning "brain" model orchestrating multiple robot bodies via a hierarchical reasoning+action-model split |
| [[papers/vla/behavior-prompting-policy-demonstrations-as-prompts]] Behavior Prompting Policy: Demonstrations as Prompts for Manipulation | arXiv | ⭐ HIGH PRIORITY: Single-demonstration in-context prompting policy plus iPhUMI data-collection tool; finds task diversity, not demo count, drives generalization |
| [[papers/vla/semivla-semi-supervised-vision-language-action-model]] SemiVLA: Semi-Supervised Vision-Language-Action Model | arXiv | ⭐ HIGH PRIORITY: Self-distilled pseudo-action labeling cuts reliance on costly action-labeled demos for new-environment VLA adaptation |
| [[papers/vla/one-demo-worth-thousand-trajectories-action-view-augmentation]] One Demo is Worth a Thousand Trajectories | arXiv | ⭐ HIGH PRIORITY: 3D Gaussian Splatting + trajectory optimization turns one eye-in-hand demo into many visually- and physically-consistent synthetic demonstrations |
| [[papers/vla/eventvla-event-driven-visual-evidence-memory]] EventVLA: Event-Driven Visual Evidence Memory | arXiv | Predicts future keyframe utility to decide what sparse visual evidence to retain for long-horizon, occlusion-heavy VLA memory |
| [[papers/vla/event-vla-action-conditioned-event-fusion-robust-vla]] Event-VLA: Action-Conditioned Event Fusion for Robust VLA | arXiv | Fuses event-camera streams with RGB, action-conditioned, for VLA robustness under low-light/illumination shifts |
| [[papers/vla/foresightsafety-vla-unified-diagnostic-safety-benchmark]] ForesightSafety-VLA | arXiv | 13-category safety taxonomy plus process-level risk metrics (cumulative safety cost, risk exposure time) for VLA safety evaluation |
| [[papers/vla/hil-umi-human-in-the-loop-post-training-umi]] HIL-UMI: Human-in-the-Loop Post-Training on UMI | arXiv (IJRR 2026) | ⭐ HIGH PRIORITY: Robot-free, policy-guided human-in-the-loop correction collection on UMI hardware, targeting VLA post-training's OOD blind spots |
| [[papers/vla/lessons-learned-real-i-challenge-icra-2026]] Lessons Learned From the REAL-I Challenge at ICRA 2026 | arXiv / ICRA 2026 | ⭐ HIGH PRIORITY: Cross-team empirical comparison of VLA fine-tuning recipes under a fixed real-world demonstration budget |
| [[papers/vla/vlact-representation-centric-continued-pretraining]] VLAct: Representation-Centric Continued Pre-training | arXiv | ⭐ HIGH PRIORITY: Reframes VLA continued pretraining as representation distillation, beating naive data-scaling on a 16-GPU budget |
| [[papers/vla/rmuscle-robotic-muscle-memory-efficient-vla-inference]] rMuscle: Robotic Muscle Memory | arXiv | Dual context/action activation caching cuts VLA inference latency 1.3-1.4x with no retraining |
| [[papers/vla/vla-ulap-interleaving-cloud-vla-calls-edge]] VLA-ULAP: Cloud/Edge Interleaved Action Prediction | arXiv | Tiny 7.4M-param local action predictor interleaves with cloud VLA calls, cutting cloud calls 49-77% at near-parity success |
| [[papers/vla/actionpiece-rethinking-action-tokenization-autoregressive-vla]] ActionPiece: Rethinking Action Tokenization | arXiv | Introduces "physical rank consistency" as an action-tokenizer quality criterion, beating MSE-only tokenizers on SimplerEnv/VLA-Arena |
| [[papers/vla/fluxvla-engine-one-stop-vla-engineering-platform]] FluxVLA Engine | arXiv | Open, configuration-driven engineering platform unifying VLA/WAM/offline-RL training-eval-deployment tooling |
| [[papers/vla/towards-high-dof-dexterous-manipulation-vla-post-training]] Towards High-DoF Dexterous Manipulation through VLA Post-Training | arXiv | ⭐ HIGH PRIORITY: Four-step post-training pipeline (hand-action codec + SFT + DAgger + residual RL) hits 100% success across 5 real dexterous tasks |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/dextouch-wm-tactile-world-models-human-touch]] DexTouch-WM | arXiv | ⭐ HIGH PRIORITY: Matched human/robot tactile hardware lets cheap human-touch data supervise robot contact-dynamics world models |
| [[papers/world-models/ge-act-20-pretraining-scaling-world-action-model]] GE-Act 2.0 | arXiv (AgiBot) | ⭐ HIGH PRIORITY: From-scratch WAM scaling study, 300h→30,000h training data, testing whether WAMs actually need video pretraining |
| [[papers/world-models/wave-go-world-model-navigation-wheel-legged-robots]] WAVE-Go | arXiv | Risk-budgeted adaptive execution lets a navigation world-model plan truncate/replan under estimated cumulative failure risk |
| [[papers/world-models/gigabrain-wbc-05-behavior-world-model-whole-body-control]] GigaBrain-WBC-0.5 | arXiv | First "Behavior World Model" for humanoid WBC jointly predicting action/state/behavior-command, with cross-platform (G1→Maker L01) transfer |
| [[papers/world-models/feel-wm-world-models-off-road-navigation]] Feel-WM | arXiv | First off-road navigation world model predicting proprioceptive slip/tilt/shake, not just visual scene, alongside a failure-risk estimate |
| [[papers/world-models/dido-distilling-interaction-centric-dynamics-one-step-denoising]] DIDO | arXiv | Diagnoses that interaction dynamics resolve last during video-diffusion denoising, then distills WAMs to one step while preserving them |
| [[papers/world-models/modar-modality-autoregressive-world-action-models]] ModAR | arXiv | Controlled ablation finds point-tracks/depth/DINO features — not future RGB — drive WAM performance, at ~20x lower training FLOPs |
| [[papers/world-models/ewam-enhanced-world-action-model-closed-loop-online-adaptation]] EWAM | arXiv | ⭐ HIGH PRIORITY: Four lightweight trainable layers bolted onto a frozen Cosmos3 WAM backbone give zero-shot closed-loop online adaptation with no fine-tuning |
| [[papers/world-models/agentic-real2sim-physics-based-world-modeling-vl-agents]] Agentic Real2Sim | arXiv | VLM-agent pipeline turns a single real interaction video into an editable physics simulator with no manual mesh work |
| [[papers/world-models/pointzero-3d-point-track-completion-transferable-3d-dynamics]] PointZero | arXiv | Robot-action-free 3D point-track completion pretraining objective usable on arbitrary web video |
| [[papers/world-models/wla3-world-latent-action-modeling-semantics-dynamics-kinematics]] WLA³ | arXiv | One learned transition representation jointly serves as dynamics signal, VLM semantic supervision, and action-prediction target from human video |
| [[papers/world-models/zing-05-playable-worlds-real-time-joint-action-text-control]] Zing-0.5 | arXiv | Real-time (24fps, ≈$0.009/min) interactive world model unifying keyboard-style action and free-text control in one generation stream |
| [[papers/world-models/wholebodywam-wbc-grounded-coordination-humanoid-loco-manipulation]] WholeBodyWAM (WBC-Grounded Coordination) | arXiv | Extends pretrained world-action priors to full humanoid loco-manipulation via explicit whole-body-controller grounding |
| [[papers/world-models/wholebodywam-scalable-motion-priors-unimotion-4k]] WholeBodyWAM (Scalable Motion Priors) | arXiv | 4,000+ hour UniMotion-4K corpus shows a consistent motion-pretraining scaling curve for humanoid whole-body world models |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/harbor-harness-framework-agentic-robot-rl]] HARBOR | arXiv | LLM-agent harness automates robot-RL environment/reward/hyperparameter engineering across 16 tasks |
| [[papers/rl-robotics/learning-more-from-less-rl-from-hindsight]] Learning More from Less: RL from Hindsight (LfH) | arXiv | ⭐ HIGH PRIORITY: VLM-based hindsight relabeling recovers learning signal from failed VLA RL rollouts, 5x sample-efficiency gain |
| [[papers/rl-robotics/retvl-retry-supervised-value-learning-robot-imitation]] ReTVL | arXiv | Learns mistake-sensitive value functions by treating demonstration "retries" as supervision rather than noise |
| [[papers/rl-robotics/otql-optimal-transport-q-learning-flow-policy-steering]] OTQL | arXiv | ⭐ HIGH PRIORITY: Advantage-weighted OT flow matching RL-tunes flow-matching VLAs to +40-50pp success with 70% fewer denoising steps, from 50-60 episodes |
| [[papers/rl-robotics/intrinsic-robot-rewarding-reusing-vla-representations]] Intrinsic Robot Rewarding | arXiv | ⭐ HIGH PRIORITY: Reuses a VLA's own frozen visual encoder as reward feature space, no separate reward model needed |
| [[papers/rl-robotics/gr2po-group-relative-return-policy-optimization]] GR2PO | arXiv | Extends GRPO-style critic-free policy optimization to dense-reward continuous control via per-timestep return estimation |
| [[papers/rl-robotics/rl-real-time-vision-language-action-policies]] Reinforcement Learning for Real-Time VLA Policies | arXiv (Stanford) | ⭐ HIGH PRIORITY: Brings latency/staleness-aware asynchronous execution into RL fine-tuning of VLAs, not just imitation learning |
| [[papers/rl-robotics/learning-process-rewards-success-visitation-matching]] Learning Process Rewards via Success Visitation Matching | arXiv | Discriminator-based dense process reward that provably preserves the sparse-reward optimal policy |
| [[papers/rl-robotics/coherent-off-policy-improvement-large-behavior-models]] Coherent Off-Policy Improvement of Large Behavior Models | arXiv | ⭐ HIGH PRIORITY: IRL-learned dense rewards enable off-policy improvement of large behavior models with non-degradation guarantees, ≥90% success on 5/6 tasks |

### Humanoid Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/humanoid/helix-25-zero-shot-30-home-generalization]] Helix 2.5: Zero-Shot 30-Home Generalization | blog | Figure's Index human-video pretraining lifts zero-shot whole-task success 9%→56% across 30 unseen homes |
| [[papers/humanoid/apptronik-apollo-2-robot-park]] Apptronik Apollo 2 and "Robot Park" | blog | New bipedal/wheeled humanoid platform paired with a 90,000 sq ft fleet-scale data-collection facility and a DeepMind data partnership |
| [[papers/humanoid/openhlm-empirical-recipe-whole-body-humanoid-loco-manipulation]] OpenHLM | arXiv | Systematic empirical recipe for whole-body humanoid VLAs: teleop interface design, dual-arm-to-humanoid transfer, HuMI co-training |
| [[papers/humanoid/omnicontact-chaining-meta-skills-contact-flow]] OmniContact | arXiv | "Contact flow" representation chains loco-manipulation meta-skills with autonomous recovery, +40-67pp over baselines |
| [[papers/humanoid/pot-vla-persistent-3d-object-tokens-humanoid-vla]] POT-VLA: Persistent 3D Object Tokens | arXiv | Closes the perception-action-verification loop, nearly doubling real-G1 success (39/80→71/80) over GR00T-N1.7 |
| [[papers/humanoid/spot-spatial-perception-long-horizon-humanoid-teleoperation]] SPOT | arXiv | Viewpoint-decoupled VR teleoperation interface improves long-horizon humanoid demonstration-collection ergonomics |
| [[papers/humanoid/viloman-visual-proprioceptive-whole-body-loco-manipulation]] ViLoMan | arXiv | Teacher-student distilled whole-body policy from partial human demonstrations, deployed on real G1 with only onboard depth+proprioception |
| [[papers/humanoid/glori-closed-loop-whole-body-tracking-humanoid]] GLoRI | arXiv | Single-policy autonomous (non-teleoperated) closed-loop loco-manipulation over unseen objects on a real Unitree G1 |

---
*Generated automatically. All entries verified via web search.*
