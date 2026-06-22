---
title: "Weekly Research Digest — 2026-06-22"
date: 2026-06-22
topics: [VLA, WorldModels, RL-Robotics]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 14
---

## Weekly Research Digest — 2026-06-22

> 14 new entries this week across 3 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/thinkingvla-interleaved-vision-language-reasoning]] ThinkingVLA | arXiv 2026-06-16 | Forward+inverse CoT in a MoT architecture; strong gains on long-horizon tasks |
| [[papers/vla/finetuning-vla-fewer-layers]] Finetuning VLA Requires Fewer Layers | arXiv 2026-06-18 | Training-free 50% layer pruning with no performance loss — pi0 and GR00T-N1.5 are over-parameterized |
| [[papers/vla/labvla-grounding-vla-scientific-laboratories]] LabVLA | arXiv 2026-06-11 | First VLA for scientific lab automation; Qwen3-VL + DiT action expert |
| [[papers/vla/agentic-vla-efficient-online-adaptation]] Agentic-VLA | arXiv 2026-05-21 | Agentic online adaptation with adaptive reward synthesis and experience memory |
| [[papers/vla/from-human-videos-to-robot-manipulation-survey]] From Human Videos to Robot Manipulation | IJCAI 2026 Survey | Taxonomy of human-video→VLA learning: latent action, world models, 2D/3D supervision |
| [[papers/vla/dexora-open-source-vla-bimanual-dexterity]] Dexora | ICRA 2026 | First open-source dual-arm dual-hand VLA with 100K sim + 10K real episodes |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/memorywam-efficient-world-action-modeling-persistent-memory]] MemoryWAM | arXiv 2026-06-18 | Hybrid persistent memory (recent+anchor+gist tokens) for non-Markovian WAMs; 70pp improvement |
| [[papers/world-models/weaver-effective-world-model-robotic-manipulation]] WEAVER | arXiv 2026-06-11 | Multi-view flow-matching world model; ρ=0.87 eval correlation, 38% policy improvement on pi0.5 |
| [[papers/world-models/world-models-robotic-manipulation-survey]] World Models for Robotic Manipulation: A Survey | arXiv 2026-06-01 | Three-axis taxonomy: representation predicted, action coupling, pipeline stage |
| [[papers/world-models/world-action-verifier-self-improving-forward-inverse-asymmetry]] World Action Verifier (WAV) | ICLR 2026 Outstanding Paper | Self-improving world models via forward-inverse asymmetry; no ground truth labels needed |
| [[papers/world-models/playworld-robot-world-models-autonomous-play]] PlayWorld | arXiv 2026-03-09 | World model trained from autonomous robot self-play; 65% policy improvement vs. human demos |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/playful-agentic-robot-learning-rats]] Playful Agentic Robot Learning (RATs) | arXiv 2026-06-17 | Self-directed play builds reusable code skill library; +20pp on LIBERO-PRO vs. no-play baseline |
| [[papers/rl-robotics/rove-human-interventions-humanoid-manipulation-rl]] ROVE | arXiv 2026-06-15 | Optimistic Value Estimation for RL from imperfect human interventions on humanoid VLAs |
| [[papers/rl-robotics/mpc-guided-rl-humanoid-locomotion-manipulation]] MPC-Guided RL for Humanoid | arXiv 2026-06-04 | GPU-native parallel MPC reward signal makes MPC-guided RL practical at scale for humanoids |

---
*Generated automatically. All entries verified via web search.*
