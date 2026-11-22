---
title: "AGIBOT GO-3 Preview: A World Reasoning Action Model for Humanoids"
date: 2026-10-29
topic: Humanoid
tags: [humanoid, foundation-model, world-action-model, china, benchmark]
source: https://roboticsandautomationnews.com/2026/11/05/agibot-unveils-go-3-preview-and-takes-top-spot-on-three-embodied-ai-benchmarks/106711/
venue: "blog / Innovation Day 2026 (Shanghai)"
---

## Summary

AGIBOT debuted GO-3 Preview, a next-generation embodied foundation model, at its Innovation Day 2026 event in Shanghai on October 29. The model is built on a "World Reasoning Action Model" (WRAM) framework intended to unify task reasoning, outcome prediction, and action generation in one architecture, and AGIBOT claims top rankings on three embodied AI benchmarks (RoboDojo, RoboTwin, RoboColiseum).

## Key Contributions

- A single WRAM-style architecture that couples a reasoning/outcome-prediction module with action generation, rather than bolting a separate VLA head onto a world model.
- Training reportedly spans human videos, real robot data, simulation, and post-deployment practice — an attempt at a full real/sim/human data pyramid in one pipeline.
- A stated commitment to fully open-source the model by the end of 2026, continuing AGIBOT's pattern (AgiBot World dataset, GO-1) of releasing large embodied-AI assets.

## Strengths

- Benchmark-first framing against three named leaderboards gives at least a nominal comparison point, unlike many announcement-only releases.
- Open-sourcing commitment, if honored, would make this one of the larger fully open humanoid WRAM-class models to date.
- Builds on AGIBOT's existing large-scale AgiBot World data infrastructure rather than starting from scratch.

## Weaknesses

- All benchmark claims (top-3 rankings, ~85% real-world trial success rate circulating in press coverage) are self-reported by AGIBOT with no published methodology, held-out protocol, or third-party verification at announcement time.
- No technical report, architecture diagram, or ablations are available yet — the "WRAM" terminology is asserted but not substantiated in public materials.
- Coverage is dominated by secondary Chinese-tech and press-release outlets; no primary paper or model card was found at the time of this note.

## Open Questions

- Will the promised open-source release (expected by end of 2026) include weights, training data, and benchmark harnesses, or only a subset?
- How does WRAM's reasoning-prediction-action coupling compare quantitatively to existing WAM-style architectures already in this vault (e.g. GeoSem-WAM, AHA-WAM) on the same tasks?
- Are RoboDojo/RoboTwin/RoboColiseum independently run, or are they benchmarks AGIBOT itself curates/controls?

## Significance

If the open-source release materializes, GO-3 would add another large, fully-open world-reasoning-action model to the humanoid ecosystem alongside AgiBot's existing datasets — but until a technical report lands, this is best treated as a credible announcement rather than a verified result.

## Links

- [Robotics and Automation News coverage](https://roboticsandautomationnews.com/2026/11/05/agibot-unveils-go-3-preview-and-takes-top-spot-on-three-embodied-ai-benchmarks/106711/)
- [TechNode Global coverage](https://technode.global/)
