---
title: "Counterfactual Video Generation Enables Scalable Humanoid Loco-Manipulation"
date: 2026-09-30
topic: Humanoid
tags: [humanoid, synthetic-data, video-generation, real-to-sim-to-real, vla-posttraining]
source: https://arxiv.org/abs/2609.38172
venue: "CoRL 2026"
---

## Summary

PRISM is a real-to-sim-to-real pipeline that uses video-to-video (V2V) generation to expand a handful of real human-object interaction videos into hundreds of diverse "counterfactual" videos — interactions that didn't occur in the source footage but plausibly could have (different objects, geometries, configurations). From just four real-world videos of humans carrying boxes, PRISM generates 256 counterfactual videos depicting carrying boxes, balls, bins, and barrels of varying shapes. Reconstruction and retargeting from these videos yield physically plausible robot-object trajectories used to train a unified depth-based humanoid policy that picks up, carries, and drops diverse objects zero-shot in the real world.

## Key Contributions

- Uses generative video-to-video synthesis specifically to multiply a tiny set of real demonstrations into a much larger, more diverse training corpus, rather than requiring diverse real-world data collection directly
- Targets the specific practical barrier of collecting diverse interaction videos (full-body visibility, unoccluded object interaction) which is genuinely hard to source at scale
- Demonstrates zero-shot real-world deployment of a policy trained from the synthetically-expanded data, picking up/carrying/dropping multiple object categories

## Strengths

- Going from 4 real videos to 256 usable counterfactual training videos is a striking data-multiplication ratio, and if the generated videos are physically plausible, this directly attacks the data-scarcity bottleneck at its root
- CoRL 2026 acceptance lends some confidence that the physical plausibility and downstream utility claims held up under peer review
- Zero-shot generalization to carrying balls, bins, and barrels — object categories plausibly not identical to the box-carrying source videos — suggests genuine generalization rather than narrow memorization

## Weaknesses

- Relying on V2V generation to produce physically plausible interaction dynamics (not just visually plausible video) is a strong claim; generative video models are known to sometimes violate physical consistency (object permanence, contact dynamics), and the paper's reconstruction/retargeting step must correct for this, but the correction's limits aren't deeply explored
- Validated on a fairly constrained task family (carrying/picking/dropping rigid-ish objects); unclear how well the approach extends to more dexterous, contact-rich, or deformable-object interactions
- Starting from only 4 source videos risks the generated diversity still being bounded by the specific scene/lighting/viewpoint characteristics of those 4 originals, even if object identity varies

## Open Questions

- How does PRISM's data-multiplication approach compare directly against other counterfactual/synthetic-video methods (e.g., Ego2Robot, Learning Diverse Humanoid Tasks via Synthetic Video Scenarios) on shared evaluation tasks?
- What is the failure mode when the V2V model generates a physically implausible counterfactual (e.g., an object clipping through the humanoid) — how much does the reconstruction pipeline's correction capacity bound the usable diversity?

## Significance

A compelling, CoRL-vetted demonstration that generative video expansion can multiply scarce real humanoid interaction data by orders of magnitude while preserving real-world transfer — directly relevant to the high-priority VLA/humanoid data-augmentation theme.

## Links

- [Paper](https://arxiv.org/abs/2609.38172)
- [GitHub](https://github.com/amazon-far/PRISM)
- [Dataset](https://huggingface.co/datasets/Amazon-FAR/far-prism-data)
