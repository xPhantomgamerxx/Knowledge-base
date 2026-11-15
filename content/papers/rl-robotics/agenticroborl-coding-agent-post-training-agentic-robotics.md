---
title: "AgenticRoboRL: Bringing Coding-Agent Post-Training to Agentic Robotics"
date: 2026-10-20
topic: RL-Robotics
tags: [agentic-rl, multi-turn-rl, vla-posttraining, robot-planner]
source: https://arxiv.org/abs/2610.28589
venue: "arXiv"
---

## Summary

AgenticRoboRL brings the post-training recipe that worked for coding agents (SFT on successful trajectories, then multi-turn RL on outcome rewards) to agentic robotics planners, which today mostly sit on closed-source LLMs that are never improved from their own deployment data. The framework uses harness-specific adapters to connect a planner's recorded calls (to VLA skills or to generated robot-control code) to downstream task outcomes, so one RL pipeline can post-train planners across different "harnesses" (e.g., calling a frozen VLA policy, or writing Python against robot APIs).

## Key Contributions

- A general adapter abstraction that logs planner interactions (task, initial-state ID, attempt index, terminal reward, validity, token IDs/log-probs) so multi-turn RL can be applied uniformly whether the planner invokes a VLA skill or emits executable robot code.
- Two concrete adapters released (RPent for frozen-VLA skill invocation, CaP-X for code-as-policies style control-code generation).
- Only the planner is updated; downstream execution components (the VLA, the robot API) stay frozen, isolating the RL signal to the decision-making layer.
- Empirical demonstration that this post-training loop lifts a 9B-parameter planner's LIBERO-PRO success rate from 18.1% to 71.0% (18.1% to 65.1% via SFT, +5.9pp more from RL), approaching a much larger proprietary model's memory-augmented performance (72.1%) without external memory.

## Strengths

- Addresses a real architectural gap: most "agentic robotics" stacks today bolt a static, closed LLM planner onto a trainable low-level policy, so the planner itself never improves from experience — this paper gives a concrete recipe to fix that.
- The adapter abstraction is a genuinely reusable idea: it cleanly separates "how do we get credit assignment from this harness" from "how do we run RL," which should make it easier to extend to new agentic robotics stacks.
- Reports generalization beyond the training distribution (72.2% on LIBERO-Plus with the same trained planner), suggesting the gains aren't purely overfit to LIBERO-PRO's specific task formatting.

## Weaknesses

- Results are LIBERO-PRO/LIBERO-Plus simulation only; there is no real-robot evaluation, which is a significant gap for a method whose entire motivation is "closing the loop" on real deployment.
- The CaP-X (code-generation) harness results are much weaker in absolute terms (2.7% to 28.5%), and third-party reviewers note this reflects harness difficulty rather than a clean success story — the headline 71% number is specific to the easier RPent/frozen-VLA harness.
- Comparisons to memory-augmented systems are described by reviewers as not fully controlled, so the "approaches Codex-with-memory" framing should be read cautiously.
- Each new harness needs its own bespoke adapter, so the approach is not plug-and-play across arbitrary agentic robotics stacks without engineering effort.

## Open Questions

- Does RL-based planner post-training transfer to real-robot execution, where state estimation, timing, and partial observability are far noisier than in LIBERO simulation?
- How does the planner's RL-induced behavior change interact with changes to the frozen low-level VLA skill library (e.g., if the VLA is later updated or fine-tuned itself)?
- Can the adapter abstraction be extended to harnesses involving human-in-the-loop correction or multi-robot coordination, rather than single-planner/single-robot settings?

## Significance

It is one of the first concrete demonstrations that the "coding-agent RL post-training" playbook (SFT-then-RL on outcome rewards, applied to an LLM planner rather than the low-level controller) transfers to agentic robotics, pointing at a path for making hierarchical VLA-orchestration systems self-improving rather than permanently reliant on a frozen, closed-source planner.

## Links

- [Paper](https://arxiv.org/abs/2610.28589)
- [GitHub](https://github.com/xinxinliu-ai/AgenticRoboRL)
- [Project Page](https://xinxinliu-ai.github.io/AgenticRoboRL/)
