---
title: "LEGS: Fine-Tuning Teleop-Free VLAs for Humanoid Loco-manipulation in an Embodied Gaussian Splatting World"
date: 2026-05-31
topic: Humanoid
tags: [vla-posttraining, gaussian-splatting, sim-to-real, teleop-free, humanoid-manipulation, unitree-g1, synthetic-data]
source: https://arxiv.org/abs/2606.01458
venue: "arXiv"
---

## Summary

LEGS (Loco-manipulation via Embodied Gaussian Splatting) is a hybrid simulator from Stanford-affiliated authors that composites a mesh foreground (robot and manipulated objects) over a photorealistic 3D Gaussian Splatting (3DGS) background reconstructed from a single handheld scan of a real scene. Combined with a procedural motion-primitive generator that synthesizes labeled demonstrations without any human teleoperation, and a two-stage color-calibration step that matches rendered images to the deployment camera's photometric response, LEGS produces synthetic fine-tuning data for VLA policies that transfers zero-shot to a real Unitree G1 humanoid.

## Key Contributions

- A hybrid rendering pipeline that separates a dynamic mesh foreground (robot/props, which must be simulated physically) from a static photorealistic 3DGS background (which only needs to look correct), sidestepping the need to make Gaussian splats physically simulable
- A procedural motion-primitive generator that produces large volumes of labeled pick-and-place demonstrations entirely automatically, removing human teleoperators from the data-collection loop
- A deterministic two-stage color-calibration procedure that aligns the color/exposure response of rendered 3DGS frames to the specific deployment camera, explicitly targeting the visual sim-to-real gap rather than relying on domain randomization alone
- Empirical validation across three pick-and-place tasks of increasing whole-body difficulty and three different VLA backbones (ψ₀, π0.5, and GR00T N1.6) on a real Unitree G1, with policies fine-tuned purely on LEGS-generated data matching or beating policies fine-tuned on real teleoperated demonstrations in every tested configuration

## Strengths

- Because 3DGS backgrounds are optimized directly against real photographs of the target scene, the visual domain gap that typically plagues sim-to-real VLA transfer is reduced at the source rather than patched after the fact with randomization or augmentation
- Eliminating human teleoperation from the data pipeline is a direct attack on one of the most expensive and hard-to-scale bottlenecks in current VLA fine-tuning workflows
- Generality across three distinct VLA backbones (rather than tuning the pipeline to one model) is stronger evidence that the data-generation approach, not a lucky pairing with a specific policy architecture, is what drives the results
- Real-robot, whole-body humanoid evaluation (not just tabletop arm manipulation) is a meaningfully harder and less common testbed for sim-to-real VLA transfer

## Weaknesses

- Each 3DGS background comes from a single handheld scan of one physical scene, so the demonstrated transfer is validated on the specific environments captured — it is unclear how much re-scanning/re-calibration is needed per new deployment scene, and the paper does not report costs for scaling to many diverse environments
- Evaluation is limited to three pick-and-place task types; more complex, contact-rich, or long-horizon loco-manipulation behaviors are untested, so it is unclear whether the same photometric/motion-primitive recipe generalizes beyond pick-and-place
- The procedural motion-primitive generator's coverage is bounded by what its authors chose to hand-design; tasks requiring subtler or more varied motion strategies than the primitives encode may not be well represented in the synthetic data
- Static 3DGS backgrounds cannot represent dynamic scene changes (moving people, changing lighting, rearranged clutter) during deployment, which real environments routinely exhibit

## Open Questions

- How does data-generation and scanning cost scale as the number of distinct deployment scenes grows into the tens or hundreds needed for a generally deployable home/warehouse robot?
- Does the color-calibration step need to be repeated whenever cameras or lighting conditions change, and how sensitive is downstream policy performance to calibration drift?
- Can the motion-primitive generator be extended or learned (rather than hand-procedural) to cover more diverse manipulation skills beyond pick-and-place without reintroducing a human-labeling bottleneck?

## Significance

LEGS is a concrete data point showing that photorealistic neural-rendering-based simulation, paired with fully automated demonstration synthesis, can replace human teleoperation for VLA fine-tuning on real humanoid hardware — a result that, if it generalizes, would substantially cut the cost of scaling humanoid manipulation data collection.

## Links

- [Paper](https://arxiv.org/abs/2606.01458)
