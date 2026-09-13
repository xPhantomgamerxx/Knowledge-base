---
title: "SolarWM: Open Data and Scalable Training for Long-Horizon Video World Models"
date: 2026-09-02
topic: WorldModels
tags: [video-world-model, open-source, data-engine, long-horizon, real-time]
source: https://arxiv.org/abs/2609.02886
venue: "arXiv"
---

## Summary

SolarWM is a fully open foundation for building interactive video world models, spanning data preparation, backbone adaptation, and long-horizon inference. It pairs a reconfigurable multi-source data engine — which normalizes 1.43 million clips from ten datasets into a unified, frame-aligned contract of video, metric camera geometry, captions, and provenance — with a "backbone-native" adaptation framework that turns existing video generators (Wan2.2, LTX-2.5, MiniMax-H3) into causal, real-time-interactive world models at scale (5B–33B parameters), trained only on 5-second sequences yet capable of stable rollouts from minutes to hours.

## Key Contributions

- A reconfigurable, multi-source data engine converting 1.43M clips (25.85TB, with 549K rejected clips carrying machine-readable rejection reasons for transparency) from 10 source datasets into a single frame-aligned schema covering RGB, metric camera pose/intrinsics, captions, quality metadata, and provenance.
- A backbone-native adaptation framework that adapts three different pretrained video generator families (Wan2.2, LTX-2.5, MiniMax-H3) into causal world models while preserving each backbone's native representations/objectives, rather than forcing one architecture.
- Four released model variants (5B to 33B parameters) demonstrating that the same data/recipe generalizes across backbone families, with real-time interactive rollouts extending far beyond the 5-second training horizon.
- Full open release of data, pipeline, training recipes, and weights, aimed at making long-horizon interactive video world model research reproducible rather than locked behind proprietary data pipelines (as with Cosmos, GAIA, etc.).

## Strengths

- The emphasis on data engineering (schema normalization, camera-pose annotation, explicit rejection tracking) addresses a major bottleneck in this field that is usually glossed over in favor of architecture novelty.
- Demonstrating backbone-agnostic adaptation across three different underlying video model families is a meaningfully broader generalization claim than typical single-backbone WAM papers.
- Training on only 5-second clips but achieving stable minutes-to-hours rollouts, if it holds up, is a strong result on the long-horizon consistency problem that plagues most video world models.
- Full openness (data + code + weights) is unusually complete for infrastructure at this scale and lowers the barrier for downstream robotics groups to build task-specific world models without redoing the data pipeline.

## Weaknesses

- As with any long-horizon video generation claim, "stable" hour-long rollouts likely still accumulate drift/hallucination over time; the paper's own qualitative claims should be treated cautiously pending independent replication.
- The corpus of 10 source datasets, however large, still reflects existing internet/robotics video distribution biases; coverage of contact-rich manipulation or dexterous-hand interaction (as opposed to broader "world" video) is unclear from available descriptions.
- This is a general video-world-model release rather than a robotics-specific action-conditioned model — its direct utility for robot policy learning depends on follow-up work adapting it into an action-conditioned WAM.

## Open Questions

- How does SolarWM's long-horizon consistency compare quantitatively (not just qualitatively) against Cosmos, GAIA-4, and other proprietary long-horizon world models?
- Can the released data engine and adaptation recipe be applied to robot-specific action-conditioned backbones to produce a WAM comparable to OpenWAM or similar contemporaneous work?
- What is the actual inference cost/latency of the 33B variant for real-time interactive use, and is the "real-time" claim achievable outside a data-center GPU setup?

## Significance

SolarWM's contribution is less a single new architecture and more a badly-needed open, reproducible data-and-training foundation for long-horizon video world models — a resource that many of the narrower WAM/robotics papers in this space currently lack and often build on ad hoc, proprietary data instead.

## Links

- [Paper](https://arxiv.org/abs/2609.02886)
- [GitHub](https://github.com/Junchao-cs/SolarWM)
