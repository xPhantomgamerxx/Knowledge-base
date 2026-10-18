---
title: "Splat2Act: From Captured Scenes to Personalized VLA Manipulation"
date: 2026-10-09
topic: VLA
tags: [vla, personalization, gaussian-splatting, real2sim2real, synthetic-data, vla-posttraining]
source: https://arxiv.org/abs/2610.13945
venue: "arXiv"
---

## Summary

Splat2Act is a real-to-sim-to-real pipeline that personalizes a generalist π0.5 VLA policy to a specific user's home. It builds a 3D Gaussian Splatting digital twin of a building-scale indoor scene from a phone scan, auto-generates pickup tasks against the reconstructed geometry, and uses a privileged simulation oracle to synthesize demonstrations for fine-tuning — all without a human teleoperating a real robot in the target scene.

## Key Contributions

- A two-stage personalization recipe: stage one fine-tunes on public object assets, stage two personalizes to the user's own captured objects and receptacles in the target scene.
- An automatic affordance/receptacle-finding pipeline over the Gaussian-Splat twin that turns a raw scene capture into a large pool of synthetic pickup tasks with privileged-oracle demonstrations.
- Real-robot validation on a Stretch 3, closing the sim-to-real gap for a genuinely unseen home environment rather than a lab-captured scene.

## Strengths

- The baseline number is a strong motivator: unadapted π0.5 gets 0% pickup success in the captured deployment scenes, so the paper is solving a real deployment failure mode, not a marginal benchmark gain.
- Real-robot numbers (63.9% on a 12-task subset) track closely with simulated numbers (66.7%) on the same tasks, suggesting the Gaussian-Splat twin is a reasonably faithful visual/geometric proxy for sim-to-real transfer here.
- The capture burden on the end user is low (a phone scan plus object images), which is the right UX target for any "personalize my home robot" pipeline.

## Weaknesses

- 62.5% aggregate pickup success after personalization is still well short of reliable deployment; the paper is a proof that personalization helps, not that the resulting policy is production-ready.
- The privileged simulation oracle that generates demonstrations is doing a lot of the heavy lifting — its own failure modes (e.g., on deformable or highly reflective objects that splat poorly) aren't deeply characterized.
- Evaluated on pickup tasks specifically; it's unclear how the approach extends to longer-horizon or contact-rich manipulation where Gaussian-Splat geometry is a worse proxy for true collision/contact physics.

## Open Questions

- How does personalization quality degrade as scene capture quality drops (e.g., a quick, low-coverage phone scan vs. a careful multi-minute capture)?
- Could the same pipeline be used incrementally — i.e., re-personalizing as the household's object inventory changes — without full re-capture?
- How much of the gain comes from the Splat-based visual domain match vs. simply having more in-distribution object/receptacle demonstrations?

## Significance

This is a concrete instance of the "synthetic data generation for VLA post-training" pattern applied to the hardest deployment case — an arbitrary, previously-unseen home — rather than a curated lab environment, and it reports the 0%-to-62.5% jump that makes the case for scene-specific personalization pipelines over purely generalist policies.

## Links

- [Paper](https://arxiv.org/abs/2610.13945)
