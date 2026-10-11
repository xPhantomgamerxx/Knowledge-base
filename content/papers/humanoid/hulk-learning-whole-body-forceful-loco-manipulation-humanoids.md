---
title: "HULK: Learning Whole-Body Forceful Loco-Manipulation for Humanoids"
date: 2026-10-06
topic: Humanoid
tags: [humanoid, robotics, loco-manipulation, whole-body-control, reinforcement-learning, sim-to-real]
source: https://arxiv.org/abs/2610.08970
venue: "arXiv"
---

## Summary

HULK tackles the specific problem of carrying large, heavy objects with a humanoid's whole body, where the payload shifts the robot's center of mass and loads the upper body while it is still trying to walk and track commands. The authors train two MPC-guided RL specialist teachers — one for arm motions under wrist forces, one for walking while holding bulky objects against the torso — and distill both into a single deployable policy on a Unitree G1.

## Key Contributions

- A capture-point control barrier function that keeps the wrist-force teacher balanced while under sustained external load, rather than relying on reward shaping alone.
- Two specialist teachers (wrist-force tracking and torso-carry walking) trained separately via MPC-guided RL, then distilled into one whole-body policy.
- Real-world validation on a Unitree G1 carrying heavy objects (up to 10 kg per arm) with both simulation and hardware results.

## Strengths

- Reports concrete, falsifiable numbers: lowest velocity-tracking error at 10 kg/arm and a 35.7% reduction in an aggregate balance metric versus plain MPC-guided RL, plus withstanding 130 N torso pushes.
- Directly targets a practical, under-addressed failure mode (forceful carrying) rather than just locomotion or light manipulation, which is closer to real warehouse/logistics use cases.
- Teacher-distillation design lets the two sub-skills be optimized independently before being merged, which should ease debugging versus training one monolithic policy from scratch.

## Weaknesses

- Evaluated on a single platform (Unitree G1); unclear how well the capture-point CBF and distilled policy generalize to humanoids with different mass distributions or actuator limits.
- The reliance on two separately-trained teachers adds pipeline complexity and potential distillation gap versus an end-to-end approach.
- No discussion of how the method handles objects whose mass or grip point changes mid-task, or fully dynamic object hand-offs.

## Open Questions

- How does the approach scale to bimanual carrying of irregular or deformable objects rather than idealized held loads?
- Would the capture-point barrier formulation extend to recovery from slips or missteps while under load, not just steady-state balance?
- Can the teacher/distillation recipe be generalized into a reusable training template for other forceful whole-body skills (pushing, pulling, climbing with payload)?

## Significance

Forceful, payload-aware whole-body control is a persistent gap between humanoid demos and real logistics/industrial deployment, and HULK's explicit balance guarantees under load are a concrete step toward making humanoids reliable heavy-lifting collaborators rather than just light-object manipulators.

## Links

- [Paper](https://arxiv.org/abs/2610.08970)
