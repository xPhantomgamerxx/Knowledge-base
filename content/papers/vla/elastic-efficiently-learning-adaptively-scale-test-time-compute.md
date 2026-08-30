---
title: "ELASTIC: Efficiently Learning to Adaptively Scale Test-Time Compute for Generative Control Policies"
date: 2026-06-30
topic: VLA
tags: [test-time-compute, diffusion-policy, reinforcement-learning, meta-mdp, vla-posttraining]
source: https://arxiv.org/abs/2606.31132
venue: "arXiv (CMU)"
---

## Summary

ELASTIC, from a CMU team (Andrew Zou Li, Gokul Swamy, Yonatan Bisk, Andrea Bajcsy), learns state-dependent test-time compute allocation for generative control policies (diffusion/flow-matching policies including π0.5), rather than using a fixed compute budget or scaling schedule. It formulates the choice between sequential compute (more denoising steps for finer action refinement) and parallel compute (sampling more candidate actions) as a meta-Markov Decision Process solved via reinforcement learning.

## Key Contributions

- Identifies that generative control policies expose two distinct, non-interchangeable axes of test-time compute — sequential (denoising steps) and parallel (candidate sampling) — and that their optimal allocation is state-, task-, and policy-dependent rather than fixed.
- Frames adaptive compute allocation itself as a meta-MDP and trains an RL policy to choose, per state, how much and which kind of test-time compute to spend (e.g., broader parallel exploration during early grasp approach vs. more sequential refinement during precision near-contact phases).
- Demonstrates Pareto-dominance over both fixed-budget baselines and single-axis scaling baselines (pure sequential or pure parallel) across simulated manipulation benchmarks with diffusion policies.
- On real-world robot manipulation, matches best-of-10 sampling success rate while cutting wall-clock latency by 34%, directly demonstrating a practical efficiency win, not just a quality win.

## Strengths

- Moves test-time compute scaling for robotics beyond one-size-fits-all schedules toward a principled, learned, state-conditioned allocation policy — conceptually mirrors adaptive-compute ideas from LLM inference-time scaling but grounded in the specific structure of generative control (sequential vs. parallel axes).
- The 34% latency reduction at matched success rate is a concrete, decision-relevant result for real-time robot deployment, where inference latency directly constrains control frequency.
- Validated on both simulated and real-world manipulation, and explicitly compatible with a widely-used flow-based VLA (π0.5), improving practical relevance.

## Weaknesses

- Learning the meta-MDP compute-allocation policy is itself an added training cost and additional model/component to maintain, which partially offsets the "efficiency" framing — the paper doesn't obviously address this training overhead relative to the inference savings gained.
- The meta-policy is learned relative to a specific base generative policy and task distribution; it is unclear how well a learned compute-allocation policy transfers to new tasks or a differently-trained base policy without retraining the meta-policy.
- Real-world validation results (latency reduction, matched best-of-10 success) appear to be reported on a limited task set typical of academic robot manipulation papers; broader task/embodiment diversity would strengthen generalization claims.

## Open Questions

- How does ELASTIC's meta-policy training cost scale with the size/diversity of the base policy's task distribution, and is it amortizable across many downstream tasks?
- Can the same meta-MDP framing extend to compute axes beyond denoising steps and candidate count (e.g., model size switching, early-exit decisions)?
- How robust is the learned allocation policy to shifts in inference hardware (different latency/throughput profiles), which would change the actual cost-benefit tradeoff underlying the RL-learned allocation?

## Significance

ELASTIC is a well-motivated instance of the broader trend of adaptive test-time compute scaling moving from language models into embodied/generative control policies, and its state-dependent, RL-learned allocation approach could become a standard technique for making diffusion/flow-based VLA policies both more accurate and faster where it matters most.

## Links

- [Paper](https://arxiv.org/abs/2606.31132)
