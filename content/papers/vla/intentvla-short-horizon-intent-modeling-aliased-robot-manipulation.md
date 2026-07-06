---
title: "IntentVLA: Short-Horizon Intent Modeling for Aliased Robot Manipulation"
date: 2026-05-14
topic: VLA
tags: [VLA, observation-aliasing, intent-modeling, history-conditioning, action-chunking]
source: https://arxiv.org/abs/2605.14712
venue: "arXiv 2605.14712"
---

## Summary

Robot imitation data is often multimodal: similar visual-language observations can be followed by different action chunks depending on the demonstrator's short-horizon intent or task phase. IntentVLA is a history-conditioned VLA that encodes recent visual observations into a compact short-horizon intent representation to condition action chunk generation, preventing inter-chunk conflict and unstable execution caused by inconsistent intent resampling across replanning steps.

## Key Contributions

- History-conditioned VLA framework encoding compact short-horizon intent representations
- AliasBench: a 12-task ambiguity-aware benchmark on RoboTwin2 that isolates short-horizon observation aliasing
- Improves rollout stability and outperforms strong VLA baselines on AliasBench, SimplerEnv, LIBERO, and RoboCasa
- Code available on GitHub

## Significance

Observation aliasing is a pervasive but underexplored failure mode in VLA deployment; IntentVLA and AliasBench provide both a solution and a principled evaluation framework for this problem.

## Links

- [Paper](https://arxiv.org/abs/2605.14712)
- [GitHub](https://github.com/ZGC-EmbodyAI/IntentVLA)
