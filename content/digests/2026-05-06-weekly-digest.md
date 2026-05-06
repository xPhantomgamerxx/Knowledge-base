---
title: "Weekly Research Digest — 2026-05-06"
date: 2026-05-06
topics: [VLA, WorldModels, RL-Robotics]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 8
---

## Weekly Research Digest — 2026-05-06

> 8 new entries this week across 3 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/vla/acot-vla-action-chain-of-thought-for-vla-models]] ACoT-VLA | CVPR 2026 | Reasons directly in action space via coarse action-intent chains, closing the modality gap between planning and execution |
| [[papers/vla/abot-m0-vla-foundation-model-action-manifold-learning]] ABot-M0 | arXiv | Alibaba's 6M-trajectory cross-embodiment foundation model with Action Manifold Learning for stable diffusion-free action prediction |
| [[papers/vla/dualcot-vla-visual-linguistic-chain-of-thought-parallel-reasoning]] DualCoT-VLA | arXiv | Parallel dual-modal CoT (visual + linguistic) in a single forward pass — SOTA on LIBERO and RoboCasa with no latency penalty |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/world-models/h-wm-hierarchical-world-model-task-motion-planning]] H-WM | arXiv | Hierarchical logical+visual world model enabling robust long-horizon TAMP guidance for VLA policies |
| [[papers/world-models/chain-of-world-world-model-thinking-latent-motion]] Chain of World (CoWVLA) | CVPR 2026 | Latent motion chains as world-model reasoning for VLA pretraining, outperforming pixel-space world models at lower compute |
| [[papers/world-models/hierarchical-planning-with-latent-world-models]] Hierarchical Planning with Latent World Models | arXiv | Meta FAIR's two-level latent planner achieves 70% zero-shot pick-&-place vs. 0% for flat world models |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[papers/rl-robotics/rlinf-co-sim-real-co-training-vla]] RLinf-Co | arXiv | Closed-loop sim RL with real-data anchor improves VLA success +24% (OpenVLA) and +20% (π₀.₅) over SFT co-training |
| [[papers/rl-robotics/what-matters-sim-to-online-rl-real-robots]] What Matters for Sim-to-Online RL | arXiv | 100-run ablation across 3 real robots identifies concrete design choices (data retention, delayed critic) for stable online RL |

---
*Generated automatically. All entries verified via web search.*
