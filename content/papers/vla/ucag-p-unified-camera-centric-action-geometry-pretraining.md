---
title: "One Policy, Many Embodiments: Unified Camera-Centric Action Geometry Pre-training for Heterogeneous Embodied Manipulation"
date: 2026-08-26
topic: VLA
tags: [cross-embodiment, action-representation, pretraining, generalist-policy, xiaomi]
source: https://arxiv.org/abs/2608.26058
venue: "arXiv (Xiaomi)"
---

## Summary

UCAG-P proposes a camera-centric unified action formulation that structurally aligns heterogeneous embodied datasets — spanning different robot morphologies, camera configurations, and low-level action spaces — into a shared geometric action space, rather than relying on explicit action retargeting, human-to-robot video synthesis, or dataset-specific adaptation branches as prior cross-embodiment methods do. A geometry-conditioned action translator then combines the predicted (embodiment-agnostic) motion with target-embodiment kinematics to produce executable low-level controls.

## Key Contributions

- Reformulates the cross-embodiment action representation problem around the camera's geometric frame rather than robot-specific joint/end-effector spaces, allowing a shared policy backbone to learn transferable manipulation geometry independent of the specific robot executing it.
- A decoupled architecture: a shared VLA policy learns embodiment-agnostic motion in the unified camera-centric space, while a separate geometry-conditioned action translator maps that motion into embodiment-specific executable controls using each robot's kinematics — avoiding the need for per-dataset adaptation branches.
- Trained on a very large heterogeneous corpus: 4.03K hours of robot and simulation data plus 2.34K hours of human demonstration data, showing the formulation scales to mixing human video data with multi-robot data in one pretraining pipeline.
- Strong zero-shot, single-checkpoint cross-benchmark results without benchmark-specific fine-tuning: 98.3% on LIBERO, 88.7%/89.2% on RoboTwin Easy/Hard, 82.0% zero-shot on LIBERO-Plus, and 62.0% on RoboCasa GR-1.

## Strengths

- Achieving strong scores across four quite different benchmarks (LIBERO, RoboTwin, LIBERO-Plus zero-shot, RoboCasa) from a single checkpoint without benchmark-specific fine-tuning is a meaningfully stronger generalization claim than most cross-embodiment papers, which typically fine-tune per benchmark.
- Incorporating both robot/sim data (4.03K hours) and human demonstration video (2.34K hours) into one unified geometric action space is a substantive step toward using the much larger pool of human video data to improve robot policies without bespoke retargeting pipelines per dataset.
- The decoupled shared-policy / embodiment-specific-translator architecture is a clean way to separate "what motion should happen" from "how does this particular robot execute it," which should make adding new embodiments cheaper than retraining the whole backbone.

## Weaknesses

- Camera-centric action representations are inherently dependent on accurate camera calibration/pose estimation; performance may be sensitive to camera placement variation or calibration error at deployment, a factor not obviously stress-tested in the reported benchmark numbers.
- Human demonstration data (2.34K hours) presumably requires some hand-pose/motion extraction pipeline to fit the camera-centric geometric format — the fidelity and error characteristics of that extraction pipeline (and how errors there propagate into the shared representation) aren't detailed here.
- All four evaluation benchmarks (LIBERO family, RoboTwin, RoboCasa) are simulation-based; the paper's real-world deployment validation, if any, isn't reflected in the search results, leaving open how well the camera-centric geometric abstraction survives real-world sensing noise and dynamics.

## Open Questions

- How robust is the geometry-conditioned action translator to camera pose errors or unconventional camera placements not seen during training?
- Does the unified camera-centric formulation extend cleanly to embodiments with very different actuation (e.g., dexterous multi-fingered hands vs. parallel grippers), or does the translator's kinematic conditioning become a bottleneck there?
- What real-world (non-simulation) results exist for UCAG-P, and how do they compare to the strong simulated cross-benchmark numbers?

## Significance

UCAG-P offers a structurally different answer to the cross-embodiment scaling problem than the dominant action-retargeting or per-dataset-adapter approaches, using camera geometry as the common currency across robots and even human video — a single-checkpoint, no-fine-tuning result across four benchmarks is a strong signal for this approach's promise in the "one policy, many embodiments" pursuit central to generalist robot learning.

## Links

- [Paper](https://arxiv.org/abs/2608.26058)
- [Project Page](https://public-bots.github.io/UCAG-P/)
