---
title: "Humanoid Horizon: Extending Task Horizon in Whole-Body Loco-Manipulation via Parallel Training, Dynamic Starting, and Reward Gating"
date: 2026-10-06
topic: Humanoid
tags: [humanoid, robotics, loco-manipulation, reinforcement-learning, long-horizon, benchmark]
source: https://arxiv.org/abs/2610.08320
venue: "arXiv"
---

## Summary

This paper studies why humanoid RL policies degrade on long-horizon loco-manipulation tasks that require moving multiple heavy objects in sequence within one episode, identifying two specific failure modes — easy-reward bias toward early stages and catastrophic forgetting of earlier stages — and proposing three training mechanisms (parallel training, dynamic starting, reward gating) to counter them on a new two-object benchmark (LHM-Humanoid).

## Key Contributions

- Diagnosis of "easy-reward bias" and catastrophic forgetting as the specific mechanisms behind task-horizon degradation in multi-stage humanoid manipulation.
- Parallel Training: splitting scenes into concurrent per-stage rollout streams under one shared policy so every transport stage keeps receiving gradient signal.
- Dynamic Starting: refreshing each environment's initial state with terminal states sampled from upstream rollouts, broadening state coverage at stage transitions.
- Reward Gating: zeroing out remaining-episode reward in later stages if an earlier-placed object is disturbed past a threshold, discouraging the policy from undoing completed sub-goals.
- A new benchmark (LHM-Humanoid) with 350 training scenes and 66 held-out scenes, reporting >80% per-stage success rates.

## Strengths

- Names and isolates specific, generalizable failure modes (easy-reward bias, catastrophic forgetting) rather than treating long-horizon degradation as a single vague phenomenon.
- The three proposed fixes are individually simple, interpretable, and apply to the credit-assignment/curriculum level rather than requiring a new architecture.
- Includes a held-out generalization split (66 scenes) rather than only in-distribution evaluation.

## Weaknesses

- Benchmark is limited to two-object transport scenarios; unclear how the mechanisms scale to tasks with more objects, more stages, or more varied action types beyond carrying/placing.
- Reward Gating is a fairly blunt instrument (hard zeroing past a displacement threshold) that could penalize legitimate recovery behavior if an object is only slightly perturbed.
- Metadata discrepancies across sources (different arXiv IDs/dates reported for the same title) suggest this may still be an early-stage preprint with possible revisions pending.

## Open Questions

- Do the same three mechanisms transfer to loco-manipulation tasks that are not simple sequential object transport (e.g., tool use, assembly, bimanual coordination)?
- How sensitive is Reward Gating's threshold to task and object properties, and does it require per-task tuning?
- Does Dynamic Starting risk creating a feedback loop where the policy only ever sees states its own upstream rollouts produce, narrowing rather than broadening coverage over training?

## Significance

Long-horizon credit assignment is one of the central open problems in scaling humanoid RL beyond short pick-and-place demos, and this paper's targeted diagnosis-plus-fix approach offers a concrete, testable recipe that other long-horizon humanoid work can build on or benchmark against.

## Links

- [Paper](https://arxiv.org/abs/2610.08320)
