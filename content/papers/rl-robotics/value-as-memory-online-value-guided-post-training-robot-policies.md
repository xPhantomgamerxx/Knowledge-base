---
title: "Value as Memory (VaM): Online Value-Guided Post-training for General Robot Policies"
date: 2026-10-15
topic: RL-Robotics
tags: [rl-robotics, vla-posttraining, online-rl, value-function, human-in-the-loop]
source: https://arxiv.org/abs/2610.22368
venue: "arXiv"
---

## Summary

VaM is a post-training pipeline for general robot policies (Shanghai Jiao Tong University / Shanghai Innovation Institute) that feeds a learned value function back into the policy as a "value cache" — a running task-progress memory — to address partial observability and delayed reward during real-world RL. The pipeline moves through four stages: offline demonstrations, offline RL warmup, online DAgger-style human-intervention correction, and a final "Learn from Experience" (LfE) phase of autonomous rollouts scored only by sparse terminal rewards.

## Key Contributions

- Value caching: recent value estimates are injected into the policy's observation/context as a compact progress signal, rather than relying purely on instantaneous state.
- A staged online pipeline (offline demo → offline RL warmup → online DAgger → LfE) that transitions from human-corrected to fully autonomous data collection.
- Concurrent data collection and training claimed to give ~8x more policy iterations per gradient-step budget and >2x lower wall-clock time per step versus a non-concurrent schedule.
- An ablation isolating the value source (holding the action expert fixed, swapping only the value expert) to show the value estimate itself — not just the action policy — must be kept current.

## Strengths

- The value-source ablation is a genuinely useful diagnostic: it isolates whether gains come from better actions or better value estimates, which most online-RL-for-robots papers don't disentangle.
- Reported success-rate gains (~29–33 points absolute) on long-horizon, deformable/contact-rich tasks are large enough to be meaningful if they replicate, and the concurrent collection/training throughput claim addresses a real practical bottleneck in on-robot RL.

## Weaknesses

- No independently verifiable project page, code release, or venue confirmation was found; all corroboration came from secondary aggregators (papers.cool, alphaxiv) rather than the primary PDF, so specific numbers (e.g., a reported 76.7%→40.0% drop on a Magnetic Bus Assembly task) could not be cross-confirmed.
- Evaluated on only three tasks per the ablation; unclear how value-cache staleness interacts with longer deployment or distribution shift beyond the tested horizon.

## Open Questions

- Does the value cache's benefit hold on tasks with sparser or noisier terminal rewards than the ones tested, or does it specifically require the LfE autonomous-rollout stage to stay calibrated?
- How much of the throughput win is specific to their infrastructure (concurrent collection/training) versus the value-caching idea itself?

## Significance

Adds a concrete mechanism (value-as-memory) to the growing online-RL-post-training-of-generalist-policies literature, and its action-vs-value ablation is a useful methodological contribution for anyone building similar DAgger-to-autonomous-RL pipelines.

## Links

- [Paper](https://arxiv.org/abs/2610.22368)
