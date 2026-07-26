---
title: "Supervise What Survives: Geometry-Guided VLA Adaptation from Synthetic Robot Videos"
date: 2026-06-24
topic: VLA
tags: [vla-posttraining, synthetic-data, video-generation, data-augmentation, representation-learning, Show-Lab, NUS]
source: https://arxiv.org/abs/2606.24448
venue: "arXiv"
---

## Summary

This paper, from Show Lab at the National University of Singapore, argues that the common practice of extracting pseudo-actions from generated human-to-robot videos is a mismatched abstraction: video generation preserves the visible spatial geometry of a demonstration ("where") but does not reliably preserve the underlying control signal ("how"), so treating synthesized pixels as if they were real teleoperated action labels introduces systematic error. The authors propose GRA (Geometry-guided Representation Alignment), which instead extracts future 2D end-effector waypoints from synthetic video via pose estimation, retargeting, simulation, and calibrated projection, and uses these waypoints purely as auxiliary supervision for the VLA's vision backbone through a separate 2D head, while the action head is trained exclusively on real demonstrations.

## Key Contributions

- Diagnoses a specific failure mode in synthetic-video-for-robot-learning pipelines: generated human-to-robot videos preserve geometric/spatial content but not the precise control signals needed for accurate pseudo-action extraction, making pseudo-action regression from generated pixels an unreliable supervision source
- Proposes GRA, which reroutes synthetic video's useful signal (future 2D end-effector waypoints, derived through pose estimation, retargeting, simulation, and calibrated projection) into an auxiliary loss on the vision backbone rather than into direct action supervision
- Keeps the action head trained only on real teleoperated demonstrations, cleanly separating "what synthetic video can teach" (geometric/spatial grounding) from "what only real data can teach" (precise control)
- Shows the waypoint-alignment loss acts as a persistent spatial grounding anchor during fine-tuning, preventing the vision backbone from drifting away from geometric understanding
- Validates on a 7-DoF Franka Research 3 across three real tabletop pick-and-place tasks (cube-to-pad, cup-to-coaster, mango-to-plate), each with 25 real teleoperated trajectories plus 75 generated videos per task (30 evaluation trials each), outperforming pseudo-action baselines under matched data budgets and narrowing the gap to policies trained with substantially more real demonstrations

## Strengths

- Identifies a conceptually clean and underappreciated distinction (geometry vs. control survives generation) that reframes how synthetic video should be used for VLA training, rather than just proposing another video-generation pipeline
- Directly compares against pseudo-action extraction baselines under matched data budgets, isolating the effect of the auxiliary-supervision design choice rather than conflating it with more data or a better generator
- Keeping the action head real-data-only is a conservative, defensible design that avoids compounding generation artifacts directly into control outputs
- Demonstrates real, non-trivial narrowing of the gap to models trained on substantially more real demonstrations, suggesting the method meaningfully improves real-data efficiency

## Weaknesses

- Evaluation is limited to a single robot embodiment (Franka Research 3), a single fixed third-person camera, and three tabletop pick-and-place tasks — all visually and structurally similar, so it's unclear how well the geometry-alignment idea generalizes to more diverse manipulation (deformable objects, tool use, bimanual coordination, dynamic tasks)
- The waypoint extraction pipeline itself (pose estimation, retargeting, simulation, calibrated projection) is a multi-stage process with its own error sources; the paper does not deeply characterize how errors or noise in this pipeline propagate into the auxiliary supervision signal
- Only 25 real demonstrations and 75 generated videos per task were used — a fairly small-scale evaluation regime, so the claimed data-efficiency gains are not yet shown to hold at larger real-data budgets or across more tasks per category
- Because the waypoints are 2D end-effector projections, the auxiliary signal discards 3D depth/contact information; the paper does not analyze whether tasks with more depth-dependent precision (e.g., fine insertion or stacking) would benefit or be limited by a purely 2D geometric anchor

## Open Questions

- How does GRA's auxiliary 2D-waypoint supervision compare against directly using 3D trajectory or depth-aware geometric signals extracted from the same synthetic videos?
- Does the geometry/control distinction generalize to other synthetic data modalities beyond human-to-robot video generation, e.g., purely simulated rollouts or cross-embodiment video?
- How sensitive is GRA to the quality of the underlying video generator — would a much weaker or much stronger generator change the balance between "useful geometric signal" and "harmful synthetic artifacts"?
- Would scaling the ratio of real to generated data change the current findings, or does the auxiliary-supervision benefit saturate quickly?

## Significance

The paper offers a useful conceptual correction for the growing body of work that uses generative video models as a source of robot training data: rather than treating synthetic video as a free source of pseudo-actions, it should be used for what it reliably preserves (geometry), while control still needs to come from real demonstrations — a distinction likely to influence how future synthetic-data-for-VLA pipelines are designed.

## Links

- [Paper](https://arxiv.org/abs/2606.24448)
