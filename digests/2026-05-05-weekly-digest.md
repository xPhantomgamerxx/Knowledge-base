---
title: "Weekly Research Digest — 2026-05-05"
date: 2026-05-05
topics: [VLA, WorldModels, RL-Robotics]
tags: [weekly-digest, robotics, embodied-ai]
new_entries: 10
---

## Weekly Research Digest — 2026-05-05

> 10 new entries this week across 3 topic areas.

---

### Vision-Language-Action (VLA) Models

| Release | Venue | Significance |
|---------|-------|--------------|
| [[nvidia-isaac-groot-n1-7]] NVIDIA Isaac GR00T N1.7 | Blog / NVIDIA GTC 2026 | First commercially licensed open humanoid VLA; EgoScale pretraining on 20k+ hours of human video |
| [[gemini-robotics-er-1-6]] Gemini Robotics-ER 1.6 | Blog / Google DeepMind | Adds instrument reading & multi-view success detection; Boston Dynamics collaboration for industrial robotics |
| [[vla-robotics-survey-datasets-benchmarks-data-engines]] VLA in Robotics: Survey of Datasets, Benchmarks, Data Engines | arXiv (2604.23001) | Reframes VLA progress as a data problem; systematic review of data engines and benchmark gaps |

### World Models for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[dreamdojo-generalist-robot-world-model]] DreamDojo: Generalist Robot World Model from Human Videos | arXiv (2602.06949) | 44k-hour human video pretraining with latent proxy actions; real-time inference at 10.81 FPS |
| [[dreamzero-world-action-models-zero-shot-policies]] World Action Models are Zero-shot Policies (DreamZero) | arXiv (2602.15922) | WAM architecture on video diffusion achieves 2x VLA generalization; basis for NVIDIA GR00T N2 |
| [[abot-physworld-interactive-world-foundation-model]] ABot-PhysWorld: Interactive World Foundation Model | arXiv (2603.23376) | 14B DiT with DPO-based physics alignment; outperforms Veo 3.1 and Sora v2 Pro on plausibility |
| [[simulation-distillation-world-model-sim-to-real]] Simulation Distillation (SimDist) | arXiv (2603.15759) | Distills sim reward/value models into latent world model for rapid real-world adaptation |

### Reinforcement Learning for Robotics

| Release | Venue | Significance |
|---------|-------|--------------|
| [[rl-token-bootstrapping-online-rl-vla]] RL Token: Bootstrapping Online RL with VLAs | arXiv (2604.23073) | Lightweight RL token interface; up to 3x speed gain on precision tasks within hours of real-world practice |
| [[large-reward-models-generalizable-online-robot-reward]] Large Reward Models: Online Robot Reward Generation via VLMs | arXiv (2603.16065) | VLM-based frame-level reward without manual engineering; >significant IL improvement in 30 RL iterations |
| [[towards-long-lived-robots-continual-learning-vla-rft]] Towards Long-Lived Robots: Continual Learning VLA via RFT | arXiv (2602.10503) | LifeLong-RFT mitigates catastrophic forgetting in VLAs without online feedback or external reward models |

---
*Generated automatically. All entries verified via web search.*
