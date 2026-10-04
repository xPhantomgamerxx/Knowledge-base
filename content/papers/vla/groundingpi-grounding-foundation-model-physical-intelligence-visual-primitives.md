---
title: "GroundingPI: A Grounding Foundation Model towards Physical Intelligence with Visual Primitives"
date: 2026-09-30
topic: VLA
tags: [vla, grounding, perception, rl-finetuning]
source: https://arxiv.org/abs/2609.39601
venue: "arXiv"
---

## Summary

GroundingPI is a 4B-parameter grounding foundation model that outputs points and boxes as quantized coordinates in a shared vocabulary, designed to be fast and precise enough for closed-loop control (object localization in clutter, for tiny objects). Trained via multimodal/spatial pretraining, SFT, and GRPO-based RL, it reaches 73.68% average across 44 baselines on 34 grounding benchmarks, beating the larger GPT-6 Astra (71.54%), and improves downstream robotic manipulation (RoboTwin 2.0) and autonomous-driving performance when used as a visual backbone.

## Key Contributions

- Positions grounding (not end-to-end action generation) as the bottleneck component worth specializing a foundation model around, rather than folding it into a monolithic VLA
- Combines SFT with GRPO-based RL specifically for grounding accuracy, rather than treating grounding as a purely supervised problem
- Demonstrates transfer value as a drop-in visual backbone for downstream manipulation and driving stacks, not just as a standalone benchmark model

## Strengths

- Beating a notably larger model (GPT-6 Astra) on a broad 34-benchmark suite is a meaningful result if the benchmarks are not narrowly overfit to grounding-specific tricks
- The RoboTwin 2.0 out-of-distribution improvement (up to 24.8% relative over the strongest baseline) suggests the grounding gains are not benchmark-only but transfer to actual manipulation robustness
- Open code, weights, and project page support reproducibility

## Weaknesses

- As a perception module rather than a full VLA, its real-world value is contingent on how well it composes with downstream action models — this composability is only indirectly validated via RoboTwin 2.0
- 34 grounding benchmarks is broad but the paper doesn't discuss benchmark overlap/correlation, so the "73.68% average" could be inflated by benchmark redundancy
- No latency/throughput numbers reported alongside the "fast enough for closed-loop control" claim, leaving the core practical claim unverified in the available summary

## Open Questions

- How does GroundingPI integrate with and improve existing deployed VLA stacks beyond RoboTwin 2.0 — does it help real-robot deployments, not just simulated benchmarks?
- What is the actual inference latency on representative robot hardware, and how does that compare to grounding modules already embedded in VLAs like GR00T or π-series models?

## Significance

Reinforces a 2026 trend of decomposing VLA capability into specialized, independently-scalable sub-models (grounding, world modeling, action generation) rather than purely scaling monolithic end-to-end architectures.

## Links

- [Paper](https://arxiv.org/abs/2609.39601)
- [Project page](https://groundingpi.github.io/)
- [GitHub](https://github.com/groundingpi/GroundingPI)
