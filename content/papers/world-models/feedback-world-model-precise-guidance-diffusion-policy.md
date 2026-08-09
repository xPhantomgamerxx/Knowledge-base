---
title: "Feedback World Model Enables Precise Guidance of Diffusion Policy"
date: 2026-05-20
topic: WorldModels
tags: [world-models, test-time-adaptation, diffusion-policy, vla-posttraining]
source: https://arxiv.org/abs/2605.15705
venue: "arXiv"
---

## Summary

This paper uses a world model for closed-loop test-time guidance of diffusion policies, rather than as a static open-loop predictor: real observations collected during execution correct the world model's latent predictive state online, and an "action-aware guidance" mechanism weights latent-prediction errors by controllability to steer the diffusion policy toward better actions.

## Key Contributions

- An online correction mechanism that updates the world model's latent state using real observations gathered mid-rollout, rather than relying purely on open-loop rollout predictions from the initial state.
- "Action-aware guidance" that weights prediction errors by how controllable the corresponding state dimensions are, focusing correction signal on aspects the policy can actually influence.
- No additional training data or parameter updates required — the mechanism operates entirely at test time on top of a pretrained diffusion policy and world model.

## Strengths

- Treating the world model as a closed-loop corrector rather than an open-loop simulator directly addresses a well-known failure mode of world-model-guided planning: compounding prediction error over long horizons. Grounding predictions in real observations as they arrive is a sound mitigation.
- Weighting guidance by controllability is a thoughtful detail — naively minimizing all latent prediction error can waste guidance capacity on uncontrollable nuisance variation (e.g., lighting, unrelated background motion).

## Weaknesses

- The method's benefit is capped by the base world model's predictive accuracy in the first place; if the world model has systematic biases (e.g., poor contact-dynamics modeling), online correction from sparse real observations may not fully compensate.
- No training or parameter updates also means the method can't fix fundamental capability gaps in the underlying diffusion policy — it's a guidance/steering mechanism, not a way to acquire new skills.

## Open Questions

- How much does the online correction step cost in terms of inference latency, and is it compatible with real-time control frequencies?
- How does performance scale with the frequency of real-observation correction (every step vs. periodic)?
- Does the controllability-weighting scheme require task-specific tuning, or does it transfer across task families without modification?

## Significance

A clean example of the 2026 trend toward using world models for test-time policy correction rather than only for training-time simulation or planning — directly relevant to the VLA/policy post-training priority theme this digest tracks, even though it's filed under world models architecturally.

## Links

- [Paper](https://arxiv.org/abs/2605.15705)
