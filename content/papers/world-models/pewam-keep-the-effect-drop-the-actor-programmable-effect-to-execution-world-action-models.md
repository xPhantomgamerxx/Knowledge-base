---
title: "Keep the Effect, Drop the Actor: Programmable Effect-to-Execution World-Action Models (PEWAM)"
date: 2026-10-01
topic: WorldModels
tags: [world-models, robotics, cross-embodiment, object-centric, in-context-learning, data-efficiency]
source: https://arxiv.org/abs/2610.02398
venue: "arXiv"
---

## Summary

PEWAM proposes conditioning robot learning on what changed in the scene — the "effect" of a demonstration — rather than on the demonstrator's specific arm trajectory. Each demonstration is compiled into an "effect program" holding the tracked 3D keypoints of objects that moved, the contact points where each object was held, and the final scene configuration, while deliberately discarding the demonstrating arm's own motion. A compact 71.5M-parameter world-action model then generates the effect, robot execution, action, and terminal state as four coupled output streams.

## Key Contributions

- "Effect program" representation that strips out embodiment-specific arm motion entirely, keeping only object-centric, embodiment-agnostic change descriptions as the conditioning signal
- A small (71.5M parameter) world-action model that jointly generates effect, execution, action, and terminal state from a single effect program, rather than needing a separate planner and low-level controller
- Demonstrates the same compiled program running unmodified across four different robot arms with no retraining
- On held-out LIBERO-Goal tasks, one demonstration's compiled program completes 40 of 90 episodes vs. at most 19 for goal-image, language-conditioned, and demonstration-conditioned baselines; on a Franka arm, programs compiled from single human videos complete 36 of 40 trials vs. 22 for a last-frame-conditioned baseline with the same backbone

## Strengths

- Deliberately discarding arm-motion information is a strong, falsifiable design bet against the dominant trend of conditioning on raw action/motion trajectories, and the reported numbers support that bet for cross-embodiment transfer
- Very small model size (71.5M parameters) relative to most WAMs in this space, suggesting the effect-centric representation may be substantially more parameter-efficient
- Strong one-shot, cross-embodiment, and human-video-to-robot transfer numbers against relevant published baselines
- Zero-retraining execution across four robot arms is a direct, practical demonstration of embodiment-agnosticity, not just a theoretical claim

## Weaknesses

- Reported wins are mixed: it exceeds published results on three of five Meta-World task classes but not on the five-class mean, suggesting the approach may not uniformly dominate
- No code or model weights are released at the project page, only the paper and a supplementary video, which limits independent verification and reuse
- Object-centric effect tracking (3D keypoints, contact points) likely requires reliable perception/tracking infrastructure that could be brittle for deformable, articulated, or heavily occluded objects not evaluated here

## Open Questions

- How robust is the effect-program extraction to perception noise, occlusion, or deformable/articulated objects where "tracked 3D keypoints" are harder to define?
- Does discarding arm motion entirely lose information that matters for tasks where *how* an object is manipulated (not just the end state) is safety- or task-critical (e.g., avoiding collisions mid-trajectory)?
- Why does the approach underperform on the Meta-World five-class mean despite winning on three individual classes — is there a systematic weakness on certain task types?

## Significance

A compact counter-example to the trend of ever-larger generative world-action models: by conditioning purely on object-centric effects and discarding embodiment-specific motion, a much smaller model achieves strong one-shot and cross-embodiment transfer, offering a data- and parameter-efficient alternative design point for the field.

## Links

- [Paper](https://arxiv.org/abs/2610.02398)
- [Project Page](https://junyi2005.github.io/pewam)
