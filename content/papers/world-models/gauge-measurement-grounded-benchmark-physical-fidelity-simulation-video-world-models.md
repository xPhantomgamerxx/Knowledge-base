---
title: "GAUGE: A Measurement-Grounded Benchmark for Physical Fidelity in Simulation Engines and Video World Models"
date: 2026-08-05
topic: WorldModels
tags: [world-models, evaluation, physical-fidelity, benchmark, simulation]
source: https://arxiv.org/abs/2608.05948
venue: "arXiv"
---

## Summary

GAUGE grounds the evaluation of physical fidelity — for both classical simulation engines and generative video world models — in real measurement data, rather than relying on visual plausibility or pixel-level similarity. Authors include researchers affiliated with Shanghai AI Lab.

## Key Contributions

- A benchmark spanning both classical physics simulators and generative video world models, enabling direct comparison between the two paradigms on the same physical-fidelity standard.
- Grounding in real measurement data (rather than proxy visual metrics), addressing a gap similar in spirit to the concurrent "How Should World Models Be Evaluated" position paper also in this quarter's literature.
- Applicable across both the classical-simulation and generative-video-world-model communities, which have historically used disjoint evaluation practices.

## Strengths

- Directly comparing classical simulators and generative video world models on a shared, measurement-grounded standard is valuable precisely because these two paradigms are usually evaluated in isolation, making it hard to know whether video world models are catching up to or still far behind physics engines on actual physical accuracy.
- Being measurement-grounded (real-world sensor data as ground truth) is a meaningfully stronger standard than the perceptual/FVD-style metrics dominant in the video-generation literature.

## Weaknesses

- As a very fresh preprint (arXiv ID from early August 2026), there has been no time for the community to validate the benchmark's own measurement methodology or to check whether it's replicable across labs.
- Measurement-grounded benchmarks are inherently limited to the physical phenomena the authors chose to measure; coverage gaps (e.g., certain material types, contact regimes) would not be visible without independently auditing the benchmark's task suite.

## Open Questions

- What is the actual reported fidelity gap between classical simulators and current generative video world models on GAUGE — does it change the field's confidence in using video world models as simulator replacements?
- How comprehensive is the physical-phenomena coverage (contact, friction, deformation, fluid dynamics, etc.), and are there known blind spots?
- Will this benchmark see adoption as a standard reporting metric for future world-model papers, given how many WAM/world-model papers are being published without a shared fidelity standard?

## Significance

Part of a notable mid-2026 push toward more rigorous, measurement-grounded evaluation of world models — a needed corrective given the sheer volume of world-action-model papers currently reporting largely self-defined or visual-quality metrics.

## Links

- [Paper](https://arxiv.org/abs/2608.05948)
