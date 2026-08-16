---
title: "Skild Brain 1.0: An Omni-Bodied Robot Foundation Model"
date: 2026-05-20
topic: Humanoid
tags: [humanoid, foundation-model, cross-embodiment, industry, blog]
source: https://www.skild.ai/blogs/building-the-general-purpose-robotic-brain
venue: "blog (Skild AI)"
---

## Summary

Skild AI's flagship "omni-bodied" foundation model: a single, very large network reportedly trained across roughly 10,000 robots spanning about 200 hardware platforms (quadrupeds, humanoids, tabletop arms, mobile manipulators), designed to control a robot it has never seen before after a short (~15-second) calibration pass, without per-platform fine-tuning. Field testing was described in outdoor humanoid deployments in Pittsburgh, reportedly reaching 60-80% task success within hours of on-robot data collection. This is the vault's first logged entry on Skild AI.

## Key Contributions

- A single-network omni-bodied control claim spanning humanoid and non-humanoid form factors from one policy.
- Rapid (~15-second) zero-shot calibration to new hardware.
- A large claimed real-world robot/platform training diversity (~10,000 robots, ~200 platforms).

## Strengths

- If the cross-embodiment generalization claim holds, this is a significant scaling result relevant to humanoid generalist-policy research.
- Real outdoor humanoid deployment testing goes beyond typical lab benchmarks.

## Weaknesses

- This is company marketing content, not a peer-reviewed paper or technical report — no architecture paper, ablations, or independently verifiable benchmark numbers were found.
- Parameter count and training-robot-count figures come from secondary press coverage rather than a primary technical document.
- Independent scrutiny of Skild's public claims has reportedly been raised elsewhere (e.g. discrepancies noted by outside coverage).

## Open Questions

- Is there an accompanying technical report or paper with benchmarks comparable to GR00T, π0, or Helix?
- What is the humanoid-specific subset of results versus quadruped/arm results?
- What data mixture and training compute were actually used?

## Significance

Fills a real gap in this vault's coverage — Skild AI's flagship cross-embodiment model had not previously been logged despite being one of the most heavily funded generalist-robotics efforts in the field.

## Links

- [Blog](https://www.skild.ai/blogs/building-the-general-purpose-robotic-brain)
