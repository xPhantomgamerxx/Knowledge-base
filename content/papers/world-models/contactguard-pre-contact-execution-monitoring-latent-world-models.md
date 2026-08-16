---
title: "ContactGuard: Pre-Contact Execution Monitoring with Action-Conditioned Latent World Models"
date: 2026-08-13
topic: WorldModels
tags: [world-models, execution-monitoring, safety, contact-rich-manipulation, latent-world-model]
source: https://arxiv.org/abs/2608.13438
venue: "arXiv"
---

## Summary

ContactGuard proposes using an action-conditioned latent world model as an online execution monitor specifically for the pre-contact phase of manipulation — the moments before the end-effector touches an object, where failures like misalignment or premature/incorrect contact are hard to catch with standard policy rollouts. The world model predicts latent future states conditioned on candidate actions and flags likely failure trajectories before physical contact occurs, functioning as a safety/verification layer rather than a policy itself.

## Key Contributions

- Repurposes a latent world model specifically for pre-contact failure monitoring, rather than full trajectory prediction or policy rollout.
- Action-conditioning to anticipate contact-relevant failure modes ahead of physical interaction.
- An evaluation spanning multiple contact-rich manipulation scenarios.

## Strengths

- Fills a specific niche — pre-contact failure detection — distinct from this vault's existing world-model-as-simulator or world-model-as-policy work.
- The safety/verification framing complements existing post-training correction methods (TACO, VLA-Corrector) already logged.
- Targets contact-rich manipulation, an underserved failure mode in prior coverage.

## Weaknesses

- Baseline comparisons, false-positive/negative rates, and real-robot validation could not be confirmed from available sources.
- Compute overhead of running a latent world model as an online monitor alongside the policy is unclear.

## Open Questions

- Does monitoring generalize to unseen contact types/materials?
- What is the intervention policy once a failure is flagged — abort, replan, or human handoff?
- How does it compare to existing execution-monitoring approaches already in the vault?

## Significance

A safety-oriented use of world models that complements the dominant "world model as simulator/policy" framing with a verification-layer role during deployment.

## Links

- [Paper](https://arxiv.org/abs/2608.13438)
