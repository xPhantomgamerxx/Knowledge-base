---
title: "NVIDIA Releases Four Open Cosmos 3 Checkpoints for Robot and AV World Simulation"
date: 2026-11-05
tags: [world-models, nvidia, cosmos, open-weights, sim-to-real]
source: https://developer.nvidia.com/blog/develop-physical-ai-reasoning-world-and-action-models-with-nvidia-cosmos-3
venue: "blog"
topic: WorldModels
---

## Summary

NVIDIA published four open-weight checkpoints post-trained from Cosmos 3 Nano (16B params each, OpenMDW 1.1 license): Sim-Auto and Sim-Transfer for driving/AV simulation, and Sim-Bimanual for robotics, which generates the next visual observation directly from a bimanual robot's actions (demonstrated with YAM and AgiBot arm setups). This extends the June 2026 Cosmos 3 base release with task-specific, deployable simulation checkpoints.

## Key Contributions

- Sim-Bimanual: an action-conditioned video model that predicts the next observation from bimanual robot actions for interactive two-arm simulation.
- Sim-Auto: a causally-distilled, streaming variant of Transfer-Auto that generates short video/LiDAR chunks in a few denoising steps for near-real-time driving simulation.
- Open release under OpenMDW 1.1 alongside cookbook examples for pairing the checkpoints with policy/control loops.

## Strengths

- Open weights and a permissive license lower the barrier for labs without access to large proprietary world models to experiment with action-conditioned simulation.
- Distillation to fewer denoising steps (Sim-Auto) is a concrete step toward making world-model rollouts fast enough for iterative use rather than offline-only generation.
- Concrete hardware targets (YAM, AgiBot bimanual arms) ground the release in actual robot platforms rather than abstract benchmarks.

## Weaknesses

- The released cookbook examples for Sim-Bimanual run open-loop only; closed-loop use (feeding generated frames back into a policy) is left as an exercise for the user, so the "interactive simulation" framing is partly aspirational at release time.
- No independent benchmark numbers (e.g., sim-to-real transfer success rate, prediction fidelity vs. competitors like Cosmos-Predict2, Genie 4, or GR00T Dreams) accompanied the release — coverage is secondary/press-based, not a technical report with quantitative claims.
- Unclear how Sim-Bimanual's action-to-observation generation handles distribution shift away from the YAM/AgiBot training setups to other embodiments.

## Open Questions

- What is the actual rollout fidelity and physical consistency of Sim-Bimanual compared to dedicated manipulation world models (e.g., WEAVER, τ0-WM)?
- Will NVIDIA release a technical report with quantitative sim-to-real or policy-evaluation results, as it did for the Cosmos 3 base model?
- How does Sim-Auto's distillation-induced speed/quality trade-off affect downstream use for RL or MPC compared to the full Transfer-Auto model?

## Significance

Continues NVIDIA's strategy of commoditizing world-foundation-model infrastructure for physical AI (following Cosmos 3's June 2026 launch), pushing action-conditioned simulation checkpoints specifically toward bimanual manipulation hardware that labs can plug into existing Isaac/GR00T pipelines.

## Links

- [NVIDIA Developer Blog](https://developer.nvidia.com/blog/develop-physical-ai-reasoning-world-and-action-models-with-nvidia-cosmos-3)
