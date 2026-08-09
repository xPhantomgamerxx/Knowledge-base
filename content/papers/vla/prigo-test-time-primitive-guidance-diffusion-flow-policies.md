---
title: "PriGo: Test-Time Primitive Guidance to Diffusion and Flow Policies for Adaptive Robotic Manipulation"
date: 2026-07-07
topic: VLA
tags: [vla, test-time-adaptation, diffusion-policy, flow-matching, vla-posttraining]
source: https://arxiv.org/abs/2607.07076
venue: "arXiv"
---

## Summary

PriGo introduces PANet, a lightweight primitive classifier, paired with a differentiable test-time guidance mechanism that steers pretrained diffusion and flow-matching policies toward semantically consistent action primitives without any retraining. It is evaluated across LIBERO, CALVIN, SIMPLER, and real-robot settings, targeting the common failure mode where generative policies produce locally plausible but semantically wrong actions (e.g., reaching the wrong object).

## Key Contributions

- A lightweight auxiliary classifier (PANet) trained to recognize which motion primitive a partially-denoised action sample corresponds to.
- A differentiable guidance signal derived from PANet that is injected into the diffusion/flow sampling process at inference time, nudging the trajectory toward the intended primitive.
- Demonstrated compatibility with both diffusion-policy and flow-matching action heads without modifying the base policy's weights.

## Strengths

- Test-time-only intervention means it can, in principle, be bolted onto any existing diffusion/flow VLA checkpoint without retraining cost — an attractive property for practitioners with fixed pretrained policies.
- Evaluation spans both simulation benchmarks (LIBERO, CALVIN, SIMPLER) and real robots, which is a meaningfully broader test than simulation alone.

## Weaknesses

- Guidance-based steering methods (classifier guidance, in the diffusion-model literature) are known to trade off sample diversity and can push the policy off-distribution if the guidance signal is miscalibrated; how PriGo avoids this at long horizons isn't clear from the available description.
- The primitive classifier PANet itself needs primitive-labeled training data, which reintroduces a data/annotation dependency the method's "training-free at test time" framing partially obscures — it is training-free for the base policy, not training-free overall.

## Open Questions

- How does PANet's primitive vocabulary generalize to tasks/primitives not seen during its own training?
- What is the computational overhead of the guidance step at inference, and is it compatible with real-time control loops?
- How does performance degrade as the number of candidate primitives grows toward open-vocabulary manipulation?

## Significance

PriGo is one of several 2026 papers converging on test-time guidance as a cheaper alternative to full RL or supervised fine-tuning for correcting VLA failure modes — relevant to the field's broader push toward inference-time compute as a lever for robot policy improvement.

## Links

- [Paper](https://arxiv.org/abs/2607.07076)
