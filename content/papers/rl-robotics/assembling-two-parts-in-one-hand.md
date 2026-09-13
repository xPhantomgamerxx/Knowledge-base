---
title: "Assembling Two Parts in One Hand"
date: 2026-09-09
topic: RL-Robotics
tags: [dexterous-manipulation, sim-to-real, in-hand-manipulation, reward-shaping, CoRL2026]
source: https://arxiv.org/abs/2609.10137
venue: "CoRL 2026 / arXiv"
---

## Summary

This paper introduces "in-hand assembly": mating two rigid parts entirely within a single dexterous hand, with no second arm, external fixture, or vise to hold either piece. The authors frame the task as reinforcement learning with a goal-reaching reward on the relative pose between the two parts, and show zero-shot sim-to-real transfer to a real 22-DoF hand using only a single RGB-D camera.

## Key Contributions

- Formulates in-hand assembly as an RL problem whose objective is a target relative pose between two held parts, rather than a scripted or model-based assembly pipeline
- Multiplicative finger-function reward that partitions the hand into two coordinated functional roles: thumb + index finger manipulate one part while middle, ring, and little fingers cage/stabilize the other
- Human reference snapshot initialization to bootstrap plausible bimanual-in-one-hand finger coordination and avoid degenerate exploration
- Policies trained entirely in IsaacGym/PhysX-style simulation and deployed zero-shot to real hardware
- Real-world validation on three tasks (Bottle, Syringe, Marker) with 15/20, 17/20, and 16/20 success rates respectively

## Strengths

- Tackles a genuinely under-explored manipulation regime — prior assembly work almost always assumes a second arm, a fixture, or a table to brace one part, whereas this removes all external support
- The finger-role partitioning reward is a simple, interpretable shaping mechanism that appears to be the key enabler of coordination, rather than relying on brute-force exploration
- Real hardware validation across three distinct object geometries (rather than a single demo task) with quantitative trial-by-trial success rates
- Honest reporting of a specific simulation-fidelity failure mode (see Weaknesses) rather than only showing successes

## Weaknesses

- Success rates (75-85%) still leave a substantial real-world failure rate for what is framed as a foundational capability
- The authors themselves identify that PhysX cannot model planar patch contacts, causing pinch grasps to degenerate to two contact points in simulation; this directly causes real-world failures when an object's long axis starts near horizontal — a known sim-to-real gap baked into the physics engine, not just perception or domain randomization
- Only three object pairs/tasks are demonstrated; generalization to more diverse part geometries, tolerances, and truly novel assemblies (not seen during training) is untested
- No comparison against a fixture-assisted or dual-arm assembly baseline to quantify how much harder single-hand assembly actually is in success-rate terms

## Open Questions

- Would richer contact modeling (e.g., differentiable or soft-contact simulators) close the pinch-grasp sim-to-real gap the authors identify, or is this a more fundamental limitation of rigid-body simulators for this task class?
- Can the finger-role reward decomposition generalize automatically to hands with different morphologies (fewer/more fingers) or does it require task-specific hand-partitioning design each time?
- How does this scale to assemblies requiring more than two parts, or parts with tight tolerances where a few millimeters of error causes failure?

## Significance

In-hand assembly without external fixturing is a capability that has been largely absent from the dexterous manipulation literature, which typically assumes a table, vise, or second arm to constrain one part. This work is a concrete step toward humanoid or single-arm robots performing fine assembly tasks in unstructured settings where no fixture is available, and its explicit finger-role reward design offers a reusable shaping strategy for other bimanual-within-one-hand coordination problems.

## Links

- [Paper](https://arxiv.org/abs/2609.10137)
